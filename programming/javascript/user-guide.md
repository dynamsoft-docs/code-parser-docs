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

<!--The original doc is hosted here => https://github.com/dynamsoft-docs/code-parser-docs-js/blob/main/programming/javascript/user-guide.md -->

# Dynamsoft Code Parser for Your Website

Dynamsoft Code Parser JavaScript Edition is equipped with industry-leading algorithms for exceptional speed, accuracy in code parsing. With its well-designed API, you can equip your web page with a code parser by just adding a few lines of code.
Once integrated, your users can open your website in a browser and parse codes to get readable information.

In this guide, you will learn step by step on how to integrate this library into your website.

<span style="font-size:20px">Table of Contents</span>

* [Hello World - Simplest Implementation](#hello-world---simplest-implementation)
* [Building your own page](#building-your-own-page)
  * [Include the library](#include-the-library)
  * [Configure the library](#configure-the-library)
  * [Interact with the library](#interact-with-the-library)
* [API Documentation](#api-documentation)

<!-- **Popular Examples**

* Hello World - [Guide](#hello-world---simplest-implementation) \| [Github](https://github.com/Dynamsoft/barcode-reader-javascript-samples/blob/v9.0.2/1.hello-world/1.hello-world.html) \| [Run](https://demo.dynamsoft.com/Samples/DBR/JS/1.hello-world/1.hello-world.html?ver=9.0.2&utm_source=guide)
* Angular Sample - [Guide]() \| [Github]() \| [Run]()
* React Sample - [Guide]() \| [Github]() \| [Run]()
* Vue Sample - [Guide]() \| [Github]() \| [Run]() -->

## Hello World - Simplest Implementation

Let’s start with the "Hello World" example of the library which demonstrates how to use the minimum code to enable a web page to parse codes into readable info.

The complete code of the "Hello World" example is shown below:

*Note：*
> Since the code that needs parsing is usually hard to understand and often comes from images, we choose an online image which contains a US driver license to demonstrate how to parse the code with the help of `BarcodeReader`. Please make sure your device is Internet-connected when open the following example in browser.

```html
<!DOCTYPE html>
<html>
<body>
    <script src="https://cdn.jsdelivr.net/npm/dynamsoft-javascript-barcode@9.0.2/dist/dbr.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/dynamsoft-javascript-codeparser@1.0.0/dist/dcp.js"></script>
    <script>
        // Specifies a license, you can visit https://www.dynamsoft.com/customer/license/trialLicense?ver=9.0.2&utm_source=guide&product=dbr&package=js to get your own trial license good for 30 days. 
        Dynamsoft.DBR.BarcodeReader.license = 'DLS2eyJoYW5kc2hha2VDb2RlIjoiMTAxMTAyNDQ0LVRYbFhaV0pRY205cSIsIm9yZ2FuaXphdGlvbklEIjoiMTAxMTAyNDQ0In0=';
        Dynamsoft.DCP.CodeParser.license =
        't0068lQAAALYEhtEBvMXXW/PQNyEwn0zwxU2eDrsWWkyVFnHbiQlE6VXULCiJA5B7kAYMJRlKL5N94Wi7R62CEiCgJnJsfNc=';
        // Initializes and uses the library
        (async () => {
            try {
                let reader = await Dynamsoft.DBR.BarcodeReader.createInstance();
                let parser = await Dynamsoft.DCP.CodeParser.createInstance();

                parser.setCodeFormat(Dynamsoft.DCP.EnumCodeFormat.CF_DL_AAMVA_ANSI);

                // decode the driver license with BarcodeReader
                let results = await reader.decode(
                    "https://pic1.zhimg.com/v2-8a34c05de1b63d093ad3e3b9b985b630_r.jpg");

                var info = "";
                for (let result of results) {
                    // input code which is the decoding result in number[] format
                    info = await parser.parseData(result.barcodeBytes);
                    // pop up the readable info
                    alert(JSON.stringify(info));
                    // see the readable info in console
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

#### About the code

* `license`: This property specifies a license key. Note that the DCP license "t0068lQAAALYEhtEBvMXXW/PQNyEwn0zwxU2eDrsWWkyVFnHbiQlE6VXULCiJA5B7kAYMJRlKL5N94Wi7R62CEiCgJnJsfNc=" used in this example is an offline license. Read more on [Specify the license](#specify-the-license).

* `createInstance()`: This method creates a CodeParser object.

* `setCodeFormat`: This method sets the code’s type before parsing.

* `parseData`: This method parses code which could be number[], Uint8Array and string.


## Building your own page

### Include the library

#### Use a CDN

The simplest way to include the library is to use either the [jsDelivr](https://jsdelivr.com/) or [UNPKG](https://unpkg.com/) CDN. The "hello world" example above uses **jsDelivr**.

* jsDelivr

  ```html
  <script src="https://cdn.jsdelivr.net/npm/dynamsoft-javascript-codeparser@1.0.0/dist/dcp.js"></script>
  ```

* UNPKG  

  ```html
  <script src="https://unpkg.com/dynamsoft-javascript-codeparser@1.0.0/dist/dcp.js"></script>
  ```

#### Host the library yourself

Besides using the CDN, you can also download the library and host its files on your own website / server before including it in your application.

Options to download the library:

* yarn

  ```cmd
  yarn add dynamsoft-javascript-codeparser
  ```

* npm

  ```cmd
  npm install dynamsoft-javascript-codeparser --save
  ```

Depending on how you downloaded the library and where you put it, you can typically include it like this:

```html
<script src="/dynamsoft-codeparser-js-1.0.0/dist/dcp.js"></script>
```

or

```html
<script src="/node_modules/dynamsoft-javascript-codeparser/dist/dcp.js"></script>
```

Refer to [how to host the library](https://www.dynamsoft.com/barcode-reader/programming/javascript/user-guide/advanced-usage.html?ver=9.0.2&utm_source=guide&product=dbr&package=js#hosting-the-library).

### Configure the library

Before using the library, you need to configure a few things.

#### Specify the license

The library requires a license to work, use the API `license` to specify a license key.

```javascript
Dynamsoft.DCP.CodeParser.license = "YOUR-LICENSE-KEY";
```

Please Contact us via the [customer portal](https://www.dynamsoft.com/customer/license/trialLicense?ver=1.0.0&utm_source=guide&product=dcp&package=js) if you want an online license.

> If you registered a Dynamsoft account and downloaded the library from the official website, Dynamsoft will generate a 30-day trial license for you and put the license key into all the samples that come with the library.

#### Specify the location of the "engine" files

This is usually only required with frameworks like Angular or React, etc. where dbr.js is compiled into another file.

The purpose is to tell the library where to find the engine files (\*.worker.js, \*.wasm.js and \*.wasm, etc.). The API is called `engineResourcePath`:

```javascript
//The following code uses the jsDelivr CDN, feel free to change it to your own location of these files
Dynamsoft.DCP.CodeParser.engineResourcePath = "https://cdn.jsdelivr.net/npm/dynamsoft-javascript-codeparser@1.0.0/dist/";
```

### Interact with the library

#### Create a `CodeParser` object

To use the library, we first create a CodeParser object.

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
try {
    const parser = await (pParser = pParser || Dynamsoft.DCP.CodeParser.createInstance());
} catch (ex) {
    console.error(ex);
}
```

#### Set code format

Before parsing, it’s important to specify what kind of code you want to parse from. See [EnumCodeFormat](../javascript/api-reference/enum/EnumCodeFormat.md) to check if DCP covers the code format you need.

```javascript
parser.setCodeFormat(format);   //format: EnumCodeFormat
```

#### Parse code

The method parseData takes data in three formats: number[], Uint8Array, string. If you want to parse a barcode directly into readable info, you can use `BarcodeReader` or `BarcodeScanner` first to get its barcodeBytes and then use CodeParser to parse them.

```javascript
parser.parseData(data);   //data: number[] | Uint8Array | string
```

#### Set encryption key if needed

If the code you want to parse needs a public key or certificate to help parsing, please set it up before calling the `parseData()` method. 

```javascript
parser.setCryptoPublicKey(key);   //key: string
// or
parser.setCertificate(value);     //value: Uint8Array | ArrayBuffer | string
```

## API Documentation

You can check out the detailed documentation about the APIs of the library at
[https://www.dynamsoft.com/code-parser/docs/programming/javascript/user-guide/?ver=latest](https://www.dynamsoft.com/code-parser/docs/programming/javascript/user-guide/?ver=latest).

