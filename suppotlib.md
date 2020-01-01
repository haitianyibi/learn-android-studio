# 支持库

  Android 9(API 28)发布后，最新支持库AndroidX也随之诞生，它属于 Jetpack 。除了现有的支持库，AndroidX库还包括最新的 Jetpack组件。

用途： 

* 新版API的向后兼容性

* 工具类和辅助类
* 调试和实用工具

支持库提供的类和方法与Android框架中的API非常相似，使用支持库代替框架API的情况：

* 特定功能的兼容性：如果要在搭载早期版本平台的设备上支持最新的平台功能，请使用支持库中的等效的类和方法。
* 相关库功能的兼容性：更复杂的支持库类可能依赖于一个或多个其他支持库类
* 常规设置兼容性

版本支持和软件包名称

支持库发布版本

库依赖项

查看应用中包含哪些库和依赖项

```
    gradle -q dependencies your-app-project:dependencies
```

# 支持库功能

ActivityCompat：包括运行时权限和动画过渡

FragmentActivity：

 AppCompatActivity:

Fragment:

ContextCompat:

IntentCompat:

loader:

Preference:

ContenResolverCompat:

# 支持库软件包

### v4 支持库

* V4 compat库：兼容性封装容器：Gradle编译脚本依赖项标识符：```com.android.support:support-compat:*28.0.0`*``

* V4 core-utils库：实用工具类：```com.android.support:support-core-utils:*28.0.0`*``

* v4 core-ui库：界面相关组件：```com.android.support:support-core-ui:28.0.0```

* v4 media-compat:媒体框架：```com.android.support:support-media-compat:28.0.0```

* v4 fragment库：界面和功能封装：```com.android.support:support-fragment:28.0.0```

### Multidex支持库

通过多个Dalvik可执行文件（DEX）为编译应用提供支持：```com.android.support:multidex:1.0.0```

### v7支持库

* v7 appcompat库:操作栏界面设计模式支持：```com.android.support:appcompat-v7:28.0.0```
* v7 cardview库：```com.android.support:cardview-v7:28.0.0```
* v7 gridlayout库：```com.android.support:gridlayout-v7:28.0.0```
* v7 mediarouter库：```com.android.support:mediarouter-v7:28.0.0```
* v7 palette库：```com.android.support:palette-v7:28.0.0```
* v7 recyclerview库：```com.android.support:recyclerview-v7:28.0.0```
* v7 Preference库：```com.android.support:preference-v7:28.0.0```
### v8支持库

* ### v8 renderscript 库

```groovy
    defaultConfig {
        renderscriptTargetApi 18
        renderscriptSupportModeEnabled true
    }
```

###  v13 支持库

```groovy
 com.android.support:support-v13:28.0.0
```

###  v14 Preference 支持库

```groovy
   com.android.support:preference-v14:28.0.0
```

### 适用于电视的 v17 Preference 支持库

```groovy
com.android.support:preference-leanback-v17:28.0.0 
```

### v17 Leanback 库

```groovy
   com.android.support:leanback-v17:28.0.0
```

###  Vector Drawable 库

```groovy
 com.android.support:support-vector-drawable:28.0.0
```

###  Animated Vector Drawable 库

```groovy
com.android.support:animated-vector-drawable:28.0.0
```

###  Design 支持库

```groovy
   com.android.support:design:28.0.0
```

###  Custom Tabs 支持库

```groovy
 com.android.support:customtabs:28.0.0
```

###  Percent 支持库

```groovy
com.android.support:percent:28.0.0
```

###  ExifInterface 支持库

```groovy
 com.android.support:exifinterface:28.0.0
    
```

### 适用于电视的 App Recommendation 支持库

```groovy
  com.android.support:recommendation:28.0.0
```

# 支持库设置

### 选择支持库

### 添加支持库

### 使用支持库API

# 界面

通用布局容器：RecyclerView、ViewPager、GridLayout、PercentFrameLayout、PercentRelativeLayout

专用布局容器：DrawerLayout、SlidingPaneLayout、NestedScrollView、SwipeRefreshLayout

视图、对话框、微件：CardView、AppCompatDialogFragment、NotificationCompat、SearchView

# Material Design

CoordinatorLayout、AppBarLayout、FloatingActionButton、DrawerLayout、TabLayout、Snackbar

## Wear UI 库

```groovy
 com.android.support:wear:28.0.0
```

# 图形

矢量图、矢量动画支持

# 无障碍性

ExploreByTouchHelper

# 媒体播放

MediaRouter、MediaControllerCompat

# TV应用

# Wear应用

# 实用工具

