# cordova-plugin-debuggable-webview

Within our project we have a mobile application that is making use of Ionic and Cordova. Whenever we want to test a new release, we publish the apk to an internal test track in the Playstore, from where our testers can download this apk. Because we want to be able to do some debugging if necessary during this stage, we wanted an option to build an apk that still allowed debugging. But we also wanted to be able to turn off the possibillity of debugging without having to remove the plugin. For that reason we have written this plugin.

## Installation

Use the following cordova command to install the plugin: `cordova plugin add git+https://github.com/JouriFledderman/cordova-plugin-debuggable-webview.git`

## Usage

Add the following codeblock to your config.xml within the `<platform name="android">` element:

```
<config-file parent="/manifest/application" target="AndroidManifest.xml">
  <meta-data android:name="WebViewDebug" android:value="true" />
</config-file>
```

You should also add the Android namespace to config.xml by adding the `xmlns:android="http://schemas.android.com/apk/res/android"` attribute to the root `<widget>` tag if it's not already present.

When you want to disable debugging in your apk (for example when you create a production release), make sure you set the `android:value` for the `WebViewDebug` property to false.
