---
layout: default-layout
title: Dynamsoft Code Parser JavaScript SDK - Release Notes v1.x
description: This is the release notes page for Dynamsoft Code Parser JavaScript SDK v1.x.
keywords: release notes, javascript
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
---

# Release Notes for JavaScript SDK - 1.x

## 1.0.0 (05/30/2022)

 > First released: 05-30-2022

### New

* New property `license` to control license of DCP.
* New property `engineResourcePath` to specify the path of DCP WASM engine.
* New `loadWasm()` to `CodeParser` to load and compile the WASM.
* New method `createInstance()` to `CodeParser` to create a CodeParser instance.
* New method `destroyContext()` to `CodeParser` to destroy the CodeParser instance in WASM.
* New method `setCodeFormat()` to `CodeParser` to set what type of code you want to parse.
* New method `parseData()` to `CodeParser` to parse code.
* New method `setCryptoPyblicKey()` to `CodeParser` to set a public key if code parsing needs.
* New method `setCertificate()` to `CodeParser` to set a certificate if code parsing needs.


| Versions | Available Editions |
|---|---|
| 1.0.0 | JavaScript |
