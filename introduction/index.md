---
layout: default-layout
title: Introduction - Dynamsoft Code Parser SDK
description: This is the main page of Dynamsoft Code Parser Introduction. 
needAutoGenerateSidebar: true
needGenerateH3Content: true
noTitleIndex: true
---

# Introduction to Dynamsoft Code Parser

When working with IDs, driver licenses, or sometimes even general barcodes, you may encounter results (usually as a plain string) that are "unreadable" but contain all the useful information you need. Dynamsoft Code Parser (DCP) is an SDK designed for parsing these types of results into human-readable information.

## Supported Code Types

* Machine Readable Travel Documents

All versions of Machine Readable Travel Documents (MRTD) specified by the International Civil Aviation Organization (ICAO) are supported.

For further details, take a look at [Machine Readable Travel Documents introduction]({{site.code_types}}mrtd.html).

* North America driver's license

Countries covered: USA, Canada.

All versions of the AAMVA Driver's License/Identification Specification used in the US and Canada are supported.

For further details, take a look at [North America DL/ID introduction]({{site.code_types}}aamva-dl-id.html).

* South African driver's license

The fields parsed from the South African driver's license are currently limited to some personal information, while the full information will be parsed in a future release.

For further details, take a look at [South Africa Driver License introduction]({{site.code_types}}za-dl.html).

* Aadhaar Card in India

The normal QR codes or Secure QR codes on eAadhaar, Aadhaar Letter and Aadhaar PVC Card are all capable to be parsed.

For further details, take a look at [Aadhaar introduction]({{site.code_types}}aadhaar.html).

* Vehicle Identification Number

The Vehicle Identification Number (VIN) following ISO 3779 and standard used in North America and European Union.

For further details, take a look at [VIN introduction]({{site.code_types}}vin.html).

## Supported Platforms

As of current version, DCP is available for web and server applications as "DCP JavaScript Edition" and "DCP C++ Edition".

| Platforms | Languages |
|-----------|-----------|
| Web | JavaScript |
| Server | C++ |
| Mobile | Java/Kotlin/Objective-C/Swift |

> Future versions will support more platforms, such as Android/Mobile, etc.

## Next Step

Learn how to use DCP to add code parsing capabilities to your application:

* [JavaScript (Web)]({{site.js}})
* [C++ (Server)]({{site.cpp}})
