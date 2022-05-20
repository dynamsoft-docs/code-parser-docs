---
layout: default-layout
title: Dynamsoft Code Parser JavaScript API - Main Page
description: This is the main page of Dynamsoft Code Parser JavaScript SDK API Reference.
keywords: CodeParser, api reference, javascript, js
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
breadcrumbText: API Reference
---

# JavaScript API Reference

The Dynamsoft Code Parser JavaScript library comes with one primary class: `CodeParser`.

## CodeParser

A CodeParser takes code data in forms of byte array or plain string as input and returns parsed results. The following code snippet shows its basic usage:

```js
let parser = await Dynamsoft.DCP.CodeParser.createInstance();
parser.setCodeFormat(enumcodeformat);
let result = await parser.parseData(code);
console.log(result);
```

The APIs for this class include:

### Initialize License

| API Name | Description |
|---|---|
| [license](#license) | Initializes license of DCP. |

### Initialize Engine

| API Name | Description |
|---|---|
| [engineResourcePath](#engineresourcepath) | Specifies the path of WASM engine. |
| [loadWasm()](#loadwasm) | Loads and compiles the WASM. |

### Create and Destroy

| API Name | Description |
|---|---|
| [createInstance()](#createinstance) | Creates a `CodeParser` instance. |
| [destroyContext()](#destroycontext) | Destroys the `CodeParser` instance in WASM. |

### Set Code Format

| API Name | Description |
|---|---|
| [setCodeFormat()](#setcodeformat) | Sets input code's format. |

### Parse Code Data

| API Name | Description |
|---|---|
| [parseData()](#parseData) | Parses code data for readable results. |

### Set Encryption Key

| API Name | Description |
|---|---|
| [setCryptoPublicKey()](#setcryptopublickey) | Set a public key if code parsing needs. |
| [setCertificate()](#setcertificate) | Set a certificate if code parsing needs. |





## license

Specify an online license or an offline license. Dynamsoft usually provides an online license. 

`license` needs to be set before `createInstance()` or `loadWasm()`.

```typescript
static license: string
```

### Code Snippet

```js
Dynamsoft.DCP.CodeParser.license = "YOUR-LICENSE-KEY";
let parser = await Dynamsoft.DCP.CodeParser.createInstance();
```

## engineResourcePath

Specifies the path to find the engine(s). The property needs to be set before [loadWasm](#loadwasm). If not specified, the library will try to find the engine in the same location as the main JavaScript file (dbr.js).

```typescript
static engineResourcePath: string
```

### Code Snippet

```js
Dynamsoft.DCP.CodeParser.engineResourcePath = "https://cdn.jsdelivr.net/npm/dynamsoft-javascript-codeparser@1.0.1/dist/";
await Dynamsoft.DCP.CodeParser.loadWasm();
```

## loadWasm

Downloads and compiles the engine to get it loaded/ready for a CodeParser instance to be created. You can call this API to silently set the operating environment of the library as soon as the page is loaded, avoiding unnecessary waiting time when using the library later.

If this API is not called beforehand, it will be called automatically when creating an instance of CodeParser.

```typescript
static loadWasm(): Promise<void>
```

### Code Snippet

```js
window.addEventListener('DOMContentLoaded', (event) => {
   Dynamsoft.DCP.CodeParser.loadWasm();
});
```

## createInstance

Creates a `CodeParser` instance.

```typescript
static createInstance(): Promise<BarcodeReader>
```

### Return Value

A promise resolving to the created `CodeParser` object.

### Code Snippet

```js
let reader = await Dynamsoft.DCP.CodeParser.createInstance();
```

## destroyContext

Destroys the `CodeParser` instance in WASM. If your page needs to create new instances from time to time, don't forget to destroy unused old instances.

```typescript
destroyContext(): void
```

### Code Snippet

```js
let parser = await Dynamsoft.DCP.CodeParser.createInstance();
// ... parse ...
parser.destroyContext();
```

## setCodeFormat

Sets the code format that needs parsing. See EnumCodeFormat to check if it has the code format you are looking for.

```typescript
setCodeFormat(format: EnumCodeFormat): Promise<void> 
```

### Parameters

`format`: specifies the code’s format represented by EnumCodeFormat.

### Return Value

A promise that resolves when the operation succeeds.

### Code Snippet

```js
await parser.setCodeFormat(Dynamsoft.DCP.EnumCodeFormat.CF_DL_AAMVA_ANSI);
// ... parse ...
```

## parseData

Parses the code into readable info.

```typescript
parseData(source: number[] | Uint8Array | string): Promise<ParseResult> 
```

### Parameters

`source`: specifies the code data represented by a numder[], Uint8Array or string.

### Return Value

A promise resolving to a `ParseResult` object which contains the parsing result.

### Code Snippet

```js
await parser.parseData(YOUR-CODE-THAT-NEEDS-PARSING);
```

### See Also

* [Uint8Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint8Array)
* [ParseResult](./interface/ParseResult.md)


## setCryptoPublicKey

Sets the public key if your parsing process needs one.

```typescript
setCryptoPublicKey(key: string): Promise<void>
```

### Parameters

`key`: specifies the public key represented by a string.

### Return Value

A promise that resolves when the operation succeeds.

### Code Snippet

```js
let parser = await Dynamsoft.DCP.CodeParser.createInstance();
parser.setCryptoPublicKey(YOUR-PUBLIC-KEY);
// … parse …
```

## setCertificate

Sets the certificate if your parsing process needs one.

```typescript
setCertificate(value: Uint8Array | ArrayBuffer | string): Promise<void>
```

### Parameters

`value`: specifies the certificate represented by a Uint8Array, ArrayBuffer or string.

### Return Value

A promise that resolves when the operation succeeds.

### Code Snippet

```js
let parser = await Dynamsoft.DCP.CodeParser.createInstance();
parser.setCertificate(YOUR-CERTIFICATE);
// … parse …
```

### See Also

* [ArrayBuffer](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer)

