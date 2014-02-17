---
layout: post
title: Decompiling Android APK
category: Android
---

APK其实是一个压缩文件, 首先使用压缩工具解压.
解压出来的文件夹里面有classes.dex 文件, 反编译到java的.class二进制码，然后从.class二进制码反编译到java源码.

使用的工具: 
![dex2jar](http://code.google.com/p/dex2jar/downloads/list)
![JD-GUI](http://java.decompiler.free.fr/?q=jdgui)

