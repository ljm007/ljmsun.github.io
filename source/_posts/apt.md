---
title: apt切换为annotationProcessor
date: 2017-08-09 14:53:07
---
Android Gradle插件2.2版本发布后，Android 官方提供了annotationProcessor来代替android-apt，annotationProcessor同时支持 javac 和 jack 编译方式，而android-apt只支持 javac 方式。同时android-apt作者宣布不在维护。
现在Jack官方也不在支持了，不过使用Jack的人估计也没有多少。


## android-apt 切换 annotationProcessor 步骤
####  Android Gradle 插件版本升级到 2.2 及以上
```
buildscript {
     repositories {
         jcenter()
     }
     dependencies {
         classpath 'com.android.tools.build:gradle:2.3.0'
     }
 }
```
#### 删除之前的apt配置
```
buildscript {
     repositories {
         jcenter()
     }
     dependencies {
         classpath 'com.neenbedankt.gradle.plugins:android-apt:1.8'
     }
 }
```
```
 apply plugin: 'com.neenbedankt.android-apt'
```
#### 将之前使用apt的依赖改成annotationProcessor

 之前的配置：
```
apt 'com.jakewharton:butterknife-compiler:8.4.0'
```
 改为：
```
annotationProcessor 'com.jakewharton:butterknife-compiler:8.4.0'
```



