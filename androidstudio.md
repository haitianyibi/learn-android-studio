# 一、android studio

android studio基于intellij IDEA构建，为所有类型的android设备提供最快的构建应用工具。

下载[最新版本](https://developer.android.google.cn/studio#downloads)  

* 系统要求
* 命令行工具
* 离线组件：gradle 插件+Maven依赖项

特性：

* 可视化布局编辑器
* APK分析器
* 快速模拟器
* 智能代码编辑器kotlin\java\c\c++
* 基于Gradle的灵活编译系统
* 实时分析器

# 二、新变化

### 快速编码和迭代更新

1. Apply Changes

借助Android Studio的Apply Changes功能，可以将代码和资源更改推送到正在运行的应用中，而且无需重启应用（在某些情况下，无需重启当前Activity）。

2. 智能代码编辑器

代码编辑器提供高级代码补全、重构和代码分析功能

3. 快速且功能丰富的模拟器

android emulator 提供比实际设备更快安装和启动应用，可以模拟各种android设备，硬件功能如GPS定位、网络延迟、动态传感器、多点触控输入。

### 最佳代码

1. 代码模板

2. 测试工具和框架
3. Lintelligence静态分析框架

### 编译

1. 集成版本控制工具GitHub和Subersion
2. Gradle编译系统，自动化编译、依赖项管理和可定义的编译配

### GUI

1. 可视化、拖放式布局编辑器
2. APK分析器
3. 翻译编辑器、本地化编辑器
4. Vector Asset Studio

### 多代码支持

1. c、c++和NDK支持

# 三、Android SDK

Android Studio 是用于开发Android应用的官方IDE，包含构建Android应用所需的一切。

Android SDK Tools是Android SDK的一个组件，包含Android全套开发和调试工具。

Android SDK build Tools是编译Android应用所需要Android SDK的一个组件。

Android SDK Platform

Android SDK Platform Tools是Android SDK的一个组件，包含于Android Platform交互的工具。

Android 模拟器



#  四、Android Gradle

Android Gradle插件版，Android Studio构建系统以Gradle为基础，Android插件通常会与Android Studio的更新步调保持一致，但插件（以及Gradle系统的其余部分）可独立于Android Studio运行并单独更新。

# 五、预览版4.0 CANARY 9

### 下载安装

[4.0 CANARY 9下载](https://dl.google.com/dl/android/studio/ide-zips/4.0.0.9/android-studio-ide-193.6137316-windows.zip)

解压

文件结构

android-studio

bin:android studio工具

jre:android studio附带的java环境，一般不使用，android studio需要和gradle使用同一个jdk，配置相同位置的jdk，Android Studio 3.0 及更高版本支持所有 Java 7 语言功能，以及部分 Java 8 语言功能，目前java语言已经更新到java13

lib:java代码，jar包(非java官方)、native动态运行库 winpty.dll，ant构建工具

license:各种许可，因为android studio使用了其他公司的工具，代码库lib，如ant,asm,eclipse

plugins:插件

build.txt: android studio版本号

LICENSE.txt: Apache License Version 2.0

NOTICE.TXT:注意版权

uninstall.exe:卸载软件

### 配置

双击studio64.exe(64位版本)，在bin目录下

do not import settings不导入设置 

unable to access Android SDK add-on list  不能够连接Android SDK添加列表

是由于连接Android SDK添加列表网站被墙，并不是SDK下载的网站，SDK可以下载

SDK是android系统一些工具和代码库API

选择cancel取消

稍后再设置SDK

welcome欢迎界面   next下一步

选择standar标准安装    next下一步

选择界面   明/暗    next下一步

Setup Type: Standard
SDK Folder: C:\Users\Administrator\AppData\Local\Android\Sdk     //SDK安装位置，
JDK Location: G:\android-studio\jre (Note: Gradle may be using JAVA_HOME when invoked from command line. More info...)       //   JDK安装位置，附带的java环境
Total Download Size: 465 MB    
SDK Components to Download:     //SDK组件下载

Android Emulator     289 MB    //android模拟器，模拟手机设备环境

Android SDK Build-Tools 29.0.3      52.6 MB    //android SDK 构建工具





Preparing "Install Intel x86 Emulator Accelerator (HAXM installer) (revision: 7.5.4)".
Downloading https://dl.google.com/android/repository/extras/intel/haxm-windows_v7_5_4.zip
"Install Intel x86 Emulator Accelerator (HAXM installer) (revision: 7.5.4)" ready.
Installing Intel x86 Emulator Accelerator (HAXM installer) in C:\Users\Administrator\AppData\Local\Android\Sdk\extras\intel\Hardware_Accelerated_Execution_Manager
"Install Intel x86 Emulator Accelerator (HAXM installer) (revision: 7.5.4)" complete.
"Install Intel x86 Emulator Accelerator (HAXM installer) (revision: 7.5.4)" finished.
Preparing "Install Android SDK Platform 29 (revision: 4)".
Downloading https://dl.google.com/android/repository/platform-29_r04.zip
"Install Android SDK Platform 29 (revision: 4)" ready.
Installing Android SDK Platform 29 in C:\Users\Administrator\AppData\Local\Android\Sdk\platforms\android-29
"Install Android SDK Platform 29 (revision: 4)" complete.
"Install Android SDK Platform 29 (revision: 4)" finished.
Preparing "Install SDK Patch Applier v4 (revision: 1)".
Downloading https://dl.google.com/android/repository/3534162-studio.sdk-patcher.zip
"Install SDK Patch Applier v4 (revision: 1)" ready.
Installing SDK Patch Applier v4 in C:\Users\Administrator\AppData\Local\Android\Sdk\patcher\v4
"Install SDK Patch Applier v4 (revision: 1)" complete.
"Install SDK Patch Applier v4 (revision: 1)" finished.
Preparing "Install Android SDK Build-Tools 29.0.3 (revision: 29.0.3)".
Downloading https://dl.google.com/android/repository/build-tools_r29.0.3-windows.zip
"Install Android SDK Build-Tools 29.0.3 (revision: 29.0.3)" ready.
Installing Android SDK Build-Tools 29.0.3 in C:\Users\Administrator\AppData\Local\Android\Sdk\build-tools\29.0.3
"Install Android SDK Build-Tools 29.0.3 (revision: 29.0.3)" complete.
"Install Android SDK Build-Tools 29.0.3 (revision: 29.0.3)" finished.
Preparing "Install Android Emulator (revision: 30.0.0)".
Downloading https://dl.google.com/android/repository/emulator-windows-6203977.zip
"Install Android Emulator (revision: 30.0.0)" ready.
Installing Android Emulator in C:\Users\Administrator\AppData\Local\Android\Sdk\emulator
"Install Android Emulator (revision: 30.0.0)" complete.
"Install Android Emulator (revision: 30.0.0)" finished.
Preparing "Install Android SDK Platform-Tools (revision: 29.0.6)".
Downloading https://dl.google.com/android/repository/platform-tools_r29.0.6-windows.zip
"Install Android SDK Platform-Tools (revision: 29.0.6)" ready.
Installing Android SDK Platform-Tools in C:\Users\Administrator\AppData\Local\Android\Sdk\platform-tools
"Install Android SDK Platform-Tools (revision: 29.0.6)" complete.
"Install Android SDK Platform-Tools (revision: 29.0.6)" finished.
Preparing "Install Sources for Android 29 (revision: 1)".
Downloading https://dl.google.com/android/repository/sources-29_r01.zip
"Install Sources for Android 29 (revision: 1)" ready.
Installing Sources for Android 29 in C:\Users\Administrator\AppData\Local\Android\Sdk\sources\android-29
"Install Sources for Android 29 (revision: 1)" complete.
"Install Sources for Android 29 (revision: 1)" finished.
Parsing C:\Users\Administrator\AppData\Local\Android\Sdk\build-tools\29.0.3\package.xml
Parsing C:\Users\Administrator\AppData\Local\Android\Sdk\emulator\package.xml
Parsing C:\Users\Administrator\AppData\Local\Android\Sdk\extras\intel\Hardware_Accelerated_Execution_Manager\package.xml
Parsing C:\Users\Administrator\AppData\Local\Android\Sdk\patcher\v4\package.xml
Parsing C:\Users\Administrator\AppData\Local\Android\Sdk\platform-tools\package.xml
Parsing C:\Users\Administrator\AppData\Local\Android\Sdk\platforms\android-29\package.xml
Parsing C:\Users\Administrator\AppData\Local\Android\Sdk\sources\android-29\package.xml
Android SDK is up to date.
Running Intel® HAXM installer
Intel HAXM updated successfully!





在C:\Users\Administrator\AppData\Local\Android\Sdk下主要文件

build-tools:构建工具 29.0.3  如：aapt.exe/apksigner.exe/

emulator:模拟器

platforms:平台 android -29   主要是android.jar包

platform-tools:平台工具，如adb.exe



finish 完成

到android studio欢迎界面



get help -- tip of the day --取消勾选show tips on startup  基本不看，一般是快捷键的使用。



startr a new android studio project   开始一个新的android项目

Open an existing Android Studio project  打开一个现存的Android Studio 项目

Get from Version Control 从版本控制获得，即从远程（仓库）服务端获得，如git,google cloud,Subversion

Profile or debug APK  配置或调试APK

Import an Android code sample  导入Android样本代码    会自动下载样本代码主页，但会连接失败（被墙）

Import project(Gradle,Eclipse ADT,等)   导入其他项目



配置保存在 C:\Users\Administrator\\.AndroidStudioPreview4.0\\config  目录下



Configure 配置

AVD Manager：创建android虚拟机（模拟器），如设备的尺寸、dpi、功能，可以在创建项目之后再确定

SDK Manager：SDK管理器，可选择下载SDK , 平台+平台工具

setting：设置 

plugins ：一些帮助提高开发效率的插件，可以管理已安装的插件，插件市场在线安装，有时候会被墙，插件如：

Github,Git,Gradle,Groovy,Kotlin,JUnit,ideaVim,Flutter,MarkDown,Scala,Bash,

Default Project Structure:默认项目结构，如：使用的SDK位置，使用的NDK位置，使用的JDK位置，JDK选择自己安装的JDK安装目录，并非内置的(embedded)JDK 

Run Configuration Templates for New Projects  为新项目运行配置模板：

Import Settings:导入设置，android studio设置文件，

Export Settings:导出设置，导出android studio设置，方便项目迁移到其它电脑，或重新安装时保存配置

Settings Repository:设置仓库，即远程仓库，代码版本控制

Compress log show in  Explorer: 将日志文件压缩包显示在Explorer文件资源管理器，

Edit  idea.properties:

Edit studio64.exe.vmoptions:

check for update :检查更新，configure里选择更新版本类型，各版本可以同时安装，各不影响。

canary :金丝雀版，更新快，不稳定

dev:开发者版,

beta：测试版，较少bug

stable:稳定版，更新慢





新建一个项目，项目名称，java语言，空白activity，

项目目录结构C:\Users\Administrator\AndroidStudioProjects

项目名称文件夹/

.gradle:所用的gradle版本6.1-rc-1:

.idea:模块，代码样式

app:

gradle:

.gitignore: 忽略的文件，提供给某些工具扫描过滤

build.gradle: 依赖库下载地址等

gradle.properties: 下载并使用的gradle版本

gradlew:

gradlew.bat:

local.properties:配置SDK地址

settings.gradle:项目名称，





gradle工具的文件

C:\Users\Administrator\\.gradle

caches:

dameon:

native:平台相关的动态链接库

wrapper:完整的gradle文件





# 六、一些坑

```
A problem occurred configuring root project 'HelloWorld'.
> Could not resolve all artifacts for configuration ':classpath'.
   > Could not resolve com.sun.activation:javax.activation:1.2.0.
     Required by:
         project : > com.android.tools.build:gradle:4.0.0-alpha09 > com.android.tools.build:builder:4.0.0-alpha09 > com.android.tools:sdklib:27.0.0-alpha09 > com.android.tools:repository:27.0.0-alpha09
      > Could not resolve com.sun.activation:javax.activation:1.2.0.
         > Could not get resource 'https://jcenter.bintray.com/com/sun/activation/javax.activation/1.2.0/javax.activation-1.2.0.pom'.
            > Could not GET 'https://jcenter.bintray.com/com/sun/activation/javax.activation/1.2.0/javax.activation-1.2.0.pom'.
```

解析获得特定的pom文件，与依赖仓库有关

```
buildscript {
    repositories {
        google()
        jcenter()
    }
    dependencies {
        classpath "com.android.tools.build:gradle:4.0.0-alpha09"

        // NOTE: Do not place your application dependencies here; they belong
        // in the individual module build.gradle files
    }
}

allprojects {
    repositories {
        google()
        jcenter()
    }
}
```

这里只用了   google()  ，jcenter()，这两个代码库，可能有些文件获取不了，可以尝试使用国内的代码库

```
 maven { url 'http://maven.aliyun.com/nexus/content/groups/public/' }
```

build.gradle文件中配置，在仅对当前项目有效，



在settings设置里找到Build,Execution,Deployment下的remote jar repositories  即远程仓库

在Maven jar repositories加入仓库地址，可以自动找到相对应的依赖项，



https://maven.aliyun.com/mvn/view

| Repository       | Type   | Policy   | Path                                                 |
| ---------------- | ------ | -------- | ---------------------------------------------------- |
| apache snapshots | proxy  | SNAPSHOT | https://maven.aliyun.com/repository/apache-snapshots |
| central          | proxy  | RELEASE  | https://maven.aliyun.com/repository/central          |
| google           | proxy  | RELEASE  | https://maven.aliyun.com/repository/google           |
| gradle-plugin    | proxy  | RELEASE  | https://maven.aliyun.com/repository/gradle-plugin    |
| jcenter          | proxy  | RELEASE  | https://maven.aliyun.com/repository/jcenter          |
| spring           | proxy  | RELEASE  | https://maven.aliyun.com/repository/spring           |
| spring-plugin    | proxy  | RELEASE  | https://maven.aliyun.com/repository/spring-plugin    |
| public           | group  | RELEASE  | https://maven.aliyun.com/repository/public           |
| releases         | hosted | RELEASE  | https://maven.aliyun.com/repository/releases         |
| snapshots        | hosted | SNAPSHOT | https://maven.aliyun.com/repository/snapshots        |
| grails-core      | proxy  | RELEASE  | https://maven.aliyun.com/repository/grails-core      |
| mapr-public      | proxy  | RELEASE  | https://maven.aliyun.com/repository/mapr-public      |





Gradle分两个，一个是本地构建用的构建工具，另一个是Android Studio中的插件，用来调用本地的工具

gradle插件版本，项目的build.gradle中gradle:后面为版本号

```
classpath "com.android.tools.build:gradle:4.0.0-alpha09"
```

C:\Users\Administrator\\.gradle\caches\modules-2\files-2.1\com.android.tools.build\gradle\4.0.0-alpha09

本地gradle工具版本

```
distributionUrl=https\://services.gradle.org/distributions/gradle-6.1-rc-1-all.zip
```

C:\Users\Administrator\\.gradle\wrapper\dists\gradle-6.1-rc-1-all

官方建议的gradle插件版本和gradle版本

| 插件版本    | 所需的Gradle版本 |
| :---------- | :--------------- |
| 1.0.0-1.1.3 | 2.2.1-2.3        |
| 1.2.0-1.3.1 | 2.2.1-2.9        |
| 1.5.0       | 2.2.1-2.13       |
| 2.0.0-2.1.2 | 2.10-2.13        |
| 2.1.3-2.2.3 | 2.14.1+          |
| 2.3.0+      | 3.3+             |
| 3.0.0+      | 4.1+             |
| 3.1.0+      | 4.4+             |
| 3.2.0-3.2.1 | 4.6+             |
| 3.3.0-3.3.2 | 4.10.1+          |
| 3.4.0-3.4.1 | 5.1.1+           |
| 3.5.0+      | 5.4.1-5.6.4      |



想要在终端使用gradle需要配置环境变量

