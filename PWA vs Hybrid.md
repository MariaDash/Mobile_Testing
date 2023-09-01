## PWA or mashup features
There are two main types of web apps that can be installed on Android devices. The main difference is whether the application code is embedded in an application package (hybrid) or hosted on a web server (pwa).

### Hybrid Web Apps : The code (HTML, JS, CSS) is packaged in an APK package and can be distributed through the Google Play Store. The viewer module is isolated from users' internet browser, with no session or cache sharing.

### Progressive Web Apps (PWA): The code (HTML, JS, CSS) is on the web and doesn't need to be packaged as an APK. Resources are downloaded and updated as needed by the service role. The Chrome browser renders and displays your app, but will look native and will not include the normal browser address bar, etc. You can share storage, cache, and browser sessions. In essence, this is similar to installing a shortcut in the Chrome browser in a special mode. PWAs can also be listed on the Google Play Store using a trusted web action.

### PWAs and hybrid web apps are very similar to the native Android app in that they:

+ Can be installed through the App Store (Google Play Store and/or Microsoft Store)
+ Access native device features such as camera, GPS, Bluetooth, notifications and contact list
+ Work offline (no internet connection)
PWAs also have some unique features:

+ Can be installed on the Android home screen directly from the web (no App Store).
+ Can optionally be installed via the Google Play Store using a trusted web action
+ Can be discovered by searching the web or shared via a URL link
+ Use a service worker to avoid having to package native code
You don't need a platform to build a hybrid app or PWA, but there are several popular platforms that this guide will cover, including PhoneGap (with Cordova) and Ionic (with Cordova or Capacitor using Angular or React).
