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

# 界面