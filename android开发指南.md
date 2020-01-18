[TOC]



# 一、Android基础

## 1.简介

Android 应用由各种可单独调用的组件构成。例如，Activity 是提供界面 (UI) 的一种应用组件。

MainActivity 在用户点按您的应用图标时启动。您还可以将用户从其他位置（例如，从通知中，甚至从其他应用中）引导至某个 Activity。

其他组件（如广播接收器和服务）使应用能够在没有界面的情况下执行后台任务。

Android 允许您为不同的设备提供不同的资源。例如，您可以针对不同的屏幕尺寸创建不同的布局。系统会根据当前设备的屏幕尺寸确定要使用的布局。

如果应用的任何功能需要特定的硬件，如摄像头，您可以在运行时查询该设备是否具有该硬件，如果没有，则停用相应的功能。您可以指定应用需要特定的硬件，这样，Google Play 就不会允许在没有这些硬件的设备上安装应用。

## 2.构建首个应用

**Start a new Android Studio project**

**Empty Activity**

在 **Configure your project** 窗口中，完成以下操作：

- 在 **Name** 字段中输入“My First App”。
- 在 **Package name** 字段中输入“com.example.myfirstapp”。
- 如果您想将项目放在其他文件夹中，请更改其 **Save** 位置。
- 从 **Language** 下拉菜单中选择 Java 或 Kotlin。
- 选中 **Use androidx.\* artifacts** 旁边的复选框。
- 其他选项保持原样。

确保已打开 **Project** 窗口（依次选择 View > Tool Windows > Project），并从该窗口顶部的下拉列表中选择 Android 视图

- **app > java > com.example.myfirstapp > MainActivity**

  这是主 Activity。它是应用的入口点。当您构建和运行应用时，系统会启动此 `Activity` 的实例并加载其布局。

- **app > res > layout > activity_main.xml**

  此 XML 文件定义了 Activity 界面的布局。它包含一个 `TextView` 元素，其中具有“Hello, World!”文本

