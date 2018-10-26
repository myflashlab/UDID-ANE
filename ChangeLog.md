Unique Device ID Air Native Extension (Android + iOS)

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

*Dec 15, 2017 - V1.1.3*
* optimized for [ANE-LAB sofwate](https://github.com/myflashlab/ANE-LAB).

*Aug 15, 2017 - V1.1.1*
* fixed a bug check on devices with no googlePlayServices
* added intelliJ demo project

*Apr 26, 2017 - V1.1.0*
* Added support for Apple/Android Advertising ID.
* the ANE is now also dependent on [googlePlayServices_basement.ane](https://github.com/myflashlab/common-dependencies-ANE). ```<extensionID>com.myflashlab.air.extensions.dependency.googlePlayServices.basement</extensionID>```
* You need to add ```<meta-data android:name="com.google.android.gms.version" android:value="@integer/google_play_services_version" />``` to your manifest.

*Apr 09, 2017 - V1.0.0*
* beginning of the journey!