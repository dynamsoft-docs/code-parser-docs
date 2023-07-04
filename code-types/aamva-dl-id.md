---
layout: default-layout
title: North America DL/ID - Supported Code Types 
description: This page shows the details of code type North America DL/ID.
keywords: aamva, code types
needAutoGenerateSidebar: true
needGenerateH3Content: false
noTitleIndex: true
---

# North America Driver License and Identification

## Overview

The AAMVA DL/ID Card Design Standard specified by the American Association of Motor Vehicle Administrators (AAMVA) defines how to encode machine-readable information in PDF417 and magnetic stripe.

Dynamsoft Code Parser supports all versions of the AAMVA DL/ID specification (2000, 2003, 2005, 2009, 2010, 2011, 2012, 2013, 2016) and specifies two code types:

* AAMVA_DL_ID
* AAMVA_DL_ID_WITH_MAG_STRIPE

## Fields

The exposed fields for each code type is defined as below:

### AAMVA_DL_ID Fields

| Field Name | Description |
| ---------- | ----------- |
| CodeType | Code type, always has value "AAMVA_DL_ID" |
| AAMVAVersionNumber | AAMVA Version Number |
| issuerIdentificationNumber | Issuer Identification Number (IIN) |
| jurisdictionVersionNumber | Jurisdiction Version Number |
| fullName | Full name of cardholder <br>Present in version 1 (2000) |
| lastName | Last name of cardholder |
| givenName | Given name of cardholder |
| firstName | First name of cardholder |
| middleName | Middle name of cardholder |
| suffix | Name suffix |
| prefix | Name prefix |
| street_1 | Street portion of the cardholder address |
| street_2 | Second line of street portion of the cardholder address |
| city | City portion of the cardholder address |
| jurisdictionCode | State portion of the cardholder address |
| postalCode | Postal code portion of the cardholder address |
| residenceStreet_1 | Driver Residence Street Address 1 <br>Present in version 1 (2000) |
| residenceStreet_2 | Driver Residence Street Address 2 <br>Present in version 1 (2000) |
| residenceCity | Driver Residence City <br>Present in version 1 (2000) |
| residenceJurisdictionCode |  Driver Residence Jurisdiction Code <br>Present in version 1 (2000) |
| residencePostalCode | Driver Residence Postal Code <br>Present in version 1 (2000) |
| licenseNumber | License/ID Number |
| vehicleClass | Jurisdiction-specific vehicle class / Driver License Classification Code |
| restrictionCode | Jurisdiction-specific codes that represent restrictions to driving privileges |
| endorsementsCode | Jurisdiction-specific codes that represent additional privileges granted to the cardholder beyond the vehicle class |
| heightInCentimeters | Height in centimeters <br>Present in version 1 (2000) |
| height | Height of cardholder |
| weightInKilograms | weight in kilograms |
| weightInPounds | weight in pounds |
| eyeColor | Eye Color |
| hairColor | Hair color |
| expirationDate | Expiration Date |
| birthDate | Date of Birth |
| sex | Sex |
| issuedDate | Date on which the document was issued |
| issueTimestamp | Issue Timestamp used by some jurisdictions to validate the document against their data base |
| numberOfDuplicates | Number of duplicate cards issued for a license or ID if any |
| medicalIndicator | Medical Indicator/Codes |
| organDonorIndicator | Indicator that the cardholder is an organ donor |
| nonResidentIndicator | Non-Resident Indicator |
| customerIdentifier | Unique Customer Identifier |
| socialSecurityNumber | Social Security Number |
| alternativeBirthDate | Driver 'AKA' Date Of Birth |
| alternativeSocialSecurityNumber | Driver ‘AKA’ Social Security Number |
| nameAlias | Driver 'AKA' Name |
| lastNameAlias |  Alias/'AKA' Last Name |
| givenNameAlias | Alias/'AKA' Given Name |
| firstNameAlias | Alias/'AKA' First Name |
| middleNameAlias | Alias/'AKA' Middle Name |
| suffixAlias | Alias/'AKA' Suffix |
| prefixAlias | Alias/'AKA' Prefix |
| permitClassificationCode | Driver Permit Classification Code |
| permitExpirationDate | Driver Permit Expiration Date |
| permitIdentifier | Permit Identifier |
| permitIssuedDate | Driver Permit Issue Date |
| permitRestrictionCode | Driver Permit Restriction Code |
| permitEndorsementCode | Driver Permit Endorsement Code |
| weightRange | Indicates the approximate weight range of the cardholder |
| documentDiscriminator | Document Discriminator Number |
| issuingCountry | Country in which DL/ID is issued |
| federalCommercialVehicleCodes | Federal Commercial Vehicle Codes |
| birthPlace | Place of birth |
| auditInfomation | Audit information |
| inventoryControlNumber | Inventory control number |
| race | Codes for race or ethnicity of the cardholder |
| standardVehicleClassification | Standard vehicle classification code(s) |
| standardEndorsementsCode | Standard endorsement code(s) |
| standardRestrictionCode | Standard restriction code(s) |
| vehicleCodeDescription | Jurisdiction-specific vehicle classification description |
| endorsementsCodeDescription | Jurisdiction-specific endorsement code description |
| restrictionCodeDescription | Jurisdiction-specific restriction code description |
| complianceType | Compliance Type, 'F' = fully compliant and 'N' = non-compliant. |
| cardRevisionDate | Card Revision Date |
| hazmatEndorsementExpirationDate | Date on which the hazardous material endorsement granted by the document is no longer valid |
| limitedDurationDocumentIndicator | Limited Duration Document Indicator |
| familyNameTruncation | Family name truncation. A code that indicates whether a field has been truncated (T), has not been truncated (N), or –unknown whether truncated (U) |
| firstNameTruncation | First name truncation. A code that indicates whether a field has been truncated (T), has not been truncated (N), or –unknown whether truncated (U) |
| middleNameTruncation | Middle name truncation. A code that indicates whether a field has been truncated (T), has not been truncated (N), or –unknown whether truncated (U) |
| under18Until | Date on which the cardholder turns 18 years old |
| under19Until | Date on which the cardholder turns 19 years old |
| under21Until | Date on which the cardholder turns 21 years old |
| veteranIndicator | Indicator that the cardholder is a veteran |
| jurisdictionSubfiles | Jurisdiction-Specific Fields |


