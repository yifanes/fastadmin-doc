---
title: 目录结构
type: docs
order: 5
---

FastAdmin目录结构如下：

~~~ javascript
FastAdmin项目目录
├── application
│   ├── addons                          //插件扩展目录
│   ├── admin
│   │   ├── command			//控制台命令
│   │   ├── controller
│   │   ├── lang
│   │   │   ├── zh-cn			//控制器对应语言包,按需加载
│   │   │   │   ├── general		
│   │   │   │   ├── index.php
│   │   │   │   └── page.php
│   │   │   └── zh-cn.php		//后台语言包,默认加载
│   │   ├── library
│   │   │   ├── Auth.php		//后台权限验证类
│   │   │   └── traits
│   │   │       └── Backend.php         //后台控制器的Traits
│   │   ├── model
│   │   ├── view
│   │   ├── common.php
│   │   └── config.php
│   ├── api
│   │   ├── controller
│   │   ├── model
│   │   ├── view
│   │   ├── common.php
│   │   └── config.php
│   ├── common
│   │   ├── controller
│   │   │   ├── Api.php			//Api基类
│   │   │   ├── Backend.php		//后台基类
│   │   │   ├── Frontend.php            //前台基类
│   │   ├── library
│   │   ├── model
│   │   └── view
│   ├── extra
│   │   ├── site.php			//站点配置
│   │   ├── upload.php			//上传配置
│   ├── index
│   │   ├── controller
│   │   ├── lang
│   │   ├── model
│   │   └── view
│   ├── build.php
│   ├── command.php
│   ├── common.php
│   ├── config.php
│   ├── constants.php
│   ├── database.php
│   ├── route.php
│   ├── tags.php
├── extend
│   └── fast
│       ├── Auth.php			//Auth权限验证类
│       ├── Date.php			//日期类
│       ├── Form.php			//表单元素生成类
│       ├── Http.php			//Http请求类
│       ├── Menu.php			//后台菜单生成类
│       ├── Pinyin.php			//中文转拼音转换类
│       ├── Random.php			//随机数生成类
│       ├── Rsa.php			//Rsa验证类
│       └── Tree.php			//Tree类
├── public
│   ├── assets
│   │   ├── build			//打包JS、CSS的资源目录
│   │   ├── css				//CSS样式目录
│   │   ├── fonts			//字体目录
│   │   ├── img
│   │   ├── js
│   │   │   ├── backend
│   │   │   └── frontend
│   │   ├── libs			//Bower资源包位置
│   │   └── less			//Less资源目录
│   └── uploads				//上传文件目录
│   ├── index.php                       //应用入口主文件
│   ├── install.php                     //FastAdmin安装引导
│   ├── admin.php                       //后台入口文件,强烈建议修改
│   ├── robots.txt
│   └── router.php
├── runtime						
├── thinkphp				//ThinkPHP5框架核心目录
├── vendor				//Compposer资源包位置
├── .bowerrc				//Bower目录配置文件
├── LICENSE
├── README.md
├── bower.json				//Bower前端包配置
├── build.php					
├── composer.json			//Composer包配置
└── think
~~~
