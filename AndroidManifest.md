# Android Manifest



# manifest

**语法：**

```
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
              package="string"
              android:targetSandboxVersion="1"
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

### xmlns:android

定义android命名空间，属性值始终设置为“http://schemas.android.com/apk/res/android”

### package

* 用作R.java的命名空间
* 用作androidmanifest.xml文件中相关类的命名空间

### android:targetSandboxVersion

沙盒版本号越高越安全，一般为1，可设为2，免安装应用必须设置为2

### android:versionCode

内部版本号，值必须是整数，数值越大版本越新，

### android:versionName

向用户显示的版本号，值可以是字符串或字符串资源的引用。

### android:installLocation

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

应用的声明，此元素包含用于声明每个应用组件的子元素，并且具有会影响所有组件的属性，其中许多属性（如 `icon`、`label`、`permission`、`process`、`taskAffinity` 和 `allowTaskReparenting`）会为组件元素的相应属性设置默认值。其他属性（如 `debuggable`、`enabled`、`description` 和 `allowClearUserData`）则为整个应用设置值，并且不能被组件替换。

包含在manifest元素中，可包含activity/activity-alias/meta-data/service/receiver/provider/uses-library元素

---

**属性：**

android:allowTaskReparenting/android:allowBackup/android:allowClearUserData/android:backupAgent/android:backupInForeground/android:banner/android:debuggable/android:description/android:directBootAware/android:enabled/android:extracNativeLibs/android:fullBackupContent/android:hasCode/android:harwareAccelerated/android:icon/android:isGame/android:killAfterRestore/android:largeHeap/android:label/android:logo/android:manageSpaceActivity/android:name/android:networkSecurityConfig/android:permission/android:persistent/android:process/android:restoreAnyVersion/android:requireAccountType/android:restrictedAccountType/android:supportsRtl/android:taskAffinity/android:testOnly/android:theme/android:uiOptions/android:usesCleartextTraffic/android:vmSafeMode/

### android:allowTaskReparenting

应用定义的 Activity 是否可以从启动它们的任务移至对其具有粘性的任务（当下次将该任务置于前台时）。如果它们可以移动，则设为 `"true"`；如果它们必须一直与启动它们的任务在一起，则设为 `"false"`。默认值为 `"false"`。

### android:allowBackup

是否允许应用参与备份和恢复基础架构。如果将此属性设为 false，则永远不会为该应用执行备份或恢复，即使是采用全系统备份方法也不例外（这种备份方法通常会通过 adb 保存所有应用数据）。此属性的默认值为 true。

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