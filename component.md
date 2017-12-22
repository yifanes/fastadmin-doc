---
title: 组件
type: docs
order: 8
---

## 文件上传

FastAdmin支持将文件或图片直传至第三方云存储服务器而不需要通过本地服务器进行中转
你可以直接在后台安装第三方云存储的插件后使用
在使用第三方云存储功能之前请先注册一个账号并新增一个云储存服务
又拍云：https://console.upyun.com/register/?invite=SyAt3ehQZ
七牛云：https://portal.qiniu.com/signup?code=3l79xtos9w9qq
阿里云：https://promotion.aliyun.com/ntms/act/ambassador/sharetouser.html?userCode=t50mdbun&utm_source=t50mdbun 

插件配置成功后即可在后台直接上传资源到第三方云存储了。

如果在配置了第三方云存储的基础上又想启用本地上传该如何操作呢？
给按钮添加一个属性`data-url="ajax/upload"`即可单独使用本地上传



## 动态下拉列表

FastAdmin中的动态下拉列表使用的是优秀强大的`Selectpage`插件来支持，FastAdmin对其进行了二次开发。
下面介绍一个最基础的动态下拉列表示例，如下
```html
<input id="c-name" data-rule="required" data-source="category/selectpage" class="form-control selectpage" name="row[name]" type="text" value="">
```
其中需要给元素class添加一个`selectpage`，其次需要增加一个`data-source="category/selectpage"`这个属性，`category/selectpage`为我们控制器提交列表的方法

更多的使用方法请参考[Selectpage官方教程](https://terryz.github.io/)

## 富文本编辑器

FastAdmin的富文本编辑器只需要给对应的textarea增加一个class为`editor`即可，FastAdmin在渲染时即会将textarea渲染为富文本编辑器，目前支持`summernote`和`wangeditor`富文本编辑器，需安装对应的插件

## 表单元素生成

FastAdmin封装了几个常用的方法，可以快速的生成表单元素，

1. 生成下拉列表框build_select

```
{:build_select('row[flag]', 'h,i,s', null, ['id'=>'c-flag','class'=>'form-control selectpicker','required'=>''])}
```

2. 生成单选按钮组build_radios

```
{:build_radios('row[enforce]', [1=>"是", 0=>"否"], 1);}
```

3. 生成复选按钮组build_checkboxs

```
{:build_checkboxs('row[game]', [1=>"足球", 0=>"篮球"], 1);}
```