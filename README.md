# Unique Device ID ANE V1.1.5 (Android+iOS)
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

[Download demo ANE](https://github.com/myflashlab/UDID-ANE/tree/master/AIR/lib)

# AIR Usage
For the complete AS3 code usage, see the [demo project here](https://github.com/myflashlab/UDID-ANE/blob/master/AIR/src/Main.as).

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
		<uses-sdk android:targetSdkVersion="26"/>
		<uses-sdk android:minSdkVersion="15"/>
		
		<!--Required if you are using TelephonyManager API-->
		<uses-permission android:name="android.permission.READ_PHONE_STATE" />
		
		<!--Required if you want to use the Android Advert ID-->
		<meta-data android:name="com.google.android.gms.version" android:value="@integer/google_play_services_version" />



<!--
Embedding the ANE:
-->
<extensions>
	<extensionID>com.myflashlab.air.extensions.udid</extensionID>
	
	<!-- dependency ANEs https://github.com/myflashlab/common-dependencies-ANE -->
	<extensionID>com.myflashlab.air.extensions.dependency.androidSupport.arch</extensionID>
	<extensionID>com.myflashlab.air.extensions.dependency.androidSupport.core</extensionID>
	<extensionID>com.myflashlab.air.extensions.dependency.androidSupport.v4</extensionID>
    <extensionID>com.myflashlab.air.extensions.dependency.androidSupport.customtabs</extensionID>
    <extensionID>com.myflashlab.air.extensions.dependency.googlePlayServices.basement</extensionID>
    <extensionID>com.myflashlab.air.extensions.dependency.googlePlayServices.ads</extensionID>
    <extensionID>com.myflashlab.air.extensions.dependency.googlePlayServices.ads.lite</extensionID>
    <extensionID>com.myflashlab.air.extensions.dependency.googlePlayServices.gass</extensionID>
    <extensionID>com.myflashlab.air.extensions.dependency.overrideAir</extensionID>
	
	<!-- Required if you are using TelephonyManager API-->
	<extensionID>com.myflashlab.air.extensions.permissionCheck</extensionID>
  </extensions>
```

# Requirements
* Android SDK 15+
* iOS 8.0+
* AIR SDK 30+

# Permissions
Below are the list of Permissions this ANE might require. Check out the demo project available at this repository to see how we have used the [PermissionCheck ANE](http://www.myflashlabs.com/product/native-access-permission-check-settings-menu-air-native-extension/) to ask for the permissions.

Necessary | Optional
--------------------------- | ---------------------------
. | [SOURCE_PHONE](https://myflashlab.github.io/asdoc/com/myflashlab/air/extensions/nativePermissions/PermissionCheck.html#SOURCE_PHONE)

# Commercial Version
http://www.myflashlabs.com/product/unique-device-id-air-native-extension/

![UDID ANE](https://www.myflashlabs.com/wp-content/uploads/2017/04/product_adobe-air-ane-extension-udid-595x738.jpg)

# Tutorials
[How to embed ANEs into **FlashBuilder**, **FlashCC** and **FlashDevelop**](https://www.youtube.com/watch?v=Oubsb_3F3ec&list=PL_mmSjScdnxnSDTMYb1iDX4LemhIJrt1O) 
[https://support.google.com/googleplay/android-developer/answer/6048248?hl=en](https://support.google.com/googleplay/android-developer/answer/6048248?hl=en)   
[https://play.google.com/about/monetization-ads/ads/ad-id/](https://play.google.com/about/monetization-ads/ads/ad-id/)   
[https://apsalar.com/2015/06/all-about-idfa/](https://apsalar.com/2015/06/all-about-idfa/)   

# Changelog
*Nov 18, 2018 - V1.1.5*
* Works with OverrideAir ANE V5.6.1 or higher
* Works with ANELAB V1.1.26 or higher

*Sep 23, 2018 - V1.1.4*
* Removed androidSupport dependency and added the following:
    * androidSupport-arch.ane
    * androidSupport-core.ane
    * androidSupport-customtabs.ane
    * androidSupport-v4.ane
    * googlePlayServices_ads.anev
    * googlePlayServices_adsLite.ane
    * googlePlayServices_basement.ane
    * googlePlayServices_gass.ane

*Aug 15, 2017 - V1.1.3*
* optimized for [ANE-LAB sofwate](https://github.com/myflashlab/ANE-LAB).

*Aug 15, 2017 - V1.1.1*
* fixed a bug check on devices with no googlePlayServices

*Apr 26, 2017 - V1.1.0*
* Added support for Apple/Android Advertising ID.
* the ANE is now also dependent on [googlePlayServices_basement.ane](https://github.com/myflashlab/common-dependencies-ANE). ```<extensionID>com.myflashlab.air.extensions.dependency.googlePlayServices.basement</extensionID>```
* You need to add ```<meta-data android:name="com.google.android.gms.version" android:value="@integer/google_play_services_version" />``` to your manifest.

*Apr 09, 2017 - V1.0.0*
* beginning of the journey!