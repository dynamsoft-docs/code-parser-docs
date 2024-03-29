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

The following shows how you can apply for a 30-day free trial license.

- Sign in the [Customer Portal](https://www.dynamsoft.com/customer/index?utm_source=docs&product=dcp). Register for a Dynamsoft account if you haven't already done so;
- Go to [License > Trial License](https://www.dynamsoft.com/customer/license/trialLicense?utm_source=docs&product=dcp) page, select the correct version and package/edition, then click "Register for a 30-Day Trial";
- A 30-day private-trial license will be generated and the instruction on how to use it will show up on the page.

> NOTE
>
> In case the trial license fails to be generated, Dynamsoft Support team will get in touch with you. Or you can [contact us](https://www.dynamsoft.com/company/contact).

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
