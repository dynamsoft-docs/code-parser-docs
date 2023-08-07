---
layout: default-layout
Title: MappingStatus - Dynamsoft Code Parser Enumerations
Description: The enumeration MappingStatus of Dynamsoft Code Parser describes the mapping status of a parsed field.
Keywords: Mapping status
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
breadcrumbText: MappingStatus
---

# Enumeration MappingStatus

`MappingStatus` describes the mapping status of a parsed field.

<div class="sample-code-prefix template2"></div>
   >- JavaScript
   >- Android
   >- Objective-C
   >- Swift
   >- C++
   >
>
```javascript
export enum EnumMappingStatus {
   /** The field has no mapping specified. */
   MS_NONE = 0,
   /** Find a mapping for the field value. */
   MS_SUCCEEDED = 1,
   /** Failed to find a mapping for the field value. */
   MS_FAILED = 2
}
```
>
```java
public class EnumMappingStatus {
   /** The field has no mapping specified. */
   public static final int MS_NONE = 0;
   /** Find a mapping for the field value. */
   public static final int MS_SUCCEEDED = 1;
   /** Failed to find a mapping for the field value. */
   public static final int MS_FAILED = 2;
}
```
>
```objc
typedef NS_ENUM(NSInteger, DSMappingStatus)
{
   /** The field has no mapping specified. */
   DSMappingStatusNotSpecified = 0,
   /** Find a mapping for the field value. */
   DSMappingStatusSucceeded = 1,
   /** Failed to find a mapping for the field value. */
   DSMappingStatusFailed = 2
}NS_SWIFT_NAME(MappingStatus);
```
>
```swift
public enum MappingStatus : Int
{
   /** The field has no mapping specified. */
   none = 0
   /** Find a mapping for the field value. */
   succeeded = 1
   /** Failed to find a mapping for the field value. */
   failed = 2
}
```
>
```cpp
typedef enum MappingStatus
{
   /** The field has no mapping specified. */
   MS_NONE,
   /** Find a mapping for the field value. */
   MS_SUCCEEDED,
   /** Failed to find a mapping for the field value. */
   MS_FAILED
} MappingStatus;
```
