---
title: Android Activity生命周期
description: Android Activity生命周期
categories: Android
tags: Android
locate: 成都
---

# Android Activity生命周期

Android Activity 是 Android 应用程序的重要组成部分，代表应用程序中的一个屏幕。当用户在应用程序中执行某些操作时，例如启动应用程序或切换到不同的屏幕，Android 操作系统会按照特定的顺序调用 Activity 的生命周期方法。

Activity 的生命周期方法包括以下七个方法：

<ol>
<li>onCreate()</li>
<li>onStart()</li>
<li>onResume()</li>
<li>onPause()</li>
<li>onStop()</li>
<li>onRestart()</li>
<li>onDestroy()</li>
</ol>

这些方法定义了 Activity 的状态和生命周期，你可以使用这些方法来执行一些操作并处理应用程序的状态。
## 1. onCreate()

onCreate() 方法是 Activity 生命周期中的第一个方法，当 Activity 被创建时调用。在此方法中，你可以初始化应用程序中的各种变量和组件。例如，你可以在此方法中设置布局、创建视图、初始化控件等。

``` kotlin
class MainActivity : AppCompatActivity() {

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)
        Log.d(TAG, "onCreate")
    }
}
```
## 2. onStart()

onStart() 方法是 onCreate() 方法之后调用的方法，当 Activity 开始可见时调用。在此方法中，你可以开始执行一些操作并设置 Activity 的状态。

```kotlin
class MainActivity : AppCompatActivity() {

    override fun onStart() {
        super.onStart()
        Log.d(TAG, "onStart")
    }
}
```

## 3. onResume()

onResume() 方法是 Activity 生命周期中的第三个方法，当 Activity 可见并与用户交互时调用。在此方法中，你可以恢复 Activity 的状态并开始执行应用程序的主要逻辑。

```kotlin
class MainActivity : AppCompatActivity() {

    override fun onResume() {
        super.onResume()
        Log.d(TAG, "onResume")
    }
}
```

## 4. onPause()

onPause() 方法是 Activity 生命周期中的第四个方法，当 Activity 即将暂停或停止时调用。在此方法中，你可以保存 Activity 的状态和数据，并停止 Activity 中正在运行的操作。

```kotlin
class MainActivity : AppCompatActivity() {

    override fun onPause() {
        super.onPause()
        Log.d(TAG, "onPause")
    }
}
```

## 5. onStop()

onStop() 方法是 Activity 生命周期中的第五个方法，当 Activity 不再可见时调用。在此方法中，你可以停止 Activity 中正在运行的操作，并保存 Activity 的状态和数据。

```kotlin
class MainActivity : AppCompatActivity() {

    override fun onStop() {
        super.onStop()
        Log.d(TAG, "onStop")
    }
}
```

## 6. onRestart()

onRestart() 方法是 Activity 生命周期中的第六个方法，当 Activity 从停止状态重新启动时调用。在此方法中，你可以恢复 Activity 的状态和数据，并重新启动 Activity 中的操作。

``` kotlin
class MainActivity : AppCompatActivity() {

    override fun onRestart() {
        super.onRestart()
        Log.d(TAG, "onRestart")
    }
}
```

## 7. onDestroy()

onDestroy() 方法是 Activity 生命周期中的最后一个方法，当 Activity 被销毁时被调用。在此方法中，你可以停止 Activity 中正在运行的操作、释放资源并清理 Activity 的状态。

```kotlin
class MainActivity : AppCompatActivity() {

    override fun onDestroy() {
        super.onDestroy()
        Log.d(TAG, "onDestroy")
    }
}
```

## 生命周期方法调用顺序
![调用顺序](https://lees-1301878338.cos.ap-chengdu.myqcloud.com/activity_lifecycle.png)


当 Activity 首次启动时，Android 系统会按照如下顺序调用生命周期方法：

<ol>
<li>onCreate()</li>
<li>onStart()</li>
<li>onResume()</li>
</ol>

当 Activity 不再可见时，Android 系统会按照如下顺序调用生命周期方法：

<ol>
<li>onPause()</li>
<li>onStop()</li>
<li>onDestroy()</li>
</ol>

当用户旋转屏幕或按下返回按钮时，Android 系统会按照如下顺序调用生命周期方法：

<ol>
<li>onPause()</li>
<li>onStop()</li>
<li>onDestroy()</li>
<li>onCreate()</li>
<li>onStart()</li>
<li>onResume()</li>
</ol>

## 总结

Activity 生命周期方法定义了 Activity 的状态和生命周期。了解 Activity 生命周期方法的调用顺序以及如何使用这些方法可以帮助你更好地管理应用程序的状态和行为。在编写应用程序时，请务必了解 Activity 生命周期并根据应用程序的需要实现适当的逻辑。