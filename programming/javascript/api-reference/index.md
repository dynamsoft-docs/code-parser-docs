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
| [](CodeParser.md#license) | Initialize license of DCP. |

### Create and Destroy

| API Name | Description |
|---|---|
| [createInstance()](CodeParser.md#createinstance) | Creates a `CodeParser` instance. |
| [destroyContext()](CodeParser.md#destroycontext) | Destroys the `CodeParser` instance in WASM. |

