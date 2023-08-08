---
layout: default-layout
Title: ValidationStatus - Dynamsoft Code Parser Enumerations
Description: The enumeration ValidationStatus of Dynamsoft Code Parser describes the validation status of a parsed field.
Keywords: Validation status
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
breadcrumbText: ValidationStatus
---

# Enumeration ValidationStatus

`ValidationStatus` describes the validation status of a parsed field.

<div class="sample-code-prefix template2"></div>
   >- JavaScript
   >- Android
   >- Objective-C
   >- Swift
   >- C++
   >
>
```javascript
export enum EnumValidationStatus
{
   /** The field has no validation specified. */
   VS_NONE = 0,
   /** The validation for the field has been succeeded. */
   VS_SUCCEEDED = 1,
   /** The validation for the field has been failed. */
   VS_FAILED = 2
}
```
>
```java
public class EnumValidationStatus
{
   /** The field has no validation specified. */
   public static final int VS_NONE = 0;
   /** The validation for the field has been succeeded. */
   public static final int VS_SUCCEEDED = 1;
   /** The validation for the field has been failed. */
   public static final int VS_FAILED = 2;
}
```
>
```objc
typedef NS_ENUM(NSInteger, DSValidationStatus)
{
   /** The field has no validation specified. */
   DSValidationStatusNone = 0,
   /** The validation for the field has been succeeded. */
   DSValidationStatusSucceeded = 1,
   /** The validation for the field has been failed. */
   DSValidationStatusFailed = 2
}NS_SWIFT_NAME(ValidationStatus);
```
>
```swift
public enum ValidationStatus : Int
{
   /** The field has no validation specified. */
   none = 0
   /** The validation for the field has been succeeded. */
   succeeded = 1
   /** The validation for the field has been failed. */
   failed = 2
}
```
>
```cpp
typedef enum ValidationStatus
{
   /** The field has no validation specified. */
   VS_NONE,
   /** The validation for the field has been succeeded. */
   VS_SUCCEEDED,
   /** The validation for the field has been failed. */
   VS_FAILED
} ValidationStatus;
```
