---
layout: default-layout
title: Machine Readable Travel Documents - Supported Code Types 
description: This page shows the details of code type Machine Readable Travel Documents.
keywords: mrtd, code types
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
---

# Machine Readable Travel Documents

## Overview

The Machine Readable Travel Documents (MRTD) standard specified by the International Civil Aviation Organization (ICAO) defines how to encode information for optical character recognition on official travel documents.

Dynamsoft Code Parser supports all versions of MRTD and specifies five code types:

* MRTD_TD1_ID
* MRTD_TD2_ID
* MRTD_TD2_VISA
* MRTD_TD3_PASSPORT
* MRTD_TD3_VISA

## Fields

The exposed fields for each code type is defined as below:

### MRTD_TD1_ID Fields

| Field Name | Description |
| ---------- | ----------- |
| CodeType | Code type, always has value "MRTD_TD1_ID" |
| line1 | The first line of the Machine Readable Zone data |
| documentCode| Document code |
| issuingState| Issuing state or organization |
| checkDigitForDocumentNumber| Check digit to verify the data of field `documentNumber` |
| documentNumber| The document number given by the issuing State or organization, to uniquely identify the document from all other MROTDs issued by the State or organization |
| checkDigitForLongDocumentNumber| Check digit to verify the data of field longDocumentNumber |
| longDocumentNumber| if the document number has more than 9 character |
| optionalData1| Optional data elements in line 1 |
| line2| The second line of the Machine Readable Zone data |
| dateOfBirth | Date of birth |
| birthYear |  Year of birth |
| birthMonth |  Month of birth |
| birthDay |  Day of birth |
| checkDigitForBirthDate |  Check digit to verify the data of field `dateOfBirth` |
| sex | Sex |
| dateOfExpiry | Date of expiry |
| expiryYear | Year of expiry |
| expiryMonth | Month of expiry |
| expiryDay | Day of expiry |
| checkDigitForExpiryDate | Check digit to verify the data of field `dateOfExpiry` |
| nationality | Nationality |
| optionalData2 | Optional data elements in line 2  |
| compositeCheckDigit | Composite check digit |
| line3 | The third line of the Machine Readable Zone data |
| name | Name |
| primaryIdentifier | Primary identifier(s) |
| secondaryIdentifier | Secondary identifier(s) |
| fieldForCompositeCheck| Data used to calculate the composite check digit |

### MRTD_TD2_ID Fields

| Field Name | Description |
| ---------- | ----------- |
| CodeType | Code type, always has value "MRTD_TD2_ID" |
| line1 | The first line of the Machine Readable Zone data |
| documentCode| Document code |
| issuingState| Issuing state or organization |
| name | Name |
| primaryIdentifier | Primary identifier(s) |
| secondaryIdentifier | Secondary identifier(s) |
| line2| The second line of the Machine Readable Zone data |
| documentNumber| The document number given by the issuing State or organization, to uniquely identify the document from all other MROTDs issued by the State or organization |
| checkDigitForDocumentNumber| Check digit to verify the data of field `documentNumber` |
| nationality | Nationality |
| dateOfBirth | Date of birth |
| birthYear |  Year of birth |
| birthMonth |  Month of birth |
| birthDay |  Day of birth |
| checkDigitForBirthDate |  Check digit to verify the data of field `dateOfBirth` |
| sex | Sex |
| dateOfExpiry | Date of expiry |
| expiryYear | Year of expiry |
| expiryMonth | Month of expiry |
| expiryDay | Day of expiry |
| checkDigitForExpiryDate | Check digit to verify the data of field `dateOfExpiry` |
| optionalData| Optional data elements for use of the issuing State or organization |
| compositeCheckDigit| Composite check digit |

### MRTD_TD2_VISA Fields

| Field Name | Description |
| ---------- | ----------- |
| CodeType | Code type, always has value "MRTD_TD2_VISA" |
| line1 | The first line of the Machine Readable Zone data |
| documentCode| Document code |
| issuingState| Issuing state or organization |
| name | Name |
| primaryIdentifier | Primary identifier(s) |
| secondaryIdentifier | Secondary identifier(s) |
| line2| The second line of the Machine Readable Zone data |
| documentNumber| The document number given by the issuing State or organization, to uniquely identify the document from all other MROTDs issued by the State or organization |
| checkDigitForDocumentNumber| Check digit to verify the data of field `documentNumber` |
| nationality | Nationality |
| dateOfBirth | Date of birth |
| birthYear |  Year of birth |
| birthMonth |  Month of birth |
| birthDay |  Day of birth |
| checkDigitForBirthDate |  Check digit to verify the data of field `dateOfBirth` |
| sex | Sex |
| dateOfExpiry | Date of expiry |
| expiryYear | Year of expiry |
| expiryMonth | Month of expiry |
| expiryDay | Day of expiry |
| checkDigitForExpiryDate | Check digit to verify the data of field `dateOfExpiry` |
| optionalData| Optional data elements for use of the issuing State or organization |

### MRTD_TD3_PASSPORT Fields

| Field Name | Description |
| ---------- | ----------- |
| CodeType | Code type, always has value "MRTD_TD3_PASSPORT" |
| line1 | The first line of the Machine Readable Zone data |
| documentCode| Document code |
| issuingState| Issuing state or organization |
| name | Name |
| primaryIdentifier | Primary identifier(s) |
| secondaryIdentifier | Secondary identifier(s) |
| line2| The second line of the Machine Readable Zone data |
| passportNumber| Passport number |
| checkDigitForPassportNumber| Check digit to verify the data of field `passportNumber` |
| nationality | Nationality |
| dateOfBirth | Date of birth |
| birthYear |  Year of birth |
| birthMonth |  Month of birth |
| birthDay |  Day of birth |
| checkDigitForBirthDate |  Check digit to verify the data of field `dateOfBirth` |
| sex | Sex |
| dateOfExpiry | Date of expiry |
| expiryYear | Year of expiry |
| expiryMonth | Month of expiry |
| expiryDay | Day of expiry |
| checkDigitForExpiryDate | Check digit to verify the data of field `dateOfExpiry` |
| personalNumber| Personal number or other optional data elements |
| checkDigitForPersonalNumber| Check digit to verify the data of field `personalNumber` |
| compositeCheckDigit| Composite check digit |

### MRTD_TD3_VISA Fields

| Field Name | Description |
| ---------- | ----------- |
| CodeType | Code type, always has value "MRTD_TD3_VISA" |
| line1 | The first line of the Machine Readable Zone data |
| documentCode| Document code |
| issuingState| Issuing state or organization |
| name | Name |
| primaryIdentifier | Primary identifier(s) |
| secondaryIdentifier | Secondary identifier(s) |
| line2| The second line of the Machine Readable Zone data |
| documentNumber| The document number given by the issuing State or organization, to uniquely identify the document from all other MROTDs issued by the State or organization |
| checkDigitForDocumentNumber| Check digit to verify the data of field `documentNumber` |
| nationality | Nationality |
| dateOfBirth | Date of birth |
| birthYear |  Year of birth |
| birthMonth |  Month of birth |
| birthDay |  Day of birth |
| checkDigitForBirthDate |  Check digit to verify the data of field `dateOfBirth` |
| sex | Sex |
| dateOfExpiry | Date of expiry |
| expiryYear | Year of expiry |
| expiryMonth | Month of expiry |
| expiryDay | Day of expiry |
| checkDigitForExpiryDate | Check digit to verify the data of field `dateOfExpiry` |
| optionalData| Optional data elements for use of the issuing State |
