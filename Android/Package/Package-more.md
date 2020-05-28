# 打包进阶-渠道包

## 简述

### 前言

* 为什么要研究怎么打渠道包？因为众多周知的原因，国内渠道多得不得了，国外就一个Google Play，并且生态原因导致谷歌不愿意替我们考虑太多打渠道包相关的功能，国内Coder唯有自立更生

### 常见打渠道包工具

* Packer-ng
* Walle
* 多Flavor
* 自己动手重新打包修改

### 基本流程

Apk解包->修改渠道信息->重新打成Apk->签名->zipalign

## Apktool

更多人一下子就能想到的解包打包方式

### Zip方式打包

为什么使用Zip方式处理Apk？一切源于一句话：Apk文件实际上就是一个zip文件

因为Apktool解包和我们想要的解包不一样，Apktool解包不仅会对Apk进行解压，同时还会把内容根据Android标准进行解析，生成可读性强的内容，即最原始的内容被破坏了，这不是我想要的，我要的是除了我修改过的内容，其余东西都不变，因此，将apk作为zip包的直接解压才是最理想的方案