- **app > manifests > AndroidManifest.xml**

  [清单文件](https://developer.android.google.cn/guide/topics/manifest/manifest-intro)[描述了应用的基本特性并定义了每个应用组件。](https://developer.android.google.cn/guide/topics/manifest/manifest-intro)

  [有两个使用此名称的文件：一个针对项目“Project: My First App”，另一个针对应用模块“Module: app”。每个模块均有自己的 `build.gradle` 文件，但此项目当前仅有一个模块。您可以使用每个模块的 `build.file` 控制 ](https://developer.android.google.cn/guide/topics/manifest/manifest-intro)[Gradle 插件](https://developer.android.google.cn/studio/releases/gradle-plugin)编译应用的方式。要详细了解此文件，请参阅[配置编译版本](https://developer.android.google.cn/studio/build/index#module-level)。

模拟器运行

Android 应用的界面 (UI) 以布局和微件的层次结构形式构建而成。布局是 [`ViewGroup`](https://developer.android.google.cn/reference/android/view/ViewGroup.html) 对象，即控制其子视图在屏幕上的放置方式的容器。微件是 [`View`](https://developer.android.google.cn/reference/android/view/View.html) 对象，即按钮和文本框等界面组件。

![image-20200114183406594](android%E5%BC%80%E5%8F%91%E6%8C%87%E5%8D%97.assets/image-20200114183406594.png)

Android 提供了 `ViewGroup` 和 `View` 类的 XML 词汇表，因此界面的大部分内容都在 XML 文件中定义

使用 Android Studio 的 Layout Editor 创建布局，而不是教您编写 XML 代码

Layout Editor 会在您拖放视图构建布局时为您编写 XML 代码。

**app > res > layout > activity_main.xml**

 **Default Margins**

**Device for Preview** 

 **Component Tree** 面板显示布局的视图层次结构

`ConstraintLayout` 是一种布局，它根据同级视图和父布局的约束条件定义每个视图的位置。这样一来，使用扁平视图层次结构既可以创建简单布局，又可以创建复杂布局。这种布局无需嵌套布局。嵌套布局是布局内的布局（如图 2 所示），会增加绘制界面所需的时间。

移除布局中已有的内容。在 **Component Tree** 面板中点击 **TextView**，然后按 Delete 键。

**Palette** 面板中，点击 Text 以显示可用的文本控件。

将 **Plain Text** 拖动到设计编辑器中，并将其放在靠近布局顶部的位置。这是一个接受纯文本输入的 `EditText` 微件。

要按水平对齐约束视图，请创建一个文本基线之间的约束条件。为此，请点击按钮，然后点击 **Edit Baseline** 图标 ![img](android%E5%BC%80%E5%8F%91%E6%8C%87%E5%8D%97.assets/layout-editor-action-baseline.png)，该图标显示在设计编辑器中选定视图的正下方。基线锚点显示在按钮内部。点击并按住此锚点，然后将其拖动到文本框中显示的基线锚点上。

app > res > values > strings.xml

这是一个[字符串资源](https://developer.android.google.cn/guide/topics/resources/string-resource.html)文件，您可在此文件中指定所有界面字符串。该文件可让您在一个位置管理所有界面字符串，使字符串的查找、更新和本地化变得更加容易。

点击窗口顶部的 **Open editor**。此时将打开 [Translations Editor](https://developer.android.google.cn/studio/write/translations-editor.html)，它提供了一个可以添加和修改默认字符串的简单界面。它还有助于让所有已翻译的字符串井然有序。

 **Attributes** 窗口

 **text** 属性

 **hint** 属性

 **Pick a Resource**

[链](https://developer.android.google.cn/training/constraint-layout/index.html#constrain-chain)是两个或多个视图之间的双向约束条件，可让您采用一致的方式安排链接的视图。

您已经构建了一个应用，该应用将显示一个 Activity（单个屏幕），其中包含一个文本字段和一个**发送**按钮。在本节课，您将向 `MainActivity` 添加一些代码，以便在用户点按**发送**按钮时，启动一个显示消息的新 Activity

**app > java > com.example.myfirstapp > MainActivity**

Alt+Enter（或在 Mac 上按 Option+Enter）进行快速修复。如果出现一个菜单，请选择 **Import class**。

```
    public class MainActivity extends AppCompatActivity {
        @Override
        protected void onCreate(Bundle savedInstanceState) {
            super.onCreate(savedInstanceState);
            setContentView(R.layout.activity_main);
        }

        /** Called when the user taps the Send button */
        public void sendMessage(View view) {
            // Do something in response to button
        }
    }
```

返回到 **activity_main.xml** 文件，并从该按钮调用此方法：

在 **Attributes** 窗口中，找到 onClick 属性，并从其下拉列表中选择 sendMessage [MainActivity]。

当用户点按该按钮时，系统将调用 `sendMessage()` 方法。

构建一个 Intent

`Intent` 是在相互独立的组件（如两个 Activity）之间提供运行时绑定功能的对象。`Intent` 表示应用执行某项操作的意图。您可以使用 Intent 执行多种任务，但在本课中，您的 Intent 将用于启动另一个 Activity。

```
        public static final String EXTRA_MESSAGE = "com.example.myfirstapp.MESSAGE";

        public void sendMessage(View view) {
            Intent intent = new Intent(this, DisplayMessageActivity.class);
            EditText editText = (EditText) findViewById(R.id.editText);
            String message = editText.getText().toString();
            intent.putExtra(EXTRA_MESSAGE, message);
            startActivity(intent);
        }
```

```
    import androidx.appcompat.app.AppCompatActivity;
    import android.content.Intent;
    import android.os.Bundle;
    import android.view.View;
    import android.widget.EditText;
```

- `Intent` 构造函数会获取两个参数：`Context` 和 `Class`。

  首先使用 `Context` 参数，因为 `Activity` 类是 的子类。

  在本例中，系统将 `Intent,` 传递到的应用组件的 `Class` 参数为要启动的 Activity。

- `putExtra()` 方法将 `EditText` 的值添加到 Intent。`Intent` 能够以名为“extra”的键值对形式携带数据类型。

  您的键是一个公共常量 `EXTRA_MESSAGE`，因为下一个 Activity 将使用该键检索文本值。为 Intent extra 定义键时，最好使用应用的软件包名称作为前缀。这样可以确保这些键是独一无二的，万一您的应用需要与其他应用进行交互。

- `startActivity()` 方法将启动一个由 `Intent` 指定的 `DisplayMessageActivity` 实例。接下来，您需要创建该类。

**New > Activity > Empty Activity**

创建第二个 Activity

在 **Configure Activity** 窗口中，输入“DisplayMessageActivity”作为 Activity Name

Android Studio 会自动执行三项操作：

- 创建 `DisplayMessageActivity` 文件。
- 创建与 `DisplayMessageActivity` 文件对应的布局文件 `activity_display_message.xml`。
- 在 `AndroidManifest.xml` 中添加所需的Activity元素。

如果您运行应用并点按第一个 Activity 上的按钮，将启动第二个 Activity，但它为空。这是因为第二个 Activity 使用模板提供的空布局。

**app > res > layout > activity_display_message.xml** 文件

添加一个文本视图

 textSize 和 textColor 等属性

修改第二个 Activity 以显示第一个 Activity 传递的消息

在 `DisplayMessageActivity` 中，将以下代码添加到 `onCreate()` 方法中：

```
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_display_message);
        
        // Get the Intent that started this activity and extract the string
        Intent intent = getIntent();
        String message = intent.getStringExtra(MainActivity.EXTRA_MESSAGE);

        // Capture the layout's TextView and set the string as its text
        TextView textView = findViewById(R.id.textView);
        textView.setText(message);
    }
```

```
    import androidx.appcompat.app.AppCompatActivity;
    import android.content.Intent;
    import android.os.Bundle;
    import android.widget.TextView;
```

添加向上导航功能

不是主入口点的每个屏幕（所有不是主屏幕的屏幕）都必须提供导航功能，以便将用户引导至应用层次结构中的逻辑父级屏幕

要添加**向上**按钮，您需要在 [`AndroidManifest.xml`](https://developer.android.google.cn/guide/topics/manifest/manifest-intro) 文件中声明哪个 Activity 是逻辑父级。打开 **app > manifests > AndroidManifest.xml** 文件，找到 `DisplayMessageActivity` 的 `` 标记，然后将其替换为以下代码：

```
    <activity android:name=".DisplayMessageActivity"
              android:parentActivityName=".MainActivity">
        <!-- The meta-data tag is required if you support API level 15 and lower -->
        <meta-data
            android:name="android.support.PARENT_ACTIVITY"
            android:value=".MainActivity" />
    </activity>
```

Android 系统现在会自动向应用栏添加**向上**按钮。

点击工具栏中的 **Apply Changes** ![img](https://developer.android.google.cn/studio/images/buttons/toolbar-apply-changes.png?dcb_=0.26553687527109604) 以运行应用。当应用打开后，在文本字段中输入一条消息，点按 **Send** 即会看到该消息显示在第二个 Activity 中。



## 3.应用基础知识

您可以使用 Kotlin、Java 和 C++ 语言编写 Android 应用。Android SDK 工具会将您的代码连同任何数据和资源文件编译成一个 APK（*Android 软件包*），即带有 `.apk` 后缀的归档文件。一个 APK 文件包含 Android 应用的所有内容，它也是 Android 设备用来安装应用的文件。

每个 Android 应用都处于各自的安全沙盒中，并受以下 Android 安全功能的保护：

- Android 操作系统是一种多用户 Linux 系统，其中的每个应用都是一个不同的用户；
- 默认情况下，系统会为每个应用分配一个唯一的 Linux 用户 ID（该 ID 仅由系统使用，应用并不知晓）。系统会为应用中的所有文件设置权限，使得只有分配给该应用的用户 ID 才能访问这些文件；
- 每个进程都拥有自己的虚拟机 (VM)，因此应用代码独立于其他应用而运行。
- 默认情况下，每个应用都在其自己的 Linux 进程内运行。Android 系统会在需要执行任何应用组件时启动该进程，然后当不再需要该进程或系统必须为其他应用恢复内存时，其便会关闭该进程。

Android 系统实现了*最小权限原则*。换言之，默认情况下，每个应用只能访问执行其工作所需的组件，而不能访问其他组件。这样便能创建非常安全的环境，在此环境中，应用无法访问其未获得权限的系统部分。不过，应用仍可通过一些途径与其他应用共享数据以及访问系统服务：

- 可以安排两个应用共享同一 Linux 用户 ID，在此情况下，二者便能访问彼此的文件。为节省系统资源，也可安排拥有相同用户 ID 的应用在同一 Linux 进程中运行，并共享同一 VM。应用还必须使用相同的证书进行签名。
- 应用可以请求访问设备数据（如用户的联系人、短信消息、可装载存储装置（SD 卡）、相机、蓝牙等）的权限。用户必须明确授予这些权限。如需了解详细信息，请参阅[使用系统权限](https://developer.android.google.cn/training/permissions/index.html)。

本文档的其余部分将介绍以下概念：

- 用于定义应用的核心框架组件
- 用来声明组件和应用必需设备功能的清单文件。
- 与应用代码分离并允许应用针对各种设备配置适当优化其行为的资源。

应用组件是 Android 应用的基本构建块。每个组件都是一个入口点，系统或用户可通过该入口点进入您的应用。有些组件会依赖于其他组件。

共有四种不同的应用组件类型：

- Activity
- 服务
- 广播接收器
- 内容提供程序

每种类型都有不同的用途和生命周期，后者会定义如何创建和销毁组件。以下部分将介绍应用组件的四种类型。

*Activity* 是与用户交互的入口点。它表示拥有界面的单个屏幕。例如，电子邮件应用可能有一个显示新电子邮件列表的 Activity、一个用于撰写电子邮件的 Activity 以及一个用于阅读电子邮件的 Activity。尽管这些 Activity 通过协作在电子邮件应用中形成一种紧密结合的用户体验，但每个 Activity 都独立于其他 Activity 而存在。因此，其他应用可以启动其中任何一个 Activity（如果电子邮件应用允许）。例如，相机应用可以启动电子邮件应用内用于撰写新电子邮件的 Activity，以便用户共享图片。Activity 有助于完成系统和应用程序之间的以下重要交互：

- 追踪用户当前关心的内容（屏幕上显示的内容），以确保系统继续运行托管 Activity 的进程。
- 了解先前使用的进程包含用户可能返回的内容（已停止的 Activity），从而更优先保留这些进程。
- 帮助应用处理终止其进程的情况，以便用户可以返回已恢复其先前状态的 Activity。
- 提供一种途径，让应用实现彼此之间的用户流，并让系统协调这些用户流。（此处最经典的示例是共享。）

您需将 Activity 作为 `Activity` 类的子类来实现。如需了解有关 `Activity` 类的更多信息，请参阅 [Activity](https://developer.android.google.cn/guide/components/activities.html) 开发者指南。

*服务*是一个通用入口点，用于因各种原因使应用在后台保持运行状态。它是一种在后台运行的组件，用于执行长时间运行的操作或为远程进程执行作业。服务不提供界面。例如，当用户使用其他应用时，服务可能会在后台播放音乐或通过网络获取数据，但这不会阻断用户与 Activity 的交互。诸如 Activity 等其他组件可以启动服务，使该服务运行或绑定到该服务，以便与其进行交互。事实上，有两种截然不同的语义服务可以告知系统如何管理应用：已启动服务会告知系统使其运行至工作完毕。此类工作可以是在后台同步一些数据，或者在用户离开应用后继续播放音乐。在后台同步数据或播放音乐也代表了两种不同类型的已启动服务，而这些服务可以修改系统处理它们的方式：

- 音乐播放是用户可直接感知的服务，因此，应用会向用户发送通知，表明其希望成为前台，从而告诉系统此消息；在此情况下，系统明白它应尽全力维持该服务进程运行，因为进程消失会令用户感到不快。
- 通常，用户不会意识到常规后台服务正处于运行状态，因此系统可以更自由地管理其进程。如果系统需要使用 RAM 来处理用户更迫切关注的内容，则其可能允许终止服务（然后在稍后的某个时刻重启服务）。

绑定服务之所以能运行，原因是某些其他应用（或系统）已表示希望使用该服务。从根本上讲，这是为另一个进程提供 API 的服务。因此，系统会知晓这些进程之间存在依赖关系，所以如果进程 A 绑定到进程 B 中的服务，系统便知道自己需使进程 B（及其服务）为进程 A 保持运行状态。此外，如果进程 A 是用户关心的内容，系统随即也知道将进程 B 视为用户关心的内容。由于存在灵活性（无论好坏），服务已成为非常有用的构建块，并且可实现各种高级系统概念。动态壁纸、通知侦听器、屏幕保护程序、输入方法、无障碍功能服务以及众多其他核心系统功能均可构建为在其运行时由应用实现、系统绑定的服务。

您需将服务作为 `Service` 的子类来实现。如需了解有关 `Service` 类的更多信息，请参阅[服务](https://developer.android.google.cn/guide/components/services.html)开发者指南。

借助*广播接收器*组件，系统能够在常规用户流之外向应用传递事件，从而允许应用响应系统范围内的广播通知。由于广播接收器是另一个明确定义的应用入口，因此系统甚至可以向当前未运行的应用传递广播。例如，应用可通过调度提醒来发布通知，以告知用户即将发生的事件。而且，通过将该提醒传递给应用的广播接收器，应用在提醒响起之前即无需继续运行。许多广播均由系统发起，例如，通知屏幕已关闭、电池电量不足或已拍摄照片的广播。应用也可发起广播，例如，通知其他应用某些数据已下载至设备，并且可供其使用。尽管广播接收器不会显示界面，但其可以[创建状态栏通知](https://developer.android.google.cn/guide/topics/ui/notifiers/notifications.html)，在发生广播事件时提醒用户。但广播接收器更常见的用途只是作为通向其他组件的*通道*，旨在执行极少量的工作。例如，它可能会根据带 `JobScheduler` 的事件调度 `JobService` 来执行某项工作

广播接收器作为 `BroadcastReceiver` 的子类实现，并且每条广播都作为 `Intent` 对象进行传递。如需了解详细信息，请参阅 `BroadcastReceiver` 类。



Android 系统设计的独特之处在于，任何应用都可启动其他应用的组件。例如，当您想让用户使用设备相机拍摄照片时，另一个应用可能也可执行该操作，因而您的应用便可使用该应用，而非自行产生一个 Activity 来拍摄照片。您无需加入甚至链接到该相机应用的代码。只需启动拍摄照片的相机应用中的 Activity 即可。完成拍摄时，系统甚至会将照片返回您的应用，以便您使用。对用户而言，这就如同相机是您应用的一部分。

当系统启动某个组件时，它会启动该应用的进程（如果尚未运行），并实例化该组件所需的类。例如，如果您的应用启动相机应用中拍摄照片的 Activity，则该 Activity 会在属于相机应用的进程（而非您的应用进程）中运行。因此，与大多数其他系统上的应用不同，Android 应用并没有单个入口点（即没有 `main()` 函数）。

由于系统在单独的进程中运行每个应用，且其文件权限会限制对其他应用的访问，因此您的应用无法直接启动其他应用中的组件，但 Android 系统可以。如要启动其他应用中的组件，请向系统传递一条消息，说明启动特定组件的 *Intent*。系统随后便会为您启动该组件。

在四种组件类型中，有三种（Activity、服务和广播接收器）均通过异步消息 *Intent* 进行启动。Intent 会在运行时对各个组件进行互相绑定。您可以将 Intent 视为从其他组件（无论该组件是属于您的应用还是其他应用）请求操作的信使。

您需使用 `Intent` 对象创建 Intent，该对象通过定义消息来启动特定组件（显式 Intent）或特定的组件*类型*（隐式 Intent）。

对于 Activity 和服务，Intent 会定义要执行的操作（例如，*查看*或*发送*某内容），并且可指定待操作数据的 URI，以及正在启动的组件可能需要了解的信息。例如，Intent 可能会传达对 Activity 的请求，以便显示图像或打开网页。在某些情况下，您可以通过启动 Activity 来接收结果，这样 Activity 还会返回 `Intent` 中的结果。例如，您可以发出一个 Intent，让用户选取某位联系人并将其返回给您。返回 Intent 包含指向所选联系人的 URI。

对于广播接收器，Intent 只会定义待广播的通知。例如，指示设备电池电量不足的广播只包含指示*“电池电量不足”*的已知操作字符串。

与 Activity、服务和广播接收器不同，内容提供程序并非由 Intent 启动。相反，它们会在成为 `ContentResolver` 的请求目标时启动。内容解析程序会通过内容提供程序处理所有直接事务，因此通过提供程序执行事务的组件便无需执行事务，而是改为在 `ContentResolver` 对象上调用方法。这会在内容提供程序与请求信息的组件之间留出一个抽象层（以确保安全）。

每种组件都有不同的启动方法：

- 如要启动 Activity，您可以向 `startActivity()` 或 `startActivityForResult()` 传递 `Intent`（当您想让 Activity 返回结果时），或者为其安排新任务。
- 在 Android 5.0（API 级别 21）及更高版本中，您可以使用 `JobScheduler` 类来调度操作。对于早期 Android 版本，您可以通过向 `startService()` 传递 `Intent` 来启动服务（或对执行中的服务下达新指令）。您也可通过向将 `bindService()` 传递 `Intent` 来绑定到该服务。
- 您可以通过向 `sendBroadcast()`、`sendOrderedBroadcast()` 或 `sendStickyBroadcast()` 等方法传递 `Intent` 来发起广播。
- 您可以通过在 `ContentResolver` 上调用 `query()`，对内容提供程序执行查询。

如需了解有关 Intent 用法的详细信息，请参阅 [Intent 和 Intent 过滤器](https://developer.android.google.cn/guide/components/intents-filters.html)文档。以下文档将为您详细介绍如何启动特定组件：[Activity](https://developer.android.google.cn/guide/components/activities.html)、[服务](https://developer.android.google.cn/guide/components/services.html)、`BroadcastReceiver` 和内容提供程序。

在 Android 系统启动应用组件之前，系统必须通过读取应用的*清单*文件 (`AndroidManifest.xml`) 确认组件存在。您的应用必须在此文件中声明其所有组件，该文件必须位于应用项目目录的根目录中。

除了声明应用的组件外，清单文件还有许多其他作用，如：

- 确定应用需要的任何用户权限，如互联网访问权限或对用户联系人的读取权限。
- 根据应用使用的 API，声明应用所需的最低 [API 级别](https://developer.android.google.cn/guide/topics/manifest/uses-sdk-element.html#ApiLevels)。
- 声明应用使用或需要的硬件和软件功能，如相机、蓝牙服务或多点触摸屏幕。
- 声明应用需要链接的 API 库（Android 框架 API 除外），如 [Google 地图库](http://code.google.com/android/add-ons/google-apis/maps-overview.html)。

清单文件的主要任务是告知系统应用组件的相关信息。例如，清单文件可按如下所示声明 Activity：

```xml
<?xml version="1.0" encoding="utf-8"?>
<manifest ... >
    <application android:icon="@drawable/app_icon.png" ... >
        <activity android:name="com.example.project.ExampleActivity"
                  android:label="@string/example_label" ... >
        </activity>
        ...
    </application>
</manifest>
```

在 `` 元素中，`android:icon` 属性指向标识应用的图标所对应的资源。

在 `` 元素中，`android:name` 属性指定 `Activity` 子类的完全限定类名，`android:label` 属性指定用作 Activity 的用户可见标签的字符串。

您必须使用以下元素声明所有应用组件：

- Activity 的 `` 元素。
- 服务的 `` 元素。
- 广播接收器的 `` 元素。
- 内容提供程序的 `` 元素。

如果未在清单文件中声明源代码中包含的 Activity、服务和内容提供程序，则这些组件对系统不可见，因此也永远不会运行。不过，您可以 `BroadcastReceiver` 对象的形式，在清单中声明或在代码中动态创建广播接收器；以及通过调用 `registerReceiver()`，在系统中注册广播接收器。

如需详细了解如何为您的应用构建清单文件，请参阅 [AndroidManifest.xml 文件](https://developer.android.google.cn/guide/topics/manifest/manifest-intro.html)文档。

声明组件功能

如上文[启动组件](https://developer.android.google.cn/guide/components/fundamentals#ActivatingComponents)中所述，您可以使用 `Intent` 来启动 Activity、服务和广播接收器。您可以通过在 Intent 中显式命名目标组件（使用组件类名）来使用 `Intent`。您还可使用隐式 Intent，通过它来描述要执行的操作类型和待操作数据（可选）。借助隐式 Intent，系统能够在设备上找到可执行该操作的组件，并启动该组件。如果有多个组件可以执行 Intent 所描述的操作，则由用户选择使用哪一个组件。

**注意：**如果您使用 Intent 来启动 `Service`，请使用[显式](https://developer.android.google.cn/guide/components/intents-filters.html#Types) Intent 来确保应用的安全性。使用隐式 Intent 启动服务存在安全隐患，因为您无法确定哪些服务将响应 Intent，且用户无法看到哪些服务已启动。从 Android 5.0（API 级别 21）开始，如果使用隐式 Intent 调用 `bindService()`，系统会抛出异常。请勿为您的服务声明 Intent 过滤器。

通过将收到的 Intent 与设备上其他应用的清单文件中提供的 *Intent 过滤器*进行比较，系统便可识别能响应 Intent 的组件。

在应用的清单文件中声明 Activity 时，您可以选择性地加入声明 Activity 功能的 Intent 过滤器，以便响应来自其他应用的 Intent。您可以将 [``](https://developer.android.google.cn/guide/topics/manifest/intent-filter-element.html) 元素作为组件声明元素的子项进行添加，从而为您的组件声明 Intent 过滤器。

例如，如果您构建的电子邮件应用包含用于撰写新电子邮件的 Activity，则可通过声明 Intent 过滤器来响应“send”Intent（目的是发送新电子邮件），如下方示例所示：

```xml
<manifest ... >
    ...
    <application ... >
        <activity android:name="com.example.project.ComposeEmailActivity">
            <intent-filter>
                <action android:name="android.intent.action.SEND" />
                <data android:type="*/*" />
                <category android:name="android.intent.category.DEFAULT" />
            </intent-filter>
        </activity>
    </application>
</manifest>
```

如果另一个应用创建包含 `ACTION_SEND` 操作的 Intent 并将其传递到 `startActivity()`，则系统可能会启动您的 Activity，以便用户能够草拟并发送电子邮件。

如需了解有关创建 Intent 过滤器的详细信息，请参阅 [Intent 和 Intent 过滤器](https://developer.android.google.cn/guide/components/intents-filters.html)文档。

声明应用要求

Android 设备多种多样，但并非所有设备都提供相同的特性和功能。以防将您的应用安装在缺少应用所需特性的设备上，您必须通过在清单文件中声明设备和软件要求，为该应用支持的设备类型明确定义一个配置文件。其中的大多数声明只是为了提供信息，系统并不会读取它们，但 Google Play 等外部服务会读取它们，以便在用户通过其设备搜索应用时为用户提供过滤功能。

例如，如果您的应用需要相机功能，并使用 Android 2.1（[API 级别](https://developer.android.google.cn/guide/topics/manifest/uses-sdk-element.html#ApiLevels) 7）中引入的 API，您必须在清单文件中声明以下要求，如下方示例所示：

```xml
<manifest ... >
    <uses-feature android:name="android.hardware.camera.any"
                  android:required="true" />
    <uses-sdk android:minSdkVersion="7" android:targetSdkVersion="19" />
    ...
</manifest>
```

通过示例中所述的声明，*没有*相机且 Android 版本*低于* 2.1 的设备将无法从 Google Play 安装您的应用。不过，您可以声明您的应用使用相机，但并不*要求*必须使用。在此情况下，您的应用必须将 [`required`](https://developer.android.google.cn/guide/topics/manifest/uses-feature-element.html#required) 属性设置为 `false`，并在运行时检查设备是否拥有相机，然后根据需要停用任何相机功能。

如需详细了解如何管理应用与不同设备的兼容性，请参阅[设备兼容性](https://developer.android.google.cn/guide/practices/compatibility.html)文档。

应用资源

Android 应用并非仅包含代码，它还需要与源代码分离的资源，如图像、音频文件以及任何与应用的视觉呈现有关的内容。例如，您可以通过 XML 文件定义 Activity 界面的动画、菜单、样式、颜色和布局。借助应用资源，您无需修改代码即可轻松更新应用的各种特性。通过提供备用资源集，您可以针对各种设备配置（如不同的语言和屏幕尺寸）优化您的应用。

对于您在 Android 项目中加入的每一项资源，SDK 构建工具均会定义唯一的整型 ID，您可以利用此 ID 来引用资源，这些资源或来自应用代码，或来自 XML 中定义的其他资源。例如，如果您的应用包含名为 `logo.png` 的图像文件（保存在 `res/drawable/` 目录中），则 SDK 工具会生成名为 `R.drawable.logo` 的资源 ID。此 ID 映射到应用特定的整型数，您可以利用它来引用该图像，并将其插入您的界面。

如果提供与源代码分离的资源，则其中最重要的一个优点在于，您可以提供适用于不同设备配置的备用资源。例如，通过在 XML 中定义界面字符串，您可以将字符串翻译为其他语言，并将这些字符串保存在单独的文件中。然后，Android 系统会根据向资源目录名称追加的语言*限定符*（如为法语字符串值追加 `res/values-fr/`）和用户的语言设置，对您的界面应用相应的语言字符串。

Android 支持许多不同的备用资源*限定符*。限定符是资源目录名称中加入的短字符串，用于定义这些资源适用的设备配置。例如，您应根据设备的屏幕方向和尺寸为 Activity 创建不同的布局。当设备屏幕为纵向（长型）时，您可能想要一种垂直排列按钮的布局；但当屏幕为横向（宽型）时，可以按水平方向排列按钮。如要根据方向更改布局，您可以定义两种不同的布局，然后对每个布局的目录名称应用相应的限定符。然后，系统会根据当前设备方向自动应用相应的布局。

如需详细了解可以在应用中加入的不同资源类型以及如何针对不同设备配置创建备用资源，请阅读[提供资源](https://developer.android.google.cn/guide/topics/resources/providing-resources.html)。如要详细了解最佳做法和设计生产质量的稳健应用，请参阅[应用架构指南](https://developer.android.google.cn/topic/libraries/architecture/guide.html)。

## 4.应用资源

资源是指代码使用的附加文件和静态内容，例如位图、布局定义、界面字符串、动画说明等。

应始终外部化应用资源（例如图像和代码中的字符串），以便单独对其进行维护

还应为特定设备配置提供备用资源，方法是将其进行分组并放入专门命名的资源目录中。在运行时，Android 会根据当前配置使用合适的资源。

根据屏幕尺寸提供不同的界面布局，或根据语言设置提供不同的字符串

外部化应用资源后，您便可使用在项目 `R` 类中生成的资源 ID 来访问这些资源

，`res/` 目录包含所有资源（在子目录中）：一个图像资源、两个布局资源、启动器图标的 `mipmap/` 目录以及一个字符串资源文件。

应用的布局方向。`ldrtl` 是指“布局方向从右到左”。`ldltr` 是指“布局方向从左到右”（默认的隐式值）。

为单组资源指定多个限定符，并使用短划线分隔

不能嵌套备用资源目录

值不区分大小写。在处理之前，资源编译器会将目录名称转换为小写，以免不区分大小写的文件系统出现问题。名称中使用的所有大写字母只是为了便于认读。

每种限定符类型仅支持一个值。

所有资源 ID 都在您项目的 `R` 类中进行定义，该类由 `aapt` 工具自动生成。

编译应用时，`aapt` 会生成 `R` 类，其中包含 `res/` 目录中所有资源的资源 ID。每个资源类型都有对应的 `R` 子类（例如，`R.drawable` 对应所有可绘制对象资源），而该类型的每个资源都有对应的静态整型数（例如，`R.drawable.icon`）。该整型数就是可用来检索资源的资源 ID。

可以以方法参数的形式传递资源 ID，进而在代码中使用资源

```
ImageView imageView = (ImageView) findViewById(R.id.myimageview);
imageView.setImageResource(R.drawable.myimage);
```

```
// Load a background for the current screen from a drawable resource
getWindow().setBackgroundDrawableResource(R.drawable.my_background_image) ;

// Set the Activity title by getting a string from the Resources object, because
//  this method requires a CharSequence rather than a resource ID
getWindow().setTitle(getResources().getText(R.string.main_title));

// Load a custom layout for the current screen
setContentView(R.layout.main_screen);

// Set a slide in animation by getting an Animation from the Resources object
flipper.setInAnimation(AnimationUtils.loadAnimation(this,
        R.anim.hyperspace_in));

// Set the text on a TextView object using a resource ID
TextView msgTextView = (TextView) findViewById(R.id.msg);
msgTextView.setText(R.string.hello_message);
```

界面的行为由基于 Java 的代码来驱动

资源是指文本字符串、布局、声音、图形和您的 Android 应用需要的任何其他静态数据。应用可以包含多组资源，每组资源针对不同的设备配置进行定制。当用户运行应用时，Android 会自动选择并加载与设备最匹配的资源。

如果多个资源文件与设备的配置匹配，则 Android 会遵循一组规则来确定使用哪个文件。在可通过资源目录名称指定的限定符中，**语言区域几乎总是处于优先地位**。

唯一优先于语言区域的限定符是 MCC（移动国家代码）和 MNC（移动网络代码）。

使用 Android 提供的 `Context` 对象查找语言区域

```
    Locale primaryLocale = context.getResources().getConfiguration().getLocales().get(0);
    String locale = primaryLocale.getDisplayName();
    
```



## 5.应用清单文件

## 6.应用权限

检查您是否具有某项权限

```
    if (ContextCompat.checkSelfPermission(thisActivity, Manifest.permission.WRITE_CALENDAR)
            != PackageManager.PERMISSION_GRANTED) {
        // Permission is not granted
    }
    
```

```
    // Here, thisActivity is the current activity
    if (ContextCompat.checkSelfPermission(thisActivity,
            Manifest.permission.READ_CONTACTS)
            != PackageManager.PERMISSION_GRANTED) {

        // Permission is not granted
        // Should we show an explanation?
        if (ActivityCompat.shouldShowRequestPermissionRationale(thisActivity,
                Manifest.permission.READ_CONTACTS)) {
            // Show an explanation to the user *asynchronously* -- don't block
            // this thread waiting for the user's response! After the user
            // sees the explanation, try again to request the permission.
        } else {
            // No explanation needed; request the permission
            ActivityCompat.requestPermissions(thisActivity,
                    new String[]{Manifest.permission.READ_CONTACTS},
                    MY_PERMISSIONS_REQUEST_READ_CONTACTS);

            // MY_PERMISSIONS_REQUEST_READ_CONTACTS is an
            // app-defined int constant. The callback method gets the
            // result of the request.
        }
    } else {
        // Permission has already been granted
    }
    
```

```
    @Override
    public void onRequestPermissionsResult(int requestCode,
            String[] permissions, int[] grantResults) {
        switch (requestCode) {
            case MY_PERMISSIONS_REQUEST_READ_CONTACTS: {
                // If request is cancelled, the result arrays are empty.
                if (grantResults.length > 0
                    && grantResults[0] == PackageManager.PERMISSION_GRANTED) {
                    // permission was granted, yay! Do the
                    // contacts-related task you need to do.
                } else {
                    // permission denied, boo! Disable the
                    // functionality that depends on this permission.
                }
                return;
            }

            // other 'case' lines to check for other
            // permissions this app might request.
        }
    }
    
```

# 二、核心主题

## 1.activity

`Activity` 类是 Android 应用的关键组件，而 Activity 的启动和组合方式则是该平台应用模型的基本组成部分。在编程范式中，应用是通过 `main()` 方法启动的，而 Android 系统与此不同，它会调用与其生命周期特定阶段相对应的特定回调方法来启动 `Activity` 实例中的代码。

`Activity` 类的目的就是促进这种范式的实现。当一个应用调用另一个应用时，调用方应用会调用另一个应用中的 Activity，而不是整个应用。通过这种方式，Activity 充当了应用与用户互动的入口点。您可以将 Activity 实现为 `Activity` 类的子类。

Activity 提供窗口供应用在其中绘制界面。此窗口通常会填满屏幕，但也可能比屏幕小，并浮动在其他窗口上面。通常，一个 Activity 实现应用中的一个屏幕。例如，应用中的一个 Activity 实现“偏好设置”屏幕，而另一个 Activity 实现“选择照片”屏幕。

大多数应用包含多个屏幕，这意味着它们包含多个 Activity。通常，应用中的一个 Activity 会被指定为主 Activity，这是用户启动应用时出现的第一个屏幕。然后，每个 Activity 可以启动另一个 Activity，以执行不同的操作。例如，一个简单的电子邮件应用中的主 Activity 可能会提供显示电子邮件收件箱的屏幕。主 Activity 可能会从该屏幕启动其他 Activity，以提供执行写邮件和打开邮件这类任务的屏幕。

要使应用能够使用 Activity，您必须在清单中声明 Activity 及其特定属性

打开清单文件，并添加 [](https://developer.android.google.cn/guide/topics/manifest/activity-element.html) 元素作为 [](https://developer.android.google.cn/guide/topics/manifest/application-element.html) 元素的子元素

元素唯一的必要属性是 [android:name](https://developer.android.google.cn/guide/topics/manifest/activity-element.html#nm)，该属性用于指定 Activity 的类名称。

[Intent 过滤器](https://developer.android.google.cn/guide/components/intents-filters.html)是 Android 平台的一项非常强大的功能。借助这项功能，您不但可以根据显式请求启动 Activity，还可以根据隐式请求启动 Activity

显式请求可能会告诉系统“在 Gmail 应用中启动‘发送电子邮件’Activity”，而隐式请求可能会告诉系统“在任何能够完成此工作的 Activity 中启动‘发送电子邮件’屏幕”。

当系统界面询问用户使用哪个应用来执行任务时，这就是 intent 过滤器在起作用。

要使用此功能，您需要在 [](https://developer.android.google.cn/guide/topics/manifest/activity-element.html) 元素中声明 [](https://developer.android.google.cn/guide/topics/manifest/intent-filter-element.html) 属性。此元素的定义包括 [](https://developer.android.google.cn/guide/topics/manifest/action-element.html) 元素，以及可选的 [](https://developer.android.google.cn/guide/topics/manifest/category-element.html) 元素和/或 [](https://developer.android.google.cn/guide/topics/manifest/data-element.html) 元素。这些元素组合在一起，可以指定 Activity 能够响应的 intent 类型。例如，以下代码段展示了如何配置一个发送文本数据并接收其他 Activity 的文本数据发送请求的 Activity：

一个 Activity 在其生命周期中会经历多种状态。您可以使用一系列回调来处理状态之间的转换。下面几节将介绍这些回调。

您必须实现此回调，它会在系统创建您的 Activity 时触发。您的实现应该初始化 Activity 的基本组件：例如，您的应用应该在此处创建视图并将数据绑定到列表。最重要的是，您必须在此处调用 `setContentView()` 来定义 Activity 界面的布局。

`onCreate()` 完成后，下一个回调将是 `onStart()`。

`onCreate()` 退出后，Activity 将进入“已启动”状态，并对用户可见。此回调包含 Activity 进入前台与用户进行互动之前的最后准备工作。

onResume()

系统会在 Activity 开始与用户互动之前调用此回调。此时，该 Activity 位于 Activity 堆栈的顶部，并会捕获所有用户输入。应用的大部分核心功能都是在 `onResume()` 方法中实现的。

`onResume()` 回调后面总是跟着 `onPause()` 回调。

onPause()

当 Activity 失去焦点并进入“已暂停”状态时，系统就会调用 `onPause()`。例如，当用户点按“返回”或“最近使用的应用”按钮时，就会出现此状态。当系统为您的 Activity 调用 `onPause()` 时，从技术上来说，这意味着您的 Activity 仍然部分可见，但大多数情况下，这表明用户正在离开该 Activity，该 Activity 很快将进入“已停止”或“已恢复”状态。

如果用户希望界面继续更新，则处于“已暂停”状态的 Activity 也可以继续更新界面。例如，显示导航地图屏幕或播放媒体播放器的 Activity 就属于此类 Activity。即使此类 Activity 失去了焦点，用户仍希望其界面继续更新。

您**不**应使用 `onPause()` 来保存应用或用户数据、进行网络呼叫或执行数据库事务。有关保存数据的信息，请参阅[保存和恢复 Activity 状态](https://developer.android.google.cn/guide/components/activities/activity-lifecycle.html#saras)。

`onPause()` 执行完毕后，下一个回调为 `onStop()`或 `onResume()`，具体取决于 Activity 进入“已暂停”状态后发生的情况。

onStop()

当 Activity 对用户不再可见时，系统会调用 `onStop()`。出现这种情况的原因可能是 Activity 被销毁，新的 Activity 启动，或者现有的 Activity 正在进入“已恢复”状态并覆盖了已停止的 Activity。在所有这些情况下，停止的 Activity 都将完全不再可见。

系统调用的下一个回调将是 `onRestart()`（如果 Activity 重新与用户互动）或者 `onDestroy()`（如果 Activity 彻底终止）。

onRestart()

当处于“已停止”状态的 Activity 即将重启时，系统就会调用此回调。`onRestart()` 会从 Activity 停止时的状态恢复 Activity。

此回调后面总是跟着 `onStart()`。

onDestroy()

系统会在销毁 Activity 之前调用此回调。

此回调是 Activity 接收的最后一个回调。通常，实现 `onDestroy()` 是为了确保在销毁 Activity 或包含该 Activity 的进程时释放该 Activity 的所有资源。

本部分只是简要地介绍了该主题。有关 Activity 生命周期及其回调的详细说明，请参阅 [Activity 生命周期](https://developer.android.google.cn/guide/components/activities/activity-lifecycle.html)。

## 2.架构组件

## 3.导航

## 4.intent和intent过滤器

## 5.界面

## 6.动画和过渡

## 7.图片和图形

## 8.音频和视频

## 9.后台任务

## 10.应用数据和身份

