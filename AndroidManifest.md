# Android Manifest



# manifest

**语法：**

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

androidmanifest.xml根元素，必须包含application元素，可包含compatible-screens/instrumentation/permission/permission-group/permission-tree/supports-gl-texture/supports-screens/uses-configuration/uses-feature/uses-permission/uses-permission-sdk-23/uses-sdk元素.

必须设置xmlns:android，package属性。

---

**属性：**

xmlns:android/package/android:targetSandboxVersion/android:versionCode/android:versionName/android:installLocation/

---

**xmlns:android**

定义android命名空间，属性值始终设置为“http://schemas.android.com/apk/res/android”

---

**package**

* 用作R.java的命名空间
* 用作androidmanifest.xml文件中相关类的命名空间

**android:targetSandboxVersion**

沙盒版本号越高越安全，一般为1，可设为2，免安装应用必须设置为2

**android:versionCode**

内部版本号，值必须是整数，数值越大版本越新，

**android:versionName**

向用户显示的版本号，值可以是字符串或字符串资源的引用。

**android:installLocation**

应用默认安装位置，值为inernalOnly/auto/perferExternal

安装应用后，在设置内可以将应用移到外部存储空间或内部存储空间

* internalOnly:应用必须安装在内部存储空间，如果内部存储空间满，系统将不会安装应用，该值为installLocation默认值。且系统不允许移至外部存储空间。
* auto:默认安装在内部存储空间，若内部存储空间满，系统将安装在外部存储空间，
* perferExternal:优先安装在外部存储空间，若外部存储空间满，将安装在内部存储空间。

# application

**语法：**

```xml
<application android:allowTaskReparenting=["true" | "false"]
                 android:allowBackup=["true" | "false"]
                 android:allowClearUserData=["true" | "false"]
                 android:backupAgent="string"
                 android:backupInForeground=["true" | "false"]
                 android:banner="drawable resource"
                 android:debuggable=["true" | "false"]
                 android:description="string resource"
                 android:directBootAware=["true" | "false"]
                 android:enabled=["true" | "false"]
                 android:extractNativeLibs=["true" | "false"]
                 android:fullBackupContent="string"
                 android:fullBackupOnly=["true" | "false"]
                 android:hasCode=["true" | "false"]
                 android:hardwareAccelerated=["true" | "false"]
                 android:icon="drawable resource"
                 android:isGame=["true" | "false"]
                 android:killAfterRestore=["true" | "false"]
                 android:largeHeap=["true" | "false"]
                 android:label="string resource"
                 android:logo="drawable resource"
                 android:manageSpaceActivity="string"
                 android:name="string"
                 android:networkSecurityConfig="xml resource"
                 android:permission="string"
                 android:persistent=["true" | "false"]
                 android:process="string"
                 android:restoreAnyVersion=["true" | "false"]
                 android:requiredAccountType="string"
                 android:resizeableActivity=["true" | "false"]
                 android:restrictedAccountType="string"
                 android:supportsRtl=["true" | "false"]
                 android:taskAffinity="string"
                 android:testOnly=["true" | "false"]
                 android:theme="resource or theme"
                 android:uiOptions=["none" | "splitActionBarWhenNarrow"]
                 android:usesCleartextTraffic=["true" | "false"]
                 android:vmSafeMode=["true" | "false"] >
        . . .
    </application>
```

包含与manifest元素中，可包含activity/activity-alias/meta-data/service/receiver/provider/uses-library

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