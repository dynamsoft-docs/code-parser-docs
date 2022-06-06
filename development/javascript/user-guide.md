---
layout: default-layout
title: Dynamsoft Code Parser for JavaScript - User Guide
description: This is the user guide page of Dynamsoft Code Parser for JavaScript SDK.
keywords: user guide, javascript
breadcrumbText: User Guide
noTitleIndex: true
needAutoGenerateSidebar: true
needGenerateH3Content: true
---

<!--The original doc is hosted here => https://github.com/dynamsoft-docs/code-parser-docs-js/blob/main/development/javascript/user-guide.md -->

# Dynamsoft Code Parser for Your Website

Dynamsoft Code Parser JavaScript Edition (DCP-JS) is equipped with industry-leading algorithms for exceptional speed and accuracy in code parsing. With its well-designed API, you can equip your web pages with a code parser with just a few lines of code.

Once integrated, your users can open your website in a browser and parse codes on images to get readable information.

In this guide, you will learn step by step on how to integrate the DCP-JS SDK into your website.

<span style="font-size:20px">Table of Contents</span>

* [Hello World - Simplest Implementation](#hello-world---simplest-implementation)
* [Building your own page](#building-your-own-page)
  * [Include the SDK](#include-the-sdk)
  * [Configure the SDK](#configure-the-sdk)
  * [Interact with the SDK](#interact-with-the-sdk)
* [API Documentation](#api-documentation)

## Hello World - Simplest Implementation

Let’s start with the "Hello World" example of the SDK which demonstrates how to use the minimum code to enable a web page to parse codes into readable info.

The complete code of the "Hello World" example is shown below:

> Since the code that needs parsing is usually hard to understand and often comes from images, we choose an online image which contains a US driver license to demonstrate how to parse the code with the help of `BarcodeReader` . Please make sure your device is connected to the Internet when opening the following example in your browser.

```html
<!DOCTYPE html>
<html>

<body>
    <script src="https://cdn.jsdelivr.net/npm/dynamsoft-javascript-barcode@9.0.2/dist/dbr.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/dynamsoft-code-parser@1.0.0/dist/dcp.js"></script>
  <script>
        // Specifies a license 
        Dynamsoft.DBR.BarcodeReader.license = 'DLS2eyJvcmdhbml6YXRpb25JRCI6IjIwMDAwMSJ9';
        Dynamsoft.DCP.CodeParser.license =
            't0068lQAAAIkK/J98hFlGuR23+WYADkNElcVBif3GpdrcU/KkcU4eEvYHEopVEHGmxqEF2L+XTTJ/DNFYnrKm5RQlvCXNAX8=';
        // Initializes and uses the SDK
        (async () => {
            try {
                let reader = await Dynamsoft.DBR.BarcodeReader.createInstance();
                let parser = await Dynamsoft.DCP.CodeParser.createInstance();

                parser.setCodeFormat(Dynamsoft.DCP.EnumCodeFormat.CF_AUTO);

                // Decode the driver license with BarcodeReader
                let results = await reader.decode(
                    "https://demo.dynamsoft.com/samples/dbr/js/4.use-case/SampleDriversLicense.jpg");

                let info = "";
                for (let result of results) {
                    // Parse the "code" retrieved from the barcode
                    info = await parser.parseData(result.barcodeBytes);
                    // Show the information
                    alert(JSON.stringify(info));
                    // Check the readable information in the console
                    console.log(info);
                }
            } catch (ex) {
                alert(ex);
            }
        })();
    </script>
</body>

</html>
```

### About the code

* `license`: This property specifies a license key. Read more on [Specify the license](#specify-the-license).

* `createInstance()`: This method creates a CodeParser object.

* `setCodeFormat`: This method sets the code’s format before parsing.

* `parseData`: This method parses the code.

For the rest of the code, please read more about [DBR-JS](https://www.dynamsoft.com/barcode-reader/development/javascript/user-guide/?ver=latest#getting-started---hello-world).

## Building your own page

### Include the SDK

#### Use a CDN

The simplest way to include the SDK is to use either the [jsDelivr](https://jsdelivr.com/) or [UNPKG](https://unpkg.com/) CDN. The "hello world" example above uses **jsDelivr**.

* jsDelivr

    ```html
    <script src="https://cdn.jsdelivr.net/npm/dynamsoft-code-parser@1.0.0/dist/dcp.js"></script>
    ```

* UNPKG  

    ```html
    <script src="https://unpkg.com/dynamsoft-code-parser@1.0.0/dist/dcp.js"></script>
    ```

#### Host the SDK yourself

Besides using the CDN, you can also download the SDK and host its files on your own website / server before including it in your application.

Options to download the SDK:

* yarn

    ```cmd
    yarn add dynamsoft-code-parser
    ```

* npm

    ```cmd
    npm install dynamsoft-code-parser --save
    ```

Depending on how you downloaded the SDK and where you put it, you can typically include it like this:

```html
<script src="/dynamsoft-code-parser-js-1.0.0/dist/dcp.js"></script>
```

or

```html
<script src="/node_modules/dynamsoft-code-parser/dist/dcp.js"></script>
```

### Configure the SDK

Before using the SDK, you need to configure a few things.

#### Specify the license

The SDK requires a license to work, use the API `license` to specify the license key.

```javascript
Dynamsoft.DCP.CodeParser.license = "YOUR-LICENSE-KEY";
```

Please [contact Dynamsoft Support Team](https://www.dynamsoft.com/Company/Contact.aspx) to obtain a license.

#### Specify the location of the "engine" files

This is usually only required with frameworks like Angular or React, etc. where dbr.js is compiled into another file.

The purpose is to tell the SDK where to find the engine files (\*.worker.js, \*.wasm.js and \*.wasm, etc.). The API is called `engineResourcePath` :

```javascript
//The following code uses the jsDelivr CDN, feel free to change it to your own location of these files
Dynamsoft.DCP.CodeParser.engineResourcePath = "https://cdn.jsdelivr.net/npm/dynamsoft-code-parser@1.0.0/dist/";
```

### Interact with the SDK

#### Create a `CodeParser` object

To use the SDK, we first create a CodeParser object.

```javascript
Dynamsoft.DCP.CodeParser.license = "YOUR-LICENSE-KEY";
let parser = null;
try {
    parser = await Dynamsoft.DCP.CodeParser.createInstance();
} catch (ex) {
    console.error(ex);
}
```

Tip: When creating a CodeParser object within a function which may be called more than once, it’s best to use a “helper” variable to avoid double creation such as pParser in the following code

```javascript
Dynamsoft.DCP.CodeParser.license = "YOUR-LICENSE-KEY";
let pParser = null;

function foo() {
    try {
        const parser = await (pParser = pParser || Dynamsoft.DCP.CodeParser.createInstance());
    } catch (ex) {
        console.error(ex);
    }
}
```

#### Set code format

Before parsing, you need to specify the format of code to parse. See [EnumCodeFormat](https://www.dynamsoft.com/code-parser/docs/development/javascript/api-reference/enum/EnumCodeFormat.md) to check if DCP-JS covers the code format you need.

```javascript
parser.setCodeFormat(format); //format: EnumCodeFormat
```

#### Parse code

The method `parseData()` takes data in three formats: `number[]`, `Uint8Array` and `string`. If you want to parse a barcode into readable info, you should first extract the information from the barcode using DBR-JS before parsing it with DCP-JS.

> Read more about [DBR-JS](https://www.dynamsoft.com/barcode-reader/development/javascript/user-guide/?ver=latest#getting-started---hello-world).

```javascript
parser.parseData(data); //data: number[] | Uint8Array | string
```

#### Set encryption key if needed

If your input code requires a public key or certificate to help with parsing, please set it up before calling the `parseData()` method.

```javascript
parser.setCryptoPublicKey(key); //key: string
// or
parser.setCertificate(value); //value: Uint8Array | ArrayBuffer | string
parser.parseData(data); //data: number[] | Uint8Array | string
```

## API Documentation

You can check out the detailed documentation about the APIs of the SDK at
[https://www.dynamsoft.com/code-parser/docs/development/javascript/user-guide/?ver=latest](https://www.dynamsoft.com/code-parser/docs/development/javascript/user-guide/?ver=latest).
