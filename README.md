# alpha-facebookLogin

This is an example component for use with Alpha Anywhere that demonstrates basic login and logout using the Facebook SDK.

The app must be built as a Cordova app using the Cordova App Builder built into Alpha Anywhere.
See: [Alpha Anywhere](https://www.alphasoftware.com/mobile-app-development-platform)

## Plugins Required
[cordova-plugin-fbsdk](https://github.com/MaximBelov/cordova-plugin-fbsdk)

## Installation

Copy the component into a web project directory and create a new Cordova project, using this component as the initial UX component.

Under **Required Third Party Plugins**, check the **Cordova Facebook SDK**.

You will need to provide (at a minimum) the Facebook App ID, the Facebook App Name and the Client Token. See the [Facebook Developers Page](https://developers.facebook.com) for more information on setting up a Facebook App.

## Facebook Requirements and Setup [Android]

If you plan on rolling this out on Android, you will need to generate a hash of your Android key(s) and submit those to the Developers page on Facebook to get it working. Furthermore, if you are generating this hash on Windows (specifically 64 bit versions), please use version 0.9.8e or 0.9.8d of OpenSSL for Windows and not 0.9.8k.

You can use the Keytool command line utility which is distributed with each installation of Java to generate an Android Key hash for **debug** builds. 

**MacOS**

```
keytool -exportcert -alias androiddebugkey -keystore ~/.android/debug.keystore | openssl sha1 -binary | openssl base64
```
The password is android.

**Windows**

```
keytool -exportcert -alias androiddebugkey -keystore %HOMEPATH%\.android\debug.keystore | openssl sha1 -binary | openssl base64

```
The password is android.

## Facebook Requirements and Setup [iOS]

If you plan on rolling this out on iOS, please note that you will need to ensure that you have properly set up your Native iOS App settings on the Facebook App Dashboard. Please see [Getting Started with the Facebook SDK](https://developers.facebook.com/docs/ios/getting-started/)

## Cocoapods

This plugin use the CocoaPods dependency manager in order to satisfy the iOS Facebook SDK library dependencies.

Therefore please make sure you have Cocoapods installed in your iOS build environment - setup instructions can be found [here](https://cocoapods.org). Also make sure your local Cocoapods repo is up-to-date by running 

```
pod repo update
```

If you are building your project in Xcode, you need to open YourProject.xcworkspace (not YourProject.xcodeproj) so both your Cordova app project and the Pods project will be loaded into Xcode.

You can list the pod dependencies in your Cordova iOS project by installing [cocoapods-dependencies](https://github.com/segiddins/cocoapods-dependencies):

```
sudo gem install cocoapods-dependencies
cd platforms/ios/
pod dependencies

```

### Error: pod: Command failed with exit code 31

If you install the plugin and this error is generated: 

```
Failed to install 'cordova-plugin-fbsdk': Error: pod: Command failed with exit code 31

```
it most likely means that your local Pod repo is not up-to-date. In order to solve the problem, prior the installation, run the following command in your platform to update your Pod repo:

```
pod update
```


 











