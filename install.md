---
title: 安装
type: docs
order: 2
---

## **环境要求**

~~~
PHP >= 5.5.0
Mysql >= 5.5.0
Apache 或 Nginx
PDO PHP Extension
MBstring PHP Extension
CURL PHP Extension
Node.js (可选,用于安装Bower和LESS,同时打包压缩也需要使用到)
Composer (可选,用于管理第三方扩展包)
Bower (可选,用于管理前端资源)
Less (可选,用于编辑less文件,如果你需要增改css样式，最好安装上)
~~~

## **命令行安装**

强烈建议使用命令行安装，因为采用命令行安装的方式可以和FastAdmin随时保持更新同步。使用命令行安装请提前准备好Git、Node.js、Composer、Bower环境，我们为Windows下开发者准备了一个简单的视频安装教程( http://www.fastadmin.net/video/install.html )，可跟着教程一步一步安装。Linux下FastAdmin的安装请使用以下命令进行安装。

1. 克隆FastAdmin到你本地
   `git clone https://git.oschina.net/karson/fastadmin.git `
2. 进入目录
   `cd fastadmin `
3. 下载前端插件依赖包
   `bower install `
4. 下载PHP依赖包
   `composer install`
5. 一键创建数据库并导入数据
   `php think install`

## **源代码安装**

1. 下载FastAdmin完整包解压到你本地
  https://gitee.com/karson/fastadmin/attach_files
   还可以加QQ群([636393962](https://jq.qq.com/?_wv=1027&k=487PNBb)) 在群共享下载
2. 将你的虚拟主机绑定到`/yoursitepath/public`目录
3. 访问 http://www.yourwebsite.com/install.php 按指示进行安装

## **常见问题**
1. 如果使用`命令行安装`则默认密码是`123456`
2. 提示`请先下载完整包覆盖后再安装`，说明你是直接从仓库下载的代码，请从附件或群共享中下载完整包覆盖后再进行安装
3. 执行`php think install`时出现`Access denied for user ...`，请确保数据库服务器、用户名、密码配置正确
4. 执行`php think install`时报不是内部或外部命令? 请将`php.exe`所在的目录路径加入到环境变量PATH中
5. 使用命令行安装时可能会由于你所处的网络环境导致资源下载不完整，请下载完整包覆盖后再尝试安装。
6. 如果提示`当前权限不足，无法写入配置文件application/database.php`，请检查`database.php`是否可读，还有可能是当前安装程序无法访问父目录，请检查PHP的`open_basedir`配置
7. 如果提示`找不到fastadmin.fa_admin`表或表不存在，请检查你的MySQL是否开启了支持`innodb`。

* * * * *
遇到问题到[社区](http://forum.fastadmin.net) 或QQ群：[636393962](https://jq.qq.com/?_wv=1027&k=487PNBb) 反馈




