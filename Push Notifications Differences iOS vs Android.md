# Difference between push notifications in iOS and Android
The push notification features in iOS and Android are pretty strong differ.
 
 iOS is based on the push Opt-In model, which does not allow brands to send mobile push notifications to users of their applications until these users agree to their receive. Android, on the other hand, automatically allows
users to receive push notifications with the ability to discard them manually.

The Android approach compared to the default iOS gives more a wide audience of users with push support. However, when users do not have the ability to easily and obviously opt out of their receipt, irrelevant or too frequent notifications may
push customers to disable messages or uninstall the app.
## Android Push Notification Mechanisms
● The easiest way is to use Firebase Cloud Messaging (for Android devices with Google Apps).
FCM - Firebase Cloud Messaging is a new and improved version of GCM, is a messaging service in the Google cloud. It's free and very flexible.
● If your users have Huawei devices (that is, without Google Apps), you should resort to Huawei Push Kit.
● Of course, you can also create your own push provider of push notifications or use ready-made projects, since the platform is open source.
## iOS Push Notification Mechanisms
APNS stands for Apple Push Notification Service and is a cloud platform of the iOS system. It allows send iOS push notifications.
 ![push iOS](https://github.com/MariaDash/Mobile_Testing/blob/main/push_iOS.jpg)   
