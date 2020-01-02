# 一、Android Studio

## 1.概览

### 项目结构

Android Studio的每个项目都包含一个或多个含源代码文件和资源文件的模块，Android项目视图按模块组织结构。模块类型包括：

* Android应用模块

* 库模块

* Google App Engine模块

所有编译文件都在顶层Gradle Scripts下显示，且每个应用模块都包含以下文件夹：

* manifests：包含AndroidManifest.xml文件

* java：包含 java源代码文件，包括 JUnit测试代码

* res：包含所有非代码资源，例如XML布局，界面字符串和位图图像

磁盘上的Android项目结构与此表示形式的项目结构不同，要查看项目实际的文件结构，选择project视图。

![img](https://developer.android.google.cn/studio/images/intro/project-android-view_2-1_2x.png)

![image-20200102181048465](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20200102181048465.png)


## 2.安装android studio

## 3.迁移至android studio

## 4.配置IDE

## 5.键盘快捷键

## 6.无障碍功能

## 7.更新IDE和工具

# 二、工作流基础知识

# 三、管理项目

## 1.概览

## 2.创建项目

## 3.添加kotlin代码

## 4.Dynamic Delivery简介

### 概览

### 配置基本模块

### 配置安装时分发

### 配置按需分发

### 按需分发最佳做法

### 配置免安装分发

### 配置按条件分发

## 5.添加C/C++代码

### 概览

### 安装NDK和CMake

### 配置CMake

### 关联Gradle

## 6.创建Android库

## 7.设置持续集成

# 四、编写应用

## 1.概览

## 2.从模板添加代码

## 3.查找示例代码

## 4.为新设备添加模块

## 5.创建 Java类或类型

## 6.使用 Java8语言功能

## 7.添加应用资源

## 8.使用Layout Editor构建界面

## 9.管理应用界面资源

## 10.设计应用主题背景

## 11.添加多密度矢量图形

## 12.使用Image Asset Studio 创建图标

## 13.创建可调整大小的位图（9-Patch）

## 14.创建WebP图片

## 15.本地化界面

## 16.添加Android应用连接

## 17.连接到Firebase

## 18.使用Lint检查改进代码

## 19.使用注解改进代码检查

## 20.工具属性参考

# 五、编译和运行应用

## 1.概览

## 2.在模拟器上运行应用

### 概览

### 创建和管理虚拟设备

### 从命令行启动虚拟设备

### 发送模拟器控制台命令

### 设置模拟器网络

### 配置硬件加速

### 对模拟器进行问题排查

## 3.在硬件设备上运行应用

### 概览

### 安装原始设备制造商（OEM）USB驱动程序

### 获取Google USB驱动程序

## 4.创建运行/调试配置

## 5.从命令行编译应用

# 六、配置编译版本

## 1.概览

## 2.设置应用ID

## 3. 添加编译依赖项

## 4.优化构建速度

## 5.使用构建缓存

## 6.配置编译变体

## 7.构建多个APK

## 8.合并多个清单

## 9.将构建变量注入清单

## 10.压缩应用

## 11.启用多DEX处理

## 12.使用APK分析器分析构建

## 13.Gradle提示与诀窍

# 七、调试应用

## 1.概览

## 2.配置开发者选项

## 3.写入和查看日志

## 4.分析堆栈轨迹

## 5.使用布局检查器调试布局

## 6.使用精美像素风格验证设计

## 7.查看设备上的文件

## 8.截取屏幕截图

## 9.录制视频

## 10.获取并阅读错误报告

# 八、测试应用

## 1.概览

## 2.从命令行进行测试

## 3.使用Espresso测试记录器创建界面测试

## 4.UI/App Exerciser Monkey

## 5.monkeyrunner 参考

### 概览

### monkeydevice

### monkeyimage

### monkeyrunner

# 九、剖析应用性能

## 1.概览

## 2.衡量应用效果

## 3.应用设置基准

### 概览

### 在不使用Gradle的情况下编译基准

### 在持续集成中运行基准

## 4.分析和调试预编译APK

## 5.检查CPU活动

### 概览

### 通过检查应用生成跟踪日志

## 6.查看堆和内存分配 

## 7.检查网络活动

## 8.检查能耗情况

#  十、发布应用

## 1.概览

## 2.准备发布

## 3.应用版本控制

## 4.应用签名

## 5.上传应用

# 十一、命令行工具

## 1.概览

## 2.aapt2

## 3.adb

## 4.apkanalyzer

## 5.apksigner

## 6.avdmanger

## 7.bmgr

## 8.bundletool

## 9.d8

## 10.dmtracedump

## 11.dumpsys

## 12.etc1tool

## 13.jobb

## 14.jetifier-standalone

## 15.logcat

## 16.mksdcard

## 17.sdkmanager

## 18.systrace

## 19.perfetto

## 20.zipalign

## 21.环境变量