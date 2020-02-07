# Android Manifest

# manifest

语法：

```
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
              package="string"
             android:allowBackup="true"
       		 android:icon="@mipmap/ic_launcher"
      	 	 android:label="@string/app_name"
           	 android:roundIcon="@mipmap/ic_launcher_round"
        	 android:supportsRtl="true"
        	 android:theme="@style/AppTheme">
              android:sharedUserId="string"
              android:sharedUserLabel="string resource" 
              android:versionCode="integer"
              android:versionName="string"
              android:installLocation=["auto" | "internalOnly" | "preferExternal"] >
        . . .
    </manifest>
```

androidmanifest.xml根元素，必须包含application元素，可包含compatible-screens,instrumentation,permission,permission-group,permission-tree,supports-gl-texture,supports-screens,uses-configuration,uses-feature,uses-permission,uses-permission-sdk-23,uses-sdk元素.

必须设置xmlns:android，package属性。



# application

# activity

# activity-alias

# action

# category

# compatible-screens

# data

# grant-uri-permission

# instrumentation

# intent-filter

# meta-data

# path-permission

# permission

# permission-group

# perimission-tree

# probider

# receiver

# servicer

# supports-gl-texture

# supports-screens

# uses-configuration

# uses-feature

# uses-library

# uses-perimission

# uses-perimission-sdk-23

# uses-sdk