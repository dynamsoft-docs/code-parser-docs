---   
layout: default-layout
title: Dynamsoft Code Parser Parameters under Dynamsoft Capture Vision
description: Introduce the parameters design of Dynamsoft Capture Vision related to Dynamsoft Code Parser.
keywords: Parameter, Parameter Template, Parameter Template File, Dynamsoft Code Parser
needAutoGenerateSidebar: true
noTitleIndex: true
needGenerateH3Content: true
---

# Parameter Organization Structure 

## Overview of Dynamsoft Capture Vision parameters Related to Dynamsoft Code Parser

Starting in version 2.0, Dynamsoft Code Parser is restructured under Dynamsoft Capture Vision Framework.

Dynamsoft Capture Vision (DCV) is designed for high scalability and flexibility, and its parameter system plays a crucial role in achieving this goal. The parameter system is highly configurable and can drive different behavior logic within the SDK. In this article, we will provide an overview of the parametric architecture design regarding the use of Dynamsoft Code Parser in the Dynamsoft Capture Vision framework.

>Note: If you are using Dynamsoft Code Parser out of DCV framework，go [Parameter Organization when Using Dynamsoft Code Parser Independently](#parameter-organization-when-using-dynamsoft-code-parser-independently)

### Key Terms

In order to eliminate ambiguity, we first define several key terms.

1. **Parameter**

   A parameter is designed to represent a particular aspect of the behavior of the SDK, and each parameter has its own name. For instance, the `ExpectedBarcodeCount` parameter is used to control the expected count of recognized barcodes. Parameters can be configured with specific values or ranges of values, which can be adjusted as required.

2. **Parameter template**

   A parameter template is a collection of parameters organized in a structured manner, expressed in JSON format. The name of the `CaptureVisionTemplate` object is also called "template name", which is a unique identifier assigned to each parameter template. In the DCV SDK, this name is used to load the relevant configurations and control runtime behavior.
  
3. **Parameter template file**

   A parameter template file is a JSON file that contains one or multiple parameter templates.

### Organization of a Parameter Template File

As shown in the example below, the organizational structure of a parameter template file consists of several top-level objects such as `CaptureVisionTemplates`, `SemanticProcessingOptions`,`CodeParserTaskSettingOptions` etc.

```json
{
    "CaptureVisionTemplates": [
        {
            "Name" : "CV_0",
            "ImageSourceName": "ISA_0",
            "ImageROIProcessingNameArray": ["TA_0" ],
            "SemanticProcessingNameArray": ["SP_0"] 
        }       
    ],
    "ImageSourceOptions": [ 
        {
            "Name": "ISA_0"
        }
    ],
    "TargetROIDefOptions" : [
        {
            "Name" : "TA_0",
            "TaskSettingNameArray": [ "LR_0", "BR_0", "DN_0" ]
        }
    ],
    "ImageParameterOptions": [
        {
            "Name": "IP_0"
        }
    ], 
    "BarcodeReaderTaskSettingOptions": [
        {
            "Name" : "BR_0",
            "BarcodeFormatSpecificationNameArray" : ["FS_0"]
        }
    ],
    "SemanticProcessingOptions": [
        {
            "Name": "SP_0",
            "TaskSettingNameArray": [
                "CP_0"
            ]
        }
    ],
    "CodeParserTaskSettingOptions": [
        {
            "Name": "CP_0"
        }
    ],
    "GlobalParameter":{
        "MaxTotalImageDimension":0
    }
}
```

With the exception of GlobalParameter, all top-level objects in the parameter template file are arrays of the corresponding object. For example,`CaptureVisionTemplates` are an array of `CaptureVisionTemplate` objects, and `TargetROIDefOptions` are an array of `TargetROIDef` objects.

Furthermore, to reuse the same parameter definitions, reduce the size of the parameter template file, and simplify the parameter configuration hierarchy, the reference relationship was adopted in the parameter template file design. For example, the value of the `ImageSourceName` parameter for the first object in `CaptureVisionTemplates` is `ISA_0`, which refers to the first object in `ImageSourceOptions`.

Therefore, a parameter template starts with an object in `CaptureVisionTemplates` and recursively searches for the objects that are directly or indirectly referenced by it, and then combines them to form a specific set of parameters. Then, the parameter template may be applied to DCV through "template name" to control its internal execution logic.

Next, we will focus on introducing some main objects and their relationships in a parameter template.

### Structure of a Parameter Template

The following table list the main objects type and description of a complete parameter template when using Dynamsoft Code Parser:

| Object Type | Description |
| :-- | :-- |
|  [CaptureVisionTemplate]({{site.dcv_parameters}}file/capture-vision-template.html)         |  This is the entry object of a parameter template in DCV. The `Name` parameter represents the name of the parameter template, which serves as its unique identifier.|
|  [ImageSource]({{site.dcv_parameters}}file/image-source.html)                  |  It defines the input for DCV, responsible for providing images to DCV. It can be defined as different image sources, including but not limited to image directories, scanners, cameras, etc.|
| [TargetROIDef]({{site.dcv_parameters}}file/target-roi-definition/index.html)                   |  It is used to specify one or more recognition tasks to be performed on some regions of interest (ROIs) within an image.|
|  [SemanticProcessing]({{site.dcv_parameters}}file/semantic-processing/index.html)            |  It is used to specify one or more code parsing tasks to be performed on text/byte results to help extract human readable information. |
|  [BarcodeReaderTaskSetting]({{site.dcv_parameters}}file/task-settings/barcode-reader-task-settings.html)      |  It is used to configure settings for barcode reading tasks performed on images in DCV. |
|  [LabelRecognizerTaskSetting]({{site.dcv_parameters}}file/task-settings/label-recognizer-task-settings.html)    |  It is used to configure settings for label recognition tasks performed on images in DCV.|
|  [CodeParserTaskSetting]({{site.dcv_parameters}}file/task-settings/code-parser-task-settings.html)         |  It is used to configure code parsing tasks such as passport MRZ, driving license and other user specific tasks in DCV etc.|
|  [ImageParameter]({{site.dcv_parameters}}file/image-parameter.html)              |  It provides various image-processing features to adjust and enhance the input image for better recognition results.|

For more details, please refer to [introduction of the capture vision template]({{ site.dcv_parameters }}file/capture-vision-template.html)

### How to Apply Parameters

Dynamsoft Capture Vision (DCV) provides following methods to apply DCP related parameters:

   1. `InitSettings/InitSettingsFromFile` - after calling this interface, each parameter template in the file/string will be converted into a single parameter template object. They will replace the previously associated parameter template objects on the Capture Vision Router instance.

   2. `ResetSettings` - after calling this API, the internal associated parameter template objects are reset to the factory state.

### Special Rules for DCV Parameter Configuration

In this section, we will discuss some special rules for configuring the DCV parameter templates. Understanding these rules will help you efficiently configure a simple and user-friendly parameter template.

#### Default Value of Parameters

Generally, the DCV parameter templates have been designed with many common scenarios in mind, so the default values of many parameters do not need to be modified. When configuring a custom template, you only need to configure required parameters and fine-tuning parameters related to business scenarios. Other optional parameters are automatically filled with default values. This simplifies your configuration and makes your templates easier to read.

#### Inherited Parameters

Sometimes, we need to configure multiple templates to adapt to different scenarios, but only a few parameter values differ between each template. DCV provides a parameter configuration inheritance mechanism that further reduces the amount of configuration work.
For example, when configuring `IP_A` and `IP_B` objects in `ImageParameterOptions`, you can define a `BaseImageParameterName` parameter in the `IP_B` object with a value of `IP_A`. Then `IP_B` object will inherit all the parameter definitions of `IP_A`, and if `IP_B` defines a parameter with the same name but a different value, that parameter will adopt the value of `IP_B`.

This allows you to create a new parameter template that inherits most of its configuration from an existing template, reducing the amount of repetitive configuration work needed.

## Parameter Organization when Using Dynamsoft Code Parser Independently

When using DCP out of DCV framework，the parameters are organized in a `CodeParserTaskSettingOptions` which defines a group of [`CodeParserTaskSetting`]({{ site.dcv_parameters }}file/task-settings/code-parser-task-settings.html) objects shown as below.

```json
{
    "CodeParserTaskSettingOptions": [
        {
            "Name": "DCP_READ_PASSPORT",
            "CodeSpecifications": ["MRTD_TD3_PASSPORT"]
        },
        {
            "Name": "DCP_READ_VISA",
            "CodeSpecifications": ["MRTD_TD2_VISA","MRTD_TD3_VISA"]
        }
    ]
}
```
