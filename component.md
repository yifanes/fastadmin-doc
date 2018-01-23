---
title: 组件
type: docs
order: 11
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



## 图片上传

FastAdmin的图片上传功能非常强大，我们只需要简单的配置即可支持单图或多图上传。

```html
<div class="form-group">
	<label for="c-avatar" class="control-label col-xs-12 col-sm-2">头像:</label>
	<div class="col-xs-12 col-sm-8">
		<div class="input-group">
			<input id="c-avatar" data-rule="" class="form-control" size="50" name="row[avatar]" type="text" value="{$row.avatar}">
			<div class="input-group-addon no-border no-padding">
				<span><button type="button" id="plupload-avatar" class="btn btn-danger plupload" data-input-id="c-avatar" data-mimetype="image/gif,image/jpeg,image/png,image/jpg,image/bmp" data-multiple="false" data-preview-id="p-avatar"><i class="fa fa-upload"></i> 上传</button></span>
				<span><button type="button" id="fachoose-avatar" class="btn btn-primary fachoose" data-input-id="c-avatar" data-mimetype="image/*" data-multiple="false"><i class="fa fa-list"></i> 选择</button></span>
			</div>
			<span class="msg-box n-right" for="c-avatar"></span>
		</div>
		<ul class="row list-inline plupload-preview" id="p-avatar"></ul>
	</div>
</div>
```

我们可以看到这里配置了一个文本框、一个上传按钮、一个选择按钮和一个预览的DIV

| 类型   | 说明                                       |
| ---- | ---------------------------------------- |
| 文本框  | 主要用于接收上传后返回的图片链接，文本框id属性是必选的，这里的id是`c-avatar` |
| 上传按钮 | 主要用于点击后上传文件，有几个属性非常重要，请参考下方的上传按钮属性介绍     |
| 选择按钮 | 主要用于点击后选择已经上传的文件，有几个属性非常重要，请参考下方的选择按钮属性介绍 |
| 预览区域 | 主要用于预览上传或选择文件后的预览。id属性是改造的，这里的id是`p-avatar` |

上传按钮支持属性

| 属性              | 示例值                                      | 说明                             |
| --------------- | ---------------------------------------- | ------------------------------ |
| data-url        | ajax/upload                              | 用于配置上传文件接收的地址                  |
| data-multipart  | {"key1":"value1"}                        | 用于上传时附加额外的参数信息                 |
| data-input-id   | c-avatar                                 | 用于填充返回URL地址的设文本框               |
| data-mimetype   | image/gif,image/jpeg,image/png,image/jpg,image/bmp | 用于过滤允许上传的文件类型，支持mimetype或文件后缀名 |
| data-multiple   | false                                    | 是否支持多图或多文件模式                   |
| data-preview-id | p-avatar                                 | 用于预览返回URL地址的DIV                |
| data-maxsize    | 10M                                      | 用于限制最大可上传的文件大小                 |

选择按钮支持属性

| 属性              | 示例值                                      | 说明                             |
| --------------- | ---------------------------------------- | ------------------------------ |
| data-input-id   | c-avatar                                 | 用于填充返回URL地址的设文本框               |
| data-mimetype   | image/gif,image/jpeg,image/png,image/jpg,image/bmp | 用于过滤允许上传的文件类型，支持mimetype或文件后缀名 |
| data-multiple   | false                                    | 是否支持多图或多文件模式                   |
| data-preview-id | p-avatar                                 | 用于预览返回URL地址的DIV                |

## 动态下拉列表

FastAdmin中的动态下拉列表使用的是优秀强大的`Selectpage`插件来支持，FastAdmin对其进行了二次开发。
下面介绍一个最基础的动态下拉列表示例，如下
```html
<input id="c-name" data-rule="required" data-source="category/selectpage" class="form-control selectpage" name="row[name]" type="text" value="">
```
其中需要给元素class添加一个`selectpage`，其次需要增加一个`data-source="category/selectpage"`这个属性，`category/selectpage`为我们控制器提交列表的方法

FastAdmin的Selectpage列表中`显示字段`默认读取的是`name`字段，如果我们返回的列表中不包含`name`字段，将无法展现下拉列表数据。此时我们需要添加使用`data-field="你要显示的字段"`即可。

FastAdmin的Selectpage列表中`主键字段`默认读取的是`id`字段，如果我们的主键不是`id`字段，则我们可以添加并使用`data-primary-key="你的主键ID字段"`来修改。

> FastAdmin在生成CRUD时会对包含下划线的字段默认生成selectpage模式，比如`user_id`将自动生成`data-source="user/index"`，默认读取的是`id`和`name`字段，如果需要修改，请参考上方的修改方法。

更多的使用方法请参考[Selectpage官方教程](https://terryz.github.io/)

## 富文本编辑器

FastAdmin的富文本编辑器只需要给对应的textarea增加一个class为`editor`即可，FastAdmin在渲染时即会将textarea渲染为富文本编辑器，目前支持`summernote`、`wangeditor`和`ueditor`富文本编辑器，需安装对应的插件即可正常使用。

> 在安装完对应的富文本插件后切记启用、刷新插件缓存并清除浏览器缓存后才生效。

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