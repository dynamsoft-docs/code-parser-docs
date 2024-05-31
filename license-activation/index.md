---
layout: default-layout
title: Dynamsoft Code Parser Licensing - Main Page
description: This is the main page of Dynamsoft Code Parser Licensing.
keywords: license initialization, licensing
needAutoGenerateSidebar: false
permalink: /license-activation/index.html
---

# License Initialization

## Get a trial license

You can request a 30-day trial license via the [Request a Trial License](https://www.dynamsoft.com/customer/license/trialLicense?product=dcp&utm_source=docs){:target="_blank"} link.

You can contact our support team via the [Contacting Us](https://www.dynamsoft.com/contact/){:target="_blank"} link when:

- You want request for an Offline trial license.
- Your license generation failed.

## Get a Full License

<a href="https://www.dynamsoft.com/company/contact" target="_blank">Contact us</a> to purchase a full license.

## Set the License In the Code

The following shows how to set the license in the code.

<div class="sample-code-prefix template2"></div>
   >- C++
   >- JavaScript
   >- Android
   >- Objective-C
   >- Swift
   >
>
```cpp
    int errorCode = 1;
    char errorMsg[512];
    errorCode = CLicenseManager::InitLicense("YOUR-LICENSE-KEY", errorMsg, 512);
    if (errorCode != EC_OK)
        cout << "License initialization error: " << errorMsg << endl;
    // add further process
```
>
```javascript
Dynamsoft.License.LicenseManager.initLicense("YOUR-LICENSE-KEY");
```
>
```java
LicenseManager.initLicense("YOUR-LICENSE-KEY", this, (isSuccess, error) -> {
   if (!isSuccess) {
          error.printStackTrace();
   }
});
```
>
```objc
[DSLicenseManager initLicense:@"YOUR-LICENSE-KEY" verificationDelegate:self];
- (void)onLicenseVerified:(BOOL)isSuccess error:(nullable NSError *)error {
    if (!isSuccess && error != nil) {
        NSLog(@"error: %@", error);
    }
}
```
>
```swift
LicenseManager.initLicense("YOUR-LICENSE-KEY", verificationDelegate: self)
func onLicenseVerified(_ isSuccess: Bool, error: Error?) {
   if !isSuccess {
          if let error = error {
             print("\(error.localizedDescription)")
          }
   }
}
```
