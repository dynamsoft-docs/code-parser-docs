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

* Driver license/Identification
    
    Cover countries include South Africa, USA and Canada.
    
    All versions of the AAMVA Driver License/Identification specification used in the USA and in Canada supported.

* International COVID-19 Vaccination Certificate

  International certificate QR code (VDS-NC) in Australia supported.

## How to start

There are mainly five steps to use a CodeParser:
1.	Initialize license

    Before start, it’s essential to set a license which gives you permission to use DCP. You can acquire a trial license via the customer portal. If you purchased a full license, then please use that.

2.	Initialize engine

    In this step, DCP provides two methods, one to define the path where the WASM resources (the engine files) will be loading from, another to load engine. You can call them manually if you want to save some time before creating an instance.

3.	Create Code Parser instance

    Create a Code Parser instance for later use. 

4.	Set code format

    When the instance is set up, you should set the code format (see EnumCodeFormat) that you want to get information from.

5.	Parse code

    The `parseData()` method can then be called to get results in a specific format (see EnumResultInfoType). 

  Note:
    
    If your input code needs a public key or certificate to help parsing, please set it up beforehand. 
    For example, setting a public key before parsing from South Africa driver license is required, while a certificate is usually needed when parsing from a Vaccination Certificate. 


For more information about how to use DCP, read more in the user guide.

