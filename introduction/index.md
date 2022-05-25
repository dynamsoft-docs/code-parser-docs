---
layout: default-layout
title: Dynamsoft Code Parser Introduction  - Main Page
description: This is the main page of Dynamsoft Code Parser Introduction. 
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# Introduction to Dynamsoft Code Parser

When working with IDs, driver licenses, or sometimes even general barcodes, you may encounter results (usually as a plain string) that are "unreadable" but contain all the useful information you need. Dynamsoft Code Parser (DCP) is an SDK designed for parsing these types of results into human-readable information.

For the initial release, DCP is only available for web applications as "DCP JavaScript Edition". Based on JavaScript and WebAssembly, DCP JavaScript Edition can run in all major modern browsers on all major platforms.

## Usage Scenarios

* Driver license
    
    Cover countries: USA, Canada, South Africa.
    
    All versions of the AAMVA Driver License/Identification specification used in the USA and in Canada supported.

* International COVID-19 Vaccination Certificate

    International certificate QR code (VDS-NC) in Australia supported.

> More scenarios will be supported in future releases, such as MRZ and ID parsing. Please contact us if the data format you are using is not yet supported, or you want to use the parser on a currently unsupported platform.

## How to use

There are mainly four steps to use a CodeParser:

1.	Initialize license

    Before start, it’s essential to set a license which gives you permission to use DCP. You can acquire a trial license via the [customer portal](https://www.dynamsoft.com/customer/license/trialLicense?ver=1.0.0&utm_source=guide&product=dcp&package=js). If you purchased a full license, then please use that.

2.	Create Code Parser instance

    Then you can create a Code Parser instance for later use. Since DCP JavaScript Edition is based on JavaScript and WebAssembly, it's designed to load and compile the WASM resources (the engine files) automaticly before creating a instance. The methods to set the engine path and to load WASM are also provided.

3.	Set code format

    When the instance is set up, you should set the code format (see [EnumCodeFormat](../programming/javascript/api-reference/enum/EnumCodeFormat.md)) that you want to get information from.

4.	Parse code

    The `parseData()` method can then be called to get results in a specific format (see [EnumResultInfoType](../programming/javascript/api-reference/enum/EnumResultInfoType.md)). 


> Note:

> If your input code needs a public key or certificate to help parsing, please set it up beforehand. 
> For example, setting a public key before parsing South Africa driver license is required, while a certificate is usually needed when parsing a COVID-19 Vaccination Certificate. 


For more information about how to use DCP, read more in the [user guide](../programming/javascript/user-guide.md).