### AAMVA_DL_ID_WITH_MAG_STRIPE Fields

| Field Name | Description |
| ---------- | ----------- |
| CodeType | Code type, always has value "AAMVA_DL_ID_WITH_MAG_STRIPE" |
| track1 | Information in track 1 |
| stateOrProvince | Mailing or residential code |
| city | City portion of the cardholder address |
| name | Full name of cardholder |
| address | Mailing address |
| LRCforTrack1 | Longitudinal redundancy check used to verify the data of field `track1` |
| track2 | Information in track 2 |
| ISOIIN | The assigned identification number from ISO |
| DLorID_Number | The DL/ID number assigned by each jurisdiction |
| expirationDate | Date of expiry |
| expirationYear | Year of expiry |
| expirationMonth | Month of expiry |
| birthDate | Date of birth |
| birthYear | Year of birth |
| birthMonth | Month of birth |
| birthDay | Day of birth |
| DLorID_NumberOverflow | Overflow for DL/ID number longer than 13 characters |
| LRCforTrack2 | Longitudinal redundancy check used to verify the data of field `track2` |
| track3 | Information in track 3 |
| magStripeVersion | The version level of the mag stripe format |
| jurisdictionVersion | The jurisdiction version level of the mag stripe format |
| postalCode | Postal code |
| class | Represents the type of DL (ANSI codes modified for CDLIS) |
| restrictions | Restrictions |
| endorsements | Endorsements |
| sex | Sex |
| height | Height |
| weight | Weight |
| hairColor | Hair Color |
| eyeColor | Eye Color |
| discretionaryData1 | Discretionary data for use by each jurisdiction |
| discretionaryData2 | Discretionary data for use by each jurisdiction |
| securityFunction | Discretionary data for use by each jurisdiction |
| LRCforTrack3 | Longitudinal redundancy check used to verify the data of field `track3` |
