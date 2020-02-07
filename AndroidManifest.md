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

### android:allowClearUserData

 是否允许应用重置用户数据。这些数据包括标志（如用户是否看到了介绍性提示）以及用户可自定义的设置和偏好设置。此属性的默认值为 `true`。只有属于系统映像的应用才能明确声明此属性。第三方应用不能在其清单文件中包含此属性。

### android:backupAgent

实现应用的备份代理的类的名称，它是 `BackupAgent` 的子类。属性值应该是一个完全限定类名（如 `"com.example.project.MyBackupAgent"`）。不过，作为一种简写形式，如果名称的第一个字符是句点（例如 `".MyBackupAgent"`），则会将其附加到 `` 元素中指定的软件包名称。

没有默认值。必须指定相应名称。

### android:backupInForeground

表示即使此应用处于前台等效状态，也可以对其执行[自动备份](https://developer.android.google.cn/guide/topics/data/autobackup.html)操作。系统会在自动备份操作期间关闭应用，因此使用此属性时应格外小心。将此标志设为 true 会影响应用处于活动状态时的行为。

默认值为 `false`，这表示当应用在前台运行时（如正在通过处于 `startForeground()` 状态的服务播放音乐的音乐应用），操作系统会避免对其进行备份。

### android:icon

整个应用的图标，以及每个应用组件的默认图标。

### android:isGame

应用是否为游戏。系统可以将分类为游戏的应用归入一组，或者将它们与其他应用分开显示。

默认值为 `false`。

### android:label

整个应用的用户可读标签，以及每个应用组件的默认标签

### android:logo

整个应用的徽标，以及 Activity 的默认徽标。

### android:supportsRtl

声明您的应用是否愿意支持从右到左 (RTL) 布局。

### android:taskAffinity

一个粘性名称

### android:theme

对样式资源的引用，用于为应用中的所有 Activity 定义默认主题背景。各个 Activity 可以通过设置自己的 `theme` 属性来替换默认值。

# activity

**语法：**

```
<activity android:allowEmbedded=["true" | "false"]
          android:allowTaskReparenting=["true" | "false"]
          android:alwaysRetainTaskState=["true" | "false"]
          android:autoRemoveFromRecents=["true" | "false"]
          android:banner="drawable resource"
          android:clearTaskOnLaunch=["true" | "false"]
          android:colorMode=[ "hdr" | "wideColorGamut"]
          android:configChanges=["mcc", "mnc", "locale",
                                 "touchscreen", "keyboard", "keyboardHidden",
                                 "navigation", "screenLayout", "fontScale",
                                 "uiMode", "orientation", "density",
                                 "screenSize", "smallestScreenSize"]
          android:directBootAware=["true" | "false"]
          android:documentLaunchMode=["intoExisting" | "always" |
                                  "none" | "never"]
          android:enabled=["true" | "false"]
          android:excludeFromRecents=["true" | "false"]
          android:exported=["true" | "false"]
          android:finishOnTaskLaunch=["true" | "false"]
          android:hardwareAccelerated=["true" | "false"]
          android:icon="drawable resource"
          android:immersive=["true" | "false"]
          android:label="string resource"
          android:launchMode=["standard" | "singleTop" |
                              "singleTask" | "singleInstance"]
          android:lockTaskMode=["normal" | "never" |
                              "if_whitelisted" | "always"]
          android:maxRecents="integer"
          android:maxAspectRatio="float"
          android:multiprocess=["true" | "false"]
          android:name="string"
          android:noHistory=["true" | "false"]  
          android:parentActivityName="string" 
          android:persistableMode=["persistRootOnly" | 
                                   "persistAcrossReboots" | "persistNever"]
          android:permission="string"
          android:process="string"
          android:relinquishTaskIdentity=["true" | "false"]
          android:resizeableActivity=["true" | "false"]
          android:screenOrientation=["unspecified" | "behind" |
                                     "landscape" | "portrait" |
                                     "reverseLandscape" | "reversePortrait" |
                                     "sensorLandscape" | "sensorPortrait" |
                                     "userLandscape" | "userPortrait" |
                                     "sensor" | "fullSensor" | "nosensor" |
                                     "user" | "fullUser" | "locked"]
          android:showForAllUsers=["true" | "false"]
          android:stateNotNeeded=["true" | "false"]
          android:supportsPictureInPicture=["true" | "false"]
          android:taskAffinity="string"
          android:theme="resource or theme"
          android:uiOptions=["none" | "splitActionBarWhenNarrow"]
          android:windowSoftInputMode=["stateUnspecified",
                                       "stateUnchanged", "stateHidden",
                                       "stateAlwaysHidden", "stateVisible",
                                       "stateAlwaysVisible", "adjustUnspecified",
                                       "adjustResize", "adjustPan"] >   
    . . .
</activity>
```

声明实现应用部分可视化界面的 Activity，系统不会识别和运行任何未进行声明的 Activity

包含在application元素中，可包含layout/meta-data/intent-filter元素

**属性：**

android:allowEmbedded/android:allowTaskReparenting/android:alwaysRetainTaskState/

  ### android:name

实现 Activity 的类的名称    

# activity-alias

# action

android.intent.action.AIRPLANE_MODE

android.intent.action.ALL_APPS

android.intent.action.ANSWER

android.intent.action.APPLICATION_PREFERENCES

android.intent.action.APPLICATION_RESTRICTIONS_CHANGED

android.intent.action.APP_ERROR

android.intent.action.ASSIST

android.intent.action.ATTACH_DATA

android.intent.action.BATTERY_CHANGED

android.intent.action.BATTERY_LOW

android.intent.action.BATTERY_OKAY

android.intent.action.BOOT_COMPLETED

android.intent.action.BUG_REPORT

android.intent.action.CALL

android.intent.action.CALL_BUTTON

android.intent.action.CAMERA_BUTTON

android.intent.action.CARRIER_SETUP

android.intent.action.CHOOSER

android.intent.action.CLOSE_SYSTEM_DIALOGS

android.intent.action.CONFIGURATION_CHANGED

android.intent.action.CREATE_DOCUMENT

android.intent.action.CREATE_SHORTCUT

android.intent.action.DATE_CHANGED

android.intent.action.VIEW

android.intent.action.DEFINE

android.intent.action.DELETE

android.intent.action.DEVICE_STORAGE_LOW

android.intent.action.DEVICE_STORAGE_OK

android.intent.action.DIAL

android.intent.action.DOCK_EVENT

android.intent.action.DREAMING_STARTED

android.intent.action.DREAMING_STOPPED

android.intent.action.EDIT

android.intent.action.EXTERNAL_APPLICATIONS_AVAILABLE

android.intent.action.EXTERNAL_APPLICATIONS_UNAVAILABLE

android.intent.action.FACTORY_TEST

android.intent.action.GET_CONTENT

android.intent.action.GET_RESTRICTION_ENTRIES

android.intent.action.GTALK_CONNECTED

android.intent.action.GTALK_DISCONNECTED

android.intent.action.HEADSET_PLUG

android.intent.action.INPUT_METHOD_CHANGED

android.intent.action.INSERT

android.intent.action.INSERT_OR_EDIT

android.intent.action.INSTALL_FAILURE

android.intent.action.INSTALL_PACKAGE

android.intent.action.LOCALE_CHANGED

android.intent.action.LOCKED_BOOT_COMPLETED

android.intent.action.MAIN

android.intent.action.MANAGED_PROFILE_ADDED

android.intent.action.MANAGED_PROFILE_AVAILABLE

android.intent.action.MANAGED_PROFILE_REMOVED

android.intent.action.MANAGED_PROFILE_UNAVAILABLE

android.intent.action.MANAGE_NETWORK_USAGE

android.intent.action.MANAGE_PACKAGE_STORAGE

android.intent.action.MEDIA_BAD_REMOVAL

android.intent.action.MEDIA_BUTTON

android.intent.action.MEDIA_CHECKING

android.intent.action.MEDIA_EJECT

android.intent.action.MEDIA_MOUNTED

android.intent.action.MEDIA_NOFS

android.intent.action.MEDIA_REMOVED

android.intent.action.MEDIA_SCANNER_FINISHED

android.intent.action.MEDIA_SCANNER_SCAN_FILE

android.intent.action.MEDIA_SCANNER_STARTED

android.intent.action.MEDIA_SHARED

android.intent.action.MEDIA_UNMOUNTABLE

android.intent.action.MEDIA_UNMOUNTED

android.intent.action.MY_PACKAGE_REPLACED

android.intent.action.MY_PACKAGE_SUSPENDED

android.intent.action.MY_PACKAGE_UNSUSPENDED

android.intent.action.NEW_OUTGOING_CALL

android.intent.action.OPEN_DOCUMENT

android.intent.action.OPEN_DOCUMENT_TREE

android.intent.action.PACKAGES_SUSPENDED

android.intent.action.PACKAGES_UNSUSPENDED

android.intent.action.PACKAGE_ADDED

android.intent.action.PACKAGE_CHANGED

android.intent.action.PACKAGE_DATA_CLEARED

android.intent.action.PACKAGE_FIRST_LAUNCH

android.intent.action.PACKAGE_FULLY_REMOVE

android.intent.action.PACKAGE_INSTALL

android.intent.action.PACKAGE_NEEDS_VERIFICATION

android.intent.action.PACKAGE_REMOVED

android.intent.action.PACKAGE_REPLACED

android.intent.action.PACKAGE_RESTARTED

android.intent.action.PACKAGE_VERIFIED

android.intent.action.PASTE

android.intent.action.PICK

android.intent.action.PICK_ACTIVITY

android.intent.action.ACTION_POWER_CONNECTED

android.intent.action.ACTION_POWER_DISCONNECTED

android.intent.action.POWER_USAGE_SUMMARY

android.intent.action.PROCESS_TEXT

android.intent.action.PROVIDER_CHANGED

android.intent.action.QUICK_CLOCK

android.intent.action.QUICK_VIEW

android.intent.action.REBOOT

android.intent.action.RUN

android.intent.action.SCREEN_OFF

android.intent.action.SCREEN_ON

android.intent.action.SEARCH

android.intent.action.SEARCH_LONG_PRESS

android.intent.action.SEND

android.intent.action.SENDTO

android.intent.action.SEND_MULTIPLE

android.intent.action.SET_WALLPAPER

android.intent.action.SHOW_APP_INFO

android.intent.action.ACTION_SHUTDOWN

android.intent.action.SYNC

android.intent.action.SYSTEM_TUTORIAL

android.intent.action.TIMEZONE_CHANGED

android.intent.action.TIME_SET

android.intent.action.TIME_TICK

android.intent.action.TRANSLATE

android.intent.action.UID_REMOVED

android.intent.action.USER_BACKGROUND

android.intent.action.USER_FOREGROUND

android.intent.action.USER_INITIALIZE

android.intent.action.USER_PRESENT

android.intent.action.USER_UNLOCKED

android.intent.action.VIEW

android.intent.action.VIEW_LOCUS

android.intent.action.VIEW_PERMISSION_USAGE

android.intent.action.VOICE_COMMAND

android.intent.action.WEB_SEARCH

android.intent.category.ALTERNATIVE

android.intent.category.APP_BROWSER

android.intent.category.APP_CALCULATOR

android.intent.category.APP_CALENDAR

android.intent.category.APP_CONTACTS

android.intent.category.APP_EMAIL

android.intent.category.APP_FILES

android.intent.category.APP_GALLERY

android.intent.category.APP_MAPS



# category

```
<category android:name="string" />
```

向 Intent 过滤器添加类别名称



# compatible-screens

# data

# grant-uri-permission

# instrumentation

# intent-filter

**语法：**

```xml
<intent-filter android:icon="drawable resource"
                   android:label="string resource"
                   android:priority="integer" >
        . . .
    </intent-filter>
```

指定 Activity、服务或广播接收器可以响应的 Intent 类型.Intent 过滤器声明其父组件的功能 - Activity 或服务可执行哪些操作，以及接收器可处理哪些类型的广播。它让组件可以接收所通告类型的 Intent，同时过滤掉对组件没有意义的 Intent。

包含在activity/activity-alias/service/receiver元素中，必须包含action，可以包含category/data

**属性：**

### android:icon

一个表示父 Activity、服务或广播接收器的图标，在将该组件以具备过滤器所描述功能的形式呈现给用户时显示。

必须将此属性设为对包含图片定义的可绘制资源的引用。默认值为父组件的  icon 属性设置的图标。如果父组件未指定图标，则默认值为 application元素设置的图标。



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