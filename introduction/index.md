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

    All versions of the AAMVA Driver License/Identification specification used in the USA and in Canada supported. Fields parsed from South Africa driver licenses are currently limited to some personal information, while full information will be parsed in future releases.

> More scenarios will be supported in future releases, such as International COVID-19 Vaccination Certificate, MRZ and ID parsing.

## Supported Platforms

| Platforms | Languages                 |
|-----------|---------------------------|
| <img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACIAAAAiCAYAAAA6RwvCAAAACXBIWXMAAAsSAAALEgHS3X78AAADPklEQVRYhZ1XvY4TMRD+JqKkCG+QDiQKFtEgUWR5AKQtKfMAFCkpt6RMTZXyKpR7AnIFJSKRDonuUlJBkCjoBs3e55zXa3udG2mlxPbMfPNvi6qilERkBqABUAOw388C1j2AA4AtgI2qHkplT0oOiUgtIib8hiDs908A1wAe8bvm2pZnbozHeIuQmEdSH4CKgs2yBYAp1+330f3n2pTnlt7/heehKqsrA2JpOAG0gcIZQdQRnpp7swBgS1nLs4AAWFPgwApat8oYYEq3kfWKMtdFQAhi53shYvFgLxKimMemlD0AEwtHUhG9scjF2suhgVc8MMcwTKfyFRFz3TcAXwH8jeS1CXgK4EtRFQCvAHyn0pAeAngB4Lmq7jr9HhCz9geAi4Tg9yzPdSGQd1T4IbH/FsATVb0tby/2Ftdc7HvVUBCeLjlLc6ko9g5oKQiPL5q0sVyasG3PrSVn3FyP7KfIddkUmcy5YZhwdlyqaiypHFUsu/sAmaU2qfPSMDzwZkeOXDzPIlVdswjGwNYTIh6ztgrLUESWIqIishORluUfs3rMANM9E86AN4ne4egzgNeO0VxKS90ocFeDKePurgG5cDuDjOe3A3I1cn7unbE5szEvsJwXntCKgBry7Als4xpXAkxXQlpQhoMewnAlS5reaei1gxt4/nUiKOPOI8lG5vWZ2BCLTuhMg1tSljI3Gm+/W0g2nVzDo4XJO0aBt06GTOi2aMZ7lOoHWwo8i5jEju9UVUsmU86CJnHZmZbkWMKTvbCClmbzxClMXJZ6sb4PiC40bDhXORfTlfvEmc3IPAmpYQvolXN3H+GV/xOAjwD+JQS8pPcuON5XuOsdFtrkTOkpvD2/ZZKf7jYTWmwbv6gsRWbB43Du0LIpp/go8bwZvhKRUzMM61xzfYHxbSPrm3PL2JtfXVsIN8cuz1Vsn50xW3kj8pqU1dHnhNfc2mBtFpZx7m0UnGs7j55TYr7SyOw5lbHH3+bAeE/XKoc0+uTk3ipscFxbhUb4ylIgBjmSiGHsEe4qZ6F9Tx3dyMgqjYArTSp3nbQ/XYXw+1P6xPCUR8N1bpab1d1sYk7Yon2jz1DyW1c13n7OqOI/jmBGl5fJ/S8AAAAASUVORK5CYII=" alt="web"> Web       | JavaScript                |

## How to use

There are mainly four steps to use a CodeParser, the following takes the JavaScript edtion for example:

1. Initialize license

    Before start, it’s essential to set a license which gives you permission to use DCP. You can acquire a trial license via the [customer portal](https://www.dynamsoft.com/customer/license/trialLicense?ver=1.0.0&utm_source=guide&product=dcp&package=js). If you purchased a full license, then please use that.

2. Create Code Parser instance

    Then you can create a Code Parser instance for later use. Since DCP JavaScript Edition is based on JavaScript and WebAssembly, it's designed to load and compile the WASM resources (the engine files) automaticly before creating a instance. Methods to set the engine path and to load WASM are also provided.

3. Set code format

    When the instance is set up, you should set the code format (see [EnumCodeFormat](../programming/javascript/api-reference/enum/EnumCodeFormat.md)) that you want to get information from.

4. Parse code

    The `parseData()` method can then be called to get results in a specific format (see [EnumResultInfoType](../programming/javascript/api-reference/enum/EnumResultInfoType.md)).

*Note：*

> If your input code needs a public key or certificate to help parsing, please set it up beforehand.
> For example, setting a public key before parsing South Africa driver license is required, while a certificate is usually needed when parsing a COVID-19 Vaccination Certificate.

## Next Step

Learn how to use DCP to add code parsing capabilities to your web application:

* [JavaScript (Web)]({{site.javascript}})
