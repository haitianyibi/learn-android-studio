# Activity

Android系统会调用Activity生命周期阶段特定的回调方法来执行Activity中的代码。

Activity 充当了应用与用户互动的入口点。

一个应用包含多个activity，至少一个Activity作为应用的主入口，用来控制启动应用时显示的第一个界面，每个activity之间可以相互启动以执行activity当中的代码。

使用activity必须要在清单文件中注册。将activity元素作为application的子元素。其中activity必要的属性是name。

```xml
    <manifest ... >
      <application ... >
          <activity android:name=".ExampleActivity" />
          ...
      </application ... >
      ...
    </manifest >
```

# Intent

intent提供组件之间的相互启动。

## 显式intent

指明启动指定的avtivity

## 隐式intent

启动具有相关权限的activity

activity具有不同权限，同时设置intent过滤器将响应指定的隐式intent，该隐式intent可能由其它应用给出，如果不响应其它应用的intent则不需要设置intent过滤器。由应用内部activity之间显式intent调用。

# 权限

权限是赋予给应用application的

## 声明权限

声明权限可以使别的应用启动本activity，

使用权限使应用可以执行的代码功能发挥

intent过滤使被启动的应用筛选应该启动的activity