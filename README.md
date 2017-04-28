# Unique Device ID ANE V1.1.0 (Android+iOS)
This ANE provides you with some properties which they return different Device Identifiers. You may use them in your apps to identify your users even if your users are uninstalling/re-installing your apps. Nevertheless, make sure to read [this blog](http://www.myflashlabs.com/get-adobe-air-unique-device-id/) to learn the differences between the ANE properties and use the one which best suits your app requirements.

This ANE provides you with the following Identifiers:  
* [Android ID](http://myflashlab.github.io/asdoc/com/myflashlab/air/extensions/udid/UDID.html#androidId)
* [Serial Number](http://myflashlab.github.io/asdoc/com/myflashlab/air/extensions/udid/UDID.html#serialNumber)
* [Telephony Device ID](http://myflashlab.github.io/asdoc/com/myflashlab/air/extensions/udid/UDID.html#telephonyManagerDeviceId)
* [Telephony Subscriber ID](http://myflashlab.github.io/asdoc/com/myflashlab/air/extensions/udid/UDID.html#telephonyManagerSubscriberId)
* [UUID](http://myflashlab.github.io/asdoc/com/myflashlab/air/extensions/udid/UDID.html#UUID)
* [Unique Vendor ID](http://myflashlab.github.io/asdoc/com/myflashlab/air/extensions/udid/UDID.html#vendorId)
* [Advertising ID](http://myflashlab.github.io/asdoc/com/myflashlab/air/extensions/udid/UDID.html#retriveAdId())

# asdoc
[find the latest asdoc for this ANE here.](http://myflashlab.github.io/asdoc/com/myflashlab/air/extensions/udid/UDID.html)

# Demo .apk
you may like to see the ANE in action? [Download demo .apk](https://github.com/myflashlab/UDID-ANE/tree/master/FD/dist)

**NOTICE**: the demo ANE works only after you hit the "OK" button in the dialog which opens. in your tests make sure that you are NOT calling other ANE methods prior to hitting the "OK" button.
[Download the ANE](https://github.com/myflashlab/UDID-ANE/tree/master/FD/lib)

# AIR Usage
For the complete AS3 code usage, see the [demo project here](https://github.com/myflashlab/UDID-ANE/blob/master/FD/src/Main.as).

```actionscript
import com.myflashlab.air.extensions.udid.UDID;

UDID.init();

if(UDID.OS == UDID.ANDROID) trace(UDID.androidId);
else if(UDID.OS == UDID.IOS) trace(UDID.vendorId);
```

# AIR .xml manifest
```xml
<!--
FOR ANDROID:
-->
		<!--The new Permission thing on Android works ONLY if you are targetting Android SDK 23 or higher-->
		<uses-sdk android:targetSdkVersion="23"/>
		<uses-sdk android:minSdkVersion="15"/>
		
		<!--Required if you are using TelephonyManager API-->
		<!--<uses-permission android:name="android.permission.READ_PHONE_STATE" />-->
		
		<!--Required if you want to use the Android Advert ID-->
		<meta-data android:name="com.google.android.gms.version" android:value="@integer/google_play_services_version" />
		
		
<!--
FOR iOS:
-->
		<!--iOS 8.0 or higher can support this ANE-->
		<key>MinimumOSVersion</key>
		<string>8.0</string>



<!--
Embedding the ANE:
-->
<extensions>
	<extensionID>com.myflashlab.air.extensions.udid</extensionID>
	
	<!-- download the dependency ANEs from https://github.com/myflashlab/common-dependencies-ANE -->
	<extensionID>com.myflashlab.air.extensions.dependency.androidSupport</extensionID>
    <extensionID>com.myflashlab.air.extensions.dependency.overrideAir</extensionID>
	
	<!--Required if you are using TelephonyManager API-->
	<!--<extensionID>com.myflashlab.air.extensions.permissionCheck</extensionID>-->
	
	<!--Required if you want to use the Android Advert ID-->
	<extensionID>com.myflashlab.air.extensions.dependency.googlePlayServices.basement</extensionID>
  </extensions>
```

# Requirements
* This ANE is dependent on **googlePlayServices_basement.ane**, **androidSupport.ane** and **overrideAir.ane**. Download them from [here](https://github.com/myflashlab/common-dependencies-ANE).
* Android SDK 15 or higher
* iOS 8.0 or higher

# Permissions
If you are targeting AIR 24 or higher, you need to [take care of the permissions mannually](http://www.myflashlabs.com/adobe-air-app-permissions-android-ios/). Below are the list of Permissions this ANE might require. (Note: *Necessary Permissions* are those that the ANE will NOT work without them and *Optional Permissions* are those which are needed only if you are using some specific features in the ANE.)

Check out the demo project available at this repository to see how we have used our [PermissionCheck ANE](http://www.myflashlabs.com/product/native-access-permission-check-settings-menu-air-native-extension/) to ask for the permissions.

**Necessary Permissions:**  
none

**Optional Permissions:**  

1. PermissionCheck.SOURCE_PHONE

# Commercial Version
http://www.myflashlabs.com/product/unique-device-id-air-native-extension/

![UDID ANE](http://www.myflashlabs.com/wp-content/uploads/2017/04/product_adobe-air-ane-extension-udid-595x738.jpg)

# Tutorials
[How to embed ANEs into **FlashBuilder**, **FlashCC** and **FlashDevelop**](https://www.youtube.com/watch?v=Oubsb_3F3ec&list=PL_mmSjScdnxnSDTMYb1iDX4LemhIJrt1O) 
[https://support.google.com/googleplay/android-developer/answer/6048248?hl=en](https://support.google.com/googleplay/android-developer/answer/6048248?hl=en)   
[https://play.google.com/about/monetization-ads/ads/ad-id/](https://play.google.com/about/monetization-ads/ads/ad-id/)   
[https://apsalar.com/2015/06/all-about-idfa/](https://apsalar.com/2015/06/all-about-idfa/)   

# Changelog
*Apr 26, 2017 - V1.1.0*
* Added support for Apple/Android Advertising ID.
* the ANE is now also dependent on [googlePlayServices_basement.ane](https://github.com/myflashlab/common-dependencies-ANE). ```<extensionID>com.myflashlab.air.extensions.dependency.googlePlayServices.basement</extensionID>```
* You need to add ```<meta-data android:name="com.google.android.gms.version" android:value="@integer/google_play_services_version" />``` to your manifest.

*Apr 09, 2017 - V1.0.0*
* beginning of the journey!