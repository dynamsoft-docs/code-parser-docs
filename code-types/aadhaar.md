---
layout: default-layout
title: AADHAAR - Supported Code Types 
description: This page shows the details of code type AADHAAR.
keywords: AADHAAR, code types
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
---

# Aadhaar

## Overview

Dynamsoft Code Parser supports data from the normal QR codes or Secure QR codes on eAadhaar, Aadhaar Letter and Aadhaar PVC Card and specifies code types:

* AADHAAR

## Fields

The exposed fields for code type `AADHAAR` is defined as below:

| Field Name | Description |
| ---------- | ----------- |
| CodeType | Code type, always has value "AADHAAR" |
| referenceId | Reference number |
| lastFourAadhaarDigits | Last 4 digits of Aadhaar code |
| timeStamp | Date time stamp in "DDMMYYYYHHMMSSsss" (including milliseconds) |
| name | Name of cardholder |
| givenName | Given name of cardholder |
| dateOfBirth | Date of birth |
| gender | Gender |
| idNumber | The ID number |
| email | Email as hash |
| mobile | Mobile number as hash |
| yearOfBirth | Year of birth |
| address | Address |
| careOf | Care of like "s/o" |
| district | District name |
| landmark | Landmark |
| house | House number |
| location | Locality |
| pinCode | Pin code |
| postOffice | Post office name |
| state | State Name |
| street | Street Name |
| subdistrict | Sub District Name |
| VTC | VTC Name |
| image | Photo of the resident |
| signatureHASH | Signature |
