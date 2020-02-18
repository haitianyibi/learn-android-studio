# Android Manifest

一个应用里只有一个Manifest文件，且必须使用此名称，新建new->other->androidmanifest文件，可以创建不同的文件名的manifest，但是可以有三种不同的manifest文件，main/debug/release

清单文件会向 Android 构建工具、Android 操作系统和 Google Play 描述应用的基本信息。

# 一、manifest

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

### 1.xmlns:android

定义android命名空间，属性值始终设置为“http://schemas.android.com/apk/res/android”

### 2.package

* 用作R.java的命名空间
* 用作androidmanifest.xml文件中相关类的命名空间（相对地址）
* APK 编译完成后，`package` 属性还可表示应用的通用唯一应用 ID。 当构建工具根据 `package` 名称执行上述任务后，它们会将 `package` 值替换为项目 `build.gradle` 文件（用于 Android Studio 项目）中赋予 `applicationId` 属性的值。 `package` 属性的这一最终值必须是通用唯一值，因为这是能确保在系统和 Google Play 中识别应用的唯一方式。

### 3.android:targetSandboxVersion

沙盒版本号越高越安全，一般为1，可设为2，免安装应用必须设置为2

### 4.android:versionCode

内部版本号，值必须是整数，数值越大版本越新，

### 5.android:versionName

向用户显示的版本号，值可以是字符串或字符串资源的引用。

### 6.android:installLocation

应用默认安装位置，值为inernalOnly/auto/perferExternal

安装应用后，在设置内可以将应用移到外部存储空间或内部存储空间

* internalOnly:应用必须安装在内部存储空间，如果内部存储空间满，系统将不会安装应用，该值为installLocation默认值。且系统不允许移至外部存储空间。
* auto:默认安装在内部存储空间，若内部存储空间满，系统将安装在外部存储空间，
* perferExternal:优先安装在外部存储空间，若外部存储空间满，将安装在内部存储空间。

# 二、application

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

### 1.android:allowTaskReparenting

应用定义的 Activity 是否可以从启动它们的任务移至对其具有粘性的任务（当下次将该任务置于前台时）。如果它们可以移动，则设为 `"true"`；如果它们必须一直与启动它们的任务在一起，则设为 `"false"`。默认值为 `"false"`。

### 2.android:allowBackup

是否允许应用参与备份和恢复基础架构。如果将此属性设为 false，则永远不会为该应用执行备份或恢复，即使是采用全系统备份方法也不例外（这种备份方法通常会通过 adb 保存所有应用数据）。此属性的默认值为 true。

### 3.android:allowClearUserData

 是否允许应用重置用户数据。这些数据包括标志（如用户是否看到了介绍性提示）以及用户可自定义的设置和偏好设置。此属性的默认值为 `true`。只有属于系统映像的应用才能明确声明此属性。第三方应用不能在其清单文件中包含此属性。

### 4.android:backupAgent

实现应用的备份代理的类的名称，它是 `BackupAgent` 的子类。属性值应该是一个完全限定类名（如 `"com.example.project.MyBackupAgent"`）。不过，作为一种简写形式，如果名称的第一个字符是句点（例如 `".MyBackupAgent"`），则会将其附加到 `` 元素中指定的软件包名称。

没有默认值。必须指定相应名称。

### 5.android:backupInForeground

