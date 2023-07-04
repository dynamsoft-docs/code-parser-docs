---
layout: default-layout
title: Vehicle Identification Number - Supported Code Types 
description: This page shows the details of code type Vehicle Identification Number.
keywords: vin, code types
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
---

# Vehicle Identification Number

## Overview

Vehicle Identification Number (VIN) is a unique code used by the automotive industry to identify vehicles.

The parser supports all VIN codes following ISO 3779 and standard used in North America and European Union.

## Fields

The exposed fields for code type `VIN` is defined as below:

| Field Name | Description |
| ---------- | ----------- |
| CodeType | Code type, always has value "VIN" |
| WMI | World Manufacturer Identifier |
| region | Name of the region |
| VDS | Vehicle Descriptor Section |
| checkDigit | Check digit to verify the VIN code string |
| VIS | Vehicle Identification Section |
| modelYear | Building or model year of a vehicle |
| plantCode | Manufacturer plant (assembly plant) |
| serialNumber | Serial number of the vehicle |
