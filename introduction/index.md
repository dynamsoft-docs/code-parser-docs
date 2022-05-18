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

  Cover countries include South Africa, USA and Canada.

  All versions of the AAMVA Driver License/Identification specification used in the USA and in Canada supported.

* Identification

  Cover countries include USA and Canada.

* International COVID-19 Vaccination Certificate

  International certificate QR code (VDS-NC) in Australia supported.

## How to start

The first step of using DCP is to acquire a trial license via the customer portal. If you purchased a full license, then please use that. 

After that, we should define the path where the WASM resources (the engine files) will be loading from. If the path isn’t specified, the library will try to find the engine files in the same directory as the main JavaScript file (dcp.js). 

You can create an instance of Code Parser directly without using `loadWasm()` which is used to manually load and compile the WASM resources.

When the instance is set up, you should set the code format (see EnumCodeFormat) that you want to get information from.  

The `parseData()` method can then be called to get results in a specific format (see EnumResultInfoType). If parsing process failed, you may need to check out whether your input code needs a public key or certificate to help parsing. For example, setting a public key before parsing from South Africa driver license is required, while a certificate is usually needed when parsing from a Vaccination Certificate. So DCP provides two methods, `setCryptoPublicKey()` and `setCertificate()` to cover above situations.

Finally, you can release the instance and all of the associated WASM resources by calling `destroyContext()` once all parsing job finished.