表示即使此应用处于前台等效状态，也可以对其执行[自动备份](https://developer.android.google.cn/guide/topics/data/autobackup.html)操作。系统会在自动备份操作期间关闭应用，因此使用此属性时应格外小心。将此标志设为 true 会影响应用处于活动状态时的行为。

默认值为 `false`，这表示当应用在前台运行时（如正在通过处于 `startForeground()` 状态的服务播放音乐的音乐应用），操作系统会避免对其进行备份。

### 6.android:icon

整个应用的图标，以及每个应用组件的默认图标。

### 7.android:isGame

应用是否为游戏。系统可以将分类为游戏的应用归入一组，或者将它们与其他应用分开显示。

默认值为 `false`。

### 8.android:label

整个应用的用户可读标签，以及每个应用组件的默认标签

### 9.android:logo

整个应用的徽标，以及 Activity 的默认徽标。

### 10.android:supportsRtl

声明您的应用是否愿意支持从右到左 (RTL) 布局。

### 11.android:taskAffinity

一个粘性名称

### 12.android:theme

对样式资源的引用，用于为应用中的所有 Activity 定义默认主题背景。各个 Activity 可以通过设置自己的 `theme` 属性来替换默认值。

### 13.android:banner

### 14.android:debuggable

### 15.android:description

### 16.android:directBootAware

### 17.android:enabled

### 18.android:extractNativeLibs

### 19.android:fullBackupContent

### 20.android:fullBackupOnly

### 21.android:hasCode

### 22.android:hardwareAccelerated

### 23.android:killAfterRestore

### 24.android:largeHeap

### 25.android:manageSpaceActivity

### 26.android:networkSecurityConfig

### 27.android:permission

### 28.android:persistent

### 29.android:process

### 30.android:restoreAnyVersion

### 31.android:requiredAccountType

### 32.android:restrictedAccountType

### 33.android:uiOptions

### 34.android:usesCleartextTraffic

### 35.   android:vmSafeMode

## uses-library

### android:name

### android:required

## activity

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

  ### 1.android:name

实现 Activity 的类的名称    

### 2.android:parentActivityName

```
android:parentActivityName=".MainActivity"
```

设置父activity,提供向上导航按钮，

### 3.android:allowEmbedded

### 4.android:allowTaskReparenting

### 5.android:alwaysRetainTaskState

### 6.android:autoRemoveFromRecents

### 7.android:banner

### 8.android:clearTaskOnLaunch

### 9.android:colorMode

### 10.android:configChanges

### 11.android:directBootAware

### 12.android:documentLaunchMode

### 13.android:enabled

### 14.android:excludeFromRecents

### 15.android:exported

限制 Activity 向其他应用公开

### 16.android:finishOnTaskLaunch

### 17.android:hardwareAccelerated

### 18.android:icon

### 19.android:immersive

### 20.android:label

### 21.android:launchMode

### 22.android:lockTaskMode

### 23.android:maxRecents

### 24.android:maxAspectRatio

### 25.android:multiprocess

### 26.android:name

### 27.android:noHistory

### 28.android:parentActivityName

以确定当用户按下操作栏中的“向上”按钮时应该启动哪一个 Activity

### 29.android:persistableMode

### 30.android:permission

### 31.android:process

### 32.android:relinquishTaskIdentity

### 33.android:screenOrientation

### 34.android:showForAllUsers

### 35.android:stateNotNeeded

### 36.supportsPictureInPicture

### 37.android:taskAffinity

### 38.android:theme

### 39.android:uiOptions

### 40.android:windowSoftInputMode

### intent-filter

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

#### 1.android:icon

一个表示父 Activity、服务或广播接收器的图标，在将该组件以具备过滤器所描述功能的形式呈现给用户时显示。

必须将此属性设为对包含图片定义的可绘制资源的引用。默认值为父组件的  icon 属性设置的图标。如果父组件未指定图标，则默认值为 application元素设置的图标。

#### 2.android:label

父组件的用户可读标签。将相应组件以具备过滤器所描述功能的形式呈现给用户时，将使用此标签

#### 3.android:priority

值必须是一个整数，如“`100`”。数值越高，优先级也就越高。默认值为 0。

#### 4.android:order

当多个过滤器匹配时应按什么顺序处理过滤器

`order` 与 `priority` 的不同之处在于，`priority` 在多个应用间应用，而 可消除单个应用中多个匹配的过滤器的歧义。

值必须是一个整数，如“`100`”。数值越高，匹配顺序越靠前。默认值为 `0`。

#### action

##### android:name

向 Intent 过滤器添加操作`` 元素必须包含一个或多个 `` 元素。如果 Intent 过滤器中没有 action元素，则过滤器不接受任何 Intent对象

标准操作在 `Intent` 类中定义为 ACTION_string常量

对于您定义的操作，最好将应用的软件包名称用作前缀，以确保唯一性。例如，可按如下方式指定 `TRANSMOGRIFY` 操作：

```xml
<action android:name="com.example.project.TRANSMOGRIFY" />
```

标准操作在 `Intent` 类中定义为 ACTION_string 常量

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

#### category

```
<category android:name="string" />
```

向 Intent 过滤器添加类别名称

##### 1.android:name

标准类别在 `Intent` 类中定义为 CATEGORY_name 常量

#### meta-data

#### data

<scheme>://<host>:<port>[<path>|<pathPrefix>|<pathPattern>]

- 如果没有为 Intent 过滤器指定 `scheme`，则系统会忽略其他所有 URI 属性。
- 如果没有为过滤器指定 `host`，则系统会忽略 `port` 属性以及所有路径属性。



```
<intent-filter . . . >
        <data android:scheme="something" android:host="project.example.com" />
        . . .
    </intent-filter>
```

```
<intent-filter . . . >
        <data android:scheme="something" />
        <data android:host="project.example.com" />
        . . .
    </intent-filter>
```

##### 1.android:scheme

指定的架构应不带尾随冒号（例如，应指定 `http`，而不是 `http:`）

如果为过滤器设置了数据类型（`mimeType` 属性），但未设置架构，则采用 `content:` 和 `file:` 架构。

##### 2.android:host

主机 `*.google.com` 匹配 `www.google.com`、`.google.com` 和 `developer.google.com`。

星号必须是主机属性的第一个字符。例如，主机 `google.co.*` 无效，因为星号通配符不是第一个字符。

##### 3.android:port

URI 授权方的端口部分

##### 4.android:path

URI 的路径部分，必须以 / 开头

可以包含以下通配符：

- 星号（“`*`”）匹配出现零次到多次的紧邻前面的字符的一个序列。
- 句点后跟星号（“`.*`”）匹配零个到多个字符的任意序列。

##### 5.android:pathPrefix

##### 6.android:pathPattern

由于在从 XML 读取字符串时（在将其解析为模式之前）将“`\`”用作转义字符，因此您需要进行双重转义。例如，字面量“`*`”将编写为“`\\*`”，字面量“”将编写为“`\\\\`”。这基本上与采用 Java 代码构造字符串时需要编写的内容一样。

##### 7.android:mimeType

MIME 媒体类型

## activity-alias

使用场景 - 动态修改应用在桌面上的图标

给整个应用的入口 Activity 添加一个 <activity-alias> 标签，并设置预先设计好的替代桌面图标和应用名称.

<activity-alias>一般情况下默认要设置为android:enabled="false"， 当赶上节假日需要使用预先放置的特定图标时， 通过消息推送执行java代码, 动态设置<activity-alias>的enable属性为true， 这样就实现了替换图标的目的.

### 1.android:enabled

### 2.android:exported

### 3.android:icon

### 4.android:label

### 5.android:permission

 ### 6.android:targetActivity

### intent-filter

### meta-data

## probider

声明内容提供程序组件，内容提供程序是 `ContentProvider` 的子类

### 1.android:authorities

一个或多个 URI 授权方的列表，这些 URI 授权方用于标识内容提供程序提供的数据

必须至少指定一个授权方。

### 2.android:enabled

系统是否可以实例化内容提供程序

### 3.android:directBootAware

内容提供程序是否可感知直接启动 (direct-boot)；即，它是否可以在用户解锁设备之前运行。

### 4.android:exported

内容提供程序是否可供其他应用使用：

### 5.android:grantUriPermissions

是否可以向一般无权访问内容提供程序的数据的组件授予访问这些数据的权限，

### 6.android:icon

一个表示内容提供程序的图标。

### 7.android:initOrder

应按什么顺序实例化内容提供程序，这是相对于由同一进程托管的其他内容提供程序的顺序。当内容提供程序之间存在依赖关系时，为每个提供程序设置此属性可确保按这些依赖关系要求的顺序创建这些提供程序。值是一个简单的整数，数值越高，初始化顺序越靠前。

### 8.android:label

所提供内容的用户可读标签

### 9.android:multiprocess

如果应用在多个进程中运行，则此属性决定了是否会创建内容提供程序的多个实例

### 10.android:name

实现内容提供程序的类的名称

### 11.android:permission

客户端为了读取或写入内容提供程序的数据而必须具备的权限的名称

### 12.android:process

一个进程的名称，内容提供程序应在该进程中运行。通常，应用的所有组件都在为应用创建的默认进程中运行。它与应用软件包的名称相同

### 13.android:readPermission

客户端要查询内容提供程序而必须具备的权限。

### 14.android:syncable

由内容提供程序控制的数据是否要与服务器上的数据同步

### 15.android:writePermission

客户端要对由内容提供程序控制的数据进行更改而必须具备的权限。

### grant-uri-permission

#### 1.android:path

#### 2.android:pathPrefix

#### 3.android:pathPattern

- 星号（“`*`”）匹配出现零次到多次的紧邻前面的字符的一个序列。
- 后跟星号的句点（“`.*`”）匹配零个或多个字符的任意序列。

由于在从 XML 读取字符串时（在将其解析为模式之前）将“`\`”用作转义字符，因此您需要进行双重转义：例如，字面量“`*`”将编写为“`\\*`”，字面量“”将编写为“`\\\\`”。这基本上与采用 Java 代码构造字符串时需要编写的内容一样。

### path-permission

定义内容提供程序中特定数据子集的路径和所需权限。您可以多次指定此元素，以提供多个路径。

#### 1.android:path

#### 2.android:pathPrefix

#### 3.android:pathPattern

内容提供程序数据子集的完整 URI 路径，但可以使用以下通配符：

- 星号（“`*`”）。此通配符匹配出现零次到多次的紧邻前面的字符的一个序列。
- 句点后跟星号（“`.*`”）。此通配符匹配零个或多个字符的任意序列。

由于在从 XML 读取字符串时（在将其解析为模式之前）将“`\`”用作转义字符，因此您需要进行双重转义。例如，字面量“`*`”将编写为“`\\*`”，字面量“`\`”将编写为“`\\`”。这基本上与采用 Java 代码构造字符串时需要编写的内容一样。

#### 4.android:permission

客户端要读取或写入内容提供程序的数据而必须具备的权限的名称。您可以使用此属性来方便地设置适用于读取和写入的单项权限。不过，`readPermission` 和 `writePermission` 属性优先于此属性。

#### 5.android:readPermission

客户端要查询内容提供程序而必须具备的权限。

#### 6.android:writePermission

客户端要对由内容提供程序控制的数据进行更改而必须具备的权限。

### meta-data

## receiver

将广播接收器（`BroadcastReceiver` 子类）声明为应用的组件之一

让系统知道广播接收器有两种方法：一种方法是使用此元素在清单文件中声明广播接收器。另一种方法是在代码中动态创建接收器，并使用 Context.registerReceiver() 方法注册接收器

广播接收器过多会影响应用的性能及用户设备的电池续航时间

### 1.android:directBootAware

广播接收器是否可感知直接启动；即，它是否可以在用户解锁设备之前运行。

### 2.android:enabled

系统是否可以实例化广播接收器

### 3.android:exported

广播接收器是否可以接收来自其应用外部来源的消息

### 4.android:icon

表示广播接收器的图标

### 5.android:label

广播接收器的用户可读标签

### 6.android:name

实现广播接收器的类（`BroadcastReceiver` 的子类）的名称

### 7.android:permission

广播方要向广播接收器发送消息而必须具备的权限的名称

### 8.android:process

广播接收器应在其中运行的进程的名称。通常，应用的所有组件都会在为应用创建的默认进程中运行。它的名称与应用软件包的名称相同

### intent-filter

### meta-data

## servicer

将服务（`Service` 子类）声明为应用的一个组件。与 Activity 不同，服务缺少可视化界面。服务用于实现长时间运行的后台操作

### 1.android:description

向用户描述服务的字符串。您应将此标签设置为对字符串资源的引用，以便可以像对界面中的其他字符串那样对其进行本地化

### 2.android:directBootAware

服务是否*支持直接启动*，即其是否可以在用户解锁设备之前运行。

### 3.android:enabled

系统是否可实例化服务

### 4.android:exported

其他应用的组件是否能调用服务或与之交互

### 5.android:foregroundServiceType

阐明服务是满足特定用例要求的前台服务

### 6.android:icon

表示服务的图标

### 7.android:isolatedProcess

如果设置为 true，则此服务将在与系统其余部分隔离的特殊进程下运行

### 8.android:label

可向用户显示的服务名称

### 9.android:name

实现服务的 `Service` 子类的名称

### 10.android:permission

实体启动服务或绑定到服务所必需的权限的名称

### 11.android:process

将运行服务的进程的名称。正常情况下，应用的所有组件都会在为应用创建的默认进程中运行。该名称与应用软件包的名称相同

### intent-filter

### meta-data

## meta-data

可以向父组件提供的其他任意数据项的名称值对。一个组件元素可以包含任意数量的子元素。所有这些子元素的值收集到一个 Bundle对象

普通值通过 `value` 属性指定。不过，要将资源 ID 指定为值，请改为使用 `resource` 属性。例如，以下代码会将 `@string/kangaroo` 资源中存储的任何值分配给“`zoo`”名称：

```xml
<meta-data android:name="zoo" android:value="@string/kangaroo" />
```

另一方面，使用 `resource` 属性会为资源的数字 ID 分配“`zoo`”，而不是资源中存储的值：

```xml
<meta-data android:name="zoo" android:resource="@string/kangaroo" />
```

### 1.android:name

该项的唯一名称。要确保此名称具有唯一性，请使用 Java 样式的命名惯例，例如“`com.example.project.activity.fred`”。

### 2.android:resource

对资源的引用。资源的 ID 是分配给该项的值。可以通过 `Bundle.getInt()` 方法从元数据 Bundle 中检索 ID。

### 3.android:value

| 类型                                                         | Bundle 方法    |
| :----------------------------------------------------------- | :------------- |
| 字符串值，使用双反斜线 (`\\`) 转义字符，例如“`\\n`”和“`\\uxxxxx`”表示 Unicode 字符。 | `getString()`  |
| 整数值，例如“`100`”                                          | `getInt()`     |
| 布尔值，“`true`”或“`false`”                                  | `getBoolean()` |
| 颜色值，格式为“`#rgb`”、“`#argb`”、“`#rrggbb`”或“`#aarrggbb`” | `getInt()`     |
| 浮点值，例如“`1.23`”                                         | `getFloat()`   |

# 三、permission

## 1.android:description

## 2.android:icon

## 3.android:label

## 4.android:name

## 5.android:permissionGroup

## 6.android:protectionLevel



# 四、permission-group

声明相关权限的逻辑分组的名称

## 1.android:description

描述权限组的用户可读文本

## 2.android:icon

表示权限的图标。此属性必须设置为对包含图片定义的可绘制资源的引用。

## 3.android:label

权限组的用户可读名称。为方便起见，您可以在开发应用时将此标签直接设置为原始字符串。 不过，当准备好发布应用时，应将标签设置为对字符串资源的引用，以便可以像界面中的其他字符串一样进行本地化。

## 4.android:name

权限组的名称

# 五、perimission-tree

声明权限树的基名。应用拥有树中所有名称的所有权

如果基名为 `com.example.project.taxes`，则可能会添加如下权限：

```
com.example.project.taxes.CALCULATE
com.example.project.taxes.deductions.MAKE_SOME_UP
com.example.project.taxes.deductions.EXAGGERATE
```

## 1.android:icon

一个表示树中所有权限的图标。必须将此属性设为对包含图片定义的可绘制资源的引用

## 2.android:label

组的用户可读名称。为方便起见，可直接将标签设为原始字符串，以便进行快速粗略的编程。不过，当准备好发布应用时，应将标签设为对字符串资源的引用，以便可以像界面中的其他字符串一样进行本地化。

## 3.android:name

位于权限树底部的名称。它充当树中所有权限名称的前缀

# 六、uses-perimission

## 1.android:name

## 2.android:maxSdkVersion

此权限应授予应用的最高 API 级别

# 七、uses-configuration

指示应用所需的硬件和软件功能

## 1.android:reqFiveWayNav

应用是否需要五向导航控件

## 2.android:reqHardKeyboard

应用是否需要硬件键盘

## 3.android:reqKeyboardType

应用所需的键盘类型

## 4.android:reqNavigation

应用所需的导航设备

## 5.android:reqTouchScreen

应用所需的触摸屏类型

# 八、uses-feature

声明应用使用的单个硬件或软件功能。

## 1.android:name

```xml
<uses-feature android:name="android.hardware.bluetooth" />
<uses-feature android:name="android.hardware.camera" />
```

## 2.android:required

指定应用是否需要声明的功能并且没有该功能便无法正常工作，或者使用该功能只是一种优先选择，没有它仍然可以正常工作

- 当您为某项功能声明 `android:required="true"` 时，即是规定当设备不具有该指定功能时，应用*无法正常工作，或设计为无法正常工作*。
- 当您为某项功能声明 `android:required="false"` 时，则意味着如果设备具有该功能，应用会在必要时*优先使用该功能*，但应用*设计为不使用该指定功能也可正常工作*。
- 如果您将某个功能显式声明为所需功能，则 Google Play 会将该功能添加至应用的所需功能列表。然后，它会从不提供该功能的设备上过滤该应用，使其对用户不可见

```xml
<uses-feature android:name="android.hardware.camera" android:required="true" />
<uses-feature android:name="android.hardware.camera" android:required="false" />
```

每次声明硬件功能时，请使用单独的required 元素

android.hardware.audio.low_latency

应用使用设备的低延迟时间音频管道，该管道可以减少处理声音输入或输出时的滞后和延迟。

android.hardware.audio.output

应用使用设备的扬声器、音频耳机插孔、蓝牙流式传输能力或类似机制传输声音。

android.hardware.audio.pro

应用使用设备的高端音频功能和性能能力。

android.hardware.microphone

应用使用设备的麦克风记录音频。

android.hardware.bluetooth

应用使用设备的蓝牙功能，通常用于与其他支持蓝牙的设备进行通信。

android.hardware.bluetooth_le

应用使用设备的低功耗蓝牙无线电功能。

android.hardware.camera

应用使用设备的后置相机。只有前置相机的设备不会列出该功能，因此如果您的应用可与任何朝向的相机通信，请改用 `android.hardware.camera.any` 功能

android.hardware.camera.any

应用使用设备的其中一个相机或用户为设备连接的外置相机

android.hardware.camera.autofocus

应用使用设备相机支持的自动对焦功能。

android.hardware.camera.capability.manual_post_processing

应用使用设备相机支持的 `MANUAL_POST_PROCESSING` 功能

android.hardware.camera.capability.manual_sensor

应用使用设备相机支持的 `MANUAL_SENSOR` 功能

android.hardware.camera.capability.raw

应用使用设备相机支持的 `RAW` 功能

android.hardware.camera.external

应用与用户为设备连接的外置相机进行通信

android.hardware.camera.flash

应用使用设备相机所支持的闪光灯功能

android.hardware.camera.front

应用使用设备的前置相机。

android.hardware.camera.level.full

应用使用至少一个设备相机所提供的 `FULL` 级图像捕捉支持。提供 `FULL` 支持的相机可提供快速捕捉功能、逐帧控制和手动后期处理控制。

android.hardware.fingerprint

应用使用设备的生物识别硬件读取指纹。

android.hardware.location

应用使用设备上的一项或多项功能来确定位置，例如 GPS 位置、网络位置或小区位置。

android.hardware.location.gps

应用使用通过设备的全球定位系统 (GPS) 接收器获得的精确位置坐标。

android.hardware.location.network

应用使用通过设备所支持的基于网络的地理定位系统获得的粗略位置坐标。

android.hardware.nfc

应用使用设备的近距离无线通信 (NFC) 功能。

android.hardware.sensor.accelerometer

应用使用通过设备的加速计读取的运动信息，以检测设备的当前方向。例如，应用可以使用加速计读数，以确定何时切换至纵向或横向方向。

android.hardware.sensor.gyroscope

应用使用设备的陀螺仪来检测旋转和倾斜，从而形成一个六轴定向系统。通过使用该传感器，应用可以更流畅地检测其是否需切换至纵向或横向方向。

android.hardware.screen.landscape

android.hardware.screen.portrait

应用要求设备使用纵向或横向方向。如果您的应用同时支持这两种方向，则无需声明任一功能。

android.hardware.telephony

应用使用设备的电话功能，例如提供数据通信服务的无线电话。

android.hardware.telephony.cdma

应用使用码分多址接入 (CDMA) 无线电话系统。

android.hardware.telephony.gsm

应用使用全球移动通讯系统 (GSM) 无线电话系统。

android.hardware.faketouch

应用使用基本的轻触交互事件，例如点按和拖动。

## 3.android:glEsVersion

应用需要的 OpenGL ES 版本

Google Play 按以下方式处理显式声明的功能：

- 如果您将某个功能显式声明为所需功能，则 Google Play 会将该功能添加至应用的所需功能列表。然后，它会从不提供该功能的设备上过滤该应用，使其对用户不可见。例如：

  ```xml
  <uses-feature android:name="android.hardware.camera" android:required="true" />
  ```

- 如果您将某个功能显式声明为*非*所需功能，则 Google Play *不会*将该功能添加至所需功能列表。因此，在过滤应用时，Google Play 从不会考虑显式声明的非所需功能。即使设备不提供声明的功能，Google Play 仍会考虑与设备兼容的应用并将其显示给用户，除非有其他适用的过滤规则。例如：``

| 类别                             | 权限...                                                      | ...隐含此功能要求                                            |
| :------------------------------- | :----------------------------------------------------------- | :----------------------------------------------------------- |
| 蓝牙                             | `BLUETOOTH`                                                  | `android.hardware.bluetooth`（如需了解详情，请参阅[针对蓝牙功能的特殊处理](https://developer.android.google.cn/guide/topics/manifest/uses-feature-element#bt-permission-handling)。） |
| `BLUETOOTH_ADMIN`                | `android.hardware.bluetooth`                                 |                                                              |
| 摄像头                           | `CAMERA`                                                     | `android.hardware.camera` *和* `android.hardware.camera.autofocus` |
| 位置                             | `ACCESS_MOCK_LOCATION`                                       | `android.hardware.location`                                  |
| `ACCESS_LOCATION_EXTRA_COMMANDS` | `android.hardware.location`                                  |                                                              |
| `INSTALL_LOCATION_PROVIDER`      | `android.hardware.location`                                  |                                                              |
| `ACCESS_COARSE_LOCATION`         | `android.hardware.location``android.hardware.location.network` （仅适用于目标 API 级别 20 或更低版本。） |                                                              |
| `ACCESS_FINE_LOCATION`           | `android.hardware.location``android.hardware.location.gps` （仅适用于目标 API 级别 20 或更低版本。） |                                                              |
| 麦克风                           | `RECORD_AUDIO`                                               | `android.hardware.microphone`                                |
| 电话                             | `CALL_PHONE`                                                 | `android.hardware.telephony`                                 |
| `CALL_PRIVILEGED`                | `android.hardware.telephony`                                 |                                                              |
| `MODIFY_PHONE_STATE`             | `android.hardware.telephony`                                 |                                                              |
| `PROCESS_OUTGOING_CALLS`         | `android.hardware.telephony`                                 |                                                              |
| `READ_SMS`                       | `android.hardware.telephony`                                 |                                                              |
| `RECEIVE_SMS`                    | `android.hardware.telephony`                                 |                                                              |
| `RECEIVE_MMS`                    | `android.hardware.telephony`                                 |                                                              |
| `RECEIVE_WAP_PUSH`               | `android.hardware.telephony`                                 |                                                              |
| `SEND_SMS`                       | `android.hardware.telephony`                                 |                                                              |
| `WRITE_APN_SETTINGS`             | `android.hardware.telephony`                                 |                                                              |
| `WRITE_SMS`                      | `android.hardware.telephony`                                 |                                                              |
| Wi-Fi                            | `ACCESS_WIFI_STATE`                                          | `android.hardware.wifi`                                      |
| `CHANGE_WIFI_STATE`              | `android.hardware.wifi`                                      |                                                              |
| `CHANGE_WIFI_MULTICAST_STATE`    | `android.hardware.wifi`                                      |                                                              |

# 九、uses-perimission-sdk-23

指明应用需要特定权限

## 1.android:name

权限的名称

## 2.android:maxSdkVersion

此权限应授予应用的最高 API 级别

# 十、uses-sdk

## 1.android:minSdkVersion

一个用于指定应用运行所需最低 API 级别的整数

## 2.android:targetSdkVersion

一个用于指定应用的目标 API 级别的整数

## 3.android:maxSdkVersion

一个指定作为应用设计运行目标的最高 API 级别的整数。

# 十一、supports-gl-texture

声明应用支持的一种 GL 纹理压缩格式



## 1.android:name

| 纹理压缩格式描述符                    | 注释                                                         |
| :------------------------------------ | :----------------------------------------------------------- |
| `GL_OES_compressed_ETC1_RGB8_texture` | Ericsson 纹理压缩。在 OpenGL ES 2.0 中指定，在所有支持 OpenGL ES 2.0 的 Android 设备上可用。 |
| `GL_OES_compressed_paletted_texture`  | 通用调色板纹理压缩。                                         |
| `GL_AMD_compressed_3DC_texture`       | ATI 3Dc 纹理压缩。                                           |
| `GL_AMD_compressed_ATC_texture`       | ATI 纹理压缩。在运行 Adreno GPU 的设备（包括 HTC Nexus One、Droid Incredible、EVO 及其他）上可用。为了实现最广泛的兼容性，设备还可以声明带有 `GL_ATI_texture_compression_atitc` 描述符的 `` 元素。 |
| `GL_EXT_texture_compression_latc`     | 亮度 Alpha 值纹理压缩。                                      |
| `GL_EXT_texture_compression_dxt1`     | S3 DXT1 纹理压缩。在运行 Nvidia Tegra2 平台的设备（包括 Motorala Xoom、Motorola Atrix、Droid Bionic 及其他）上受支持。 |
| `GL_EXT_texture_compression_s3tc`     | S3 纹理压缩，不特定于 DXT 变体。在运行 Nvidia Tegra2 平台的设备（包括 Motorala Xoom、Motorola Atrix、Droid Bionic 及其他）上受支持。如果您的应用需要特定的 DXT 变体，请声明相应的描述符，而不是此描述符。 |
| `GL_IMG_texture_compression_pvrtc`    | PowerVR 纹理压缩。在运行 PowerVR SGX530/540 GPU 的设备（如 Motorola DROID 系列、Samsung Galaxy S、Nexus S 和 Galaxy Tab 及其他）上可用。 |

# 十二、supports-screens

能够指定应用支持的屏幕尺寸，并为比应用支持的最大屏幕还大的屏幕启用屏幕兼容模式。请务必始终在应用中使用此元素指定应用支持的屏幕尺寸。

## 1.android:resizeable

指示应用是否可根据不同的屏幕尺寸调整大小

## 2.android:smallScreens

指示应用是否支持较小屏幕这种设备类型

## 3.android:normalScreens

指示应用是否支持“标准”屏幕这种设备类型

## 4.android:largeScreens

指示应用是否支持较大屏幕这种设备类型

## 5.android:xlargeScreens

指示应用是否支持超大屏幕这种设备类型

## 6.android:anyDensity

指示应用是否包含用于适应任何屏幕密度的资源

## 7.android:requiresSmallestWidthDp

指定所需的最小 smallestWidth。smallestWidth 是必须为应用界面提供的屏幕空间的最短边尺寸（以 `dp` 为单位），也是可用屏幕的两个尺寸中的最短尺寸

## 8.android:compatibleWidthLimitDp

指定应用支持的“最小屏幕宽度”最大值，启用[屏幕兼容模式](https://developer.android.google.cn/guide/topics/manifest/supports-screens-element#compat-mode)作为用户可选的功能

## 9.android:largestWidthLimitDp

指定应用支持的“最小屏幕宽度”最大值，强制启用[屏幕兼容模式](https://developer.android.google.cn/guide/topics/manifest/supports-screens-element#compat-mode)作为用户可选的功能

# 十三、instrumentation

声明用于监控应用与系统交互的 `Instrumentation` 类

## 1.android:functionalTest

## 2.android:handleProfiling

## 3.android:icon

## 4.android:label

## 5.android:targetPackage

## 6.android:targetProcesses

# 十四、compatible-screens

## screen

### 1.android:screenSize

### 2.android:screenDensity