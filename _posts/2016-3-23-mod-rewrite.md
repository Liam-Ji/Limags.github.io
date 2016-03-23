---
title: 如何检查和打开apache中的mod_rewrite模块
layout: post
tags:
  - apache
  - url
  - mod_rewrite
---
###检查mode_rewrite模块是否已经打开

网上搜一下有很多方法可以检查你的`apache`服务器的`mod_rewrite`模块是否已经打开，这里介绍一种简便的方式。

1. 在你的服务器新建,一般在`/var/www/html/`下，新建php文件，内容为`<?php phpinfo(); ?>`，文件名可以是`index.php`。打开浏览器输入你服务器地址。
2. 你会看到一些信息，搜索关键字`mod_rewrite`。
3. 如果能在`Loaded Modules`区找到关键字，说明模块已经载入，如下图，没看到的话进行下一步自己开启就好了。
[![mod_rewrite](/media/files/2016/03/23/mod_rewrite.jpg)](https://google.com)

###开启mod_rewrite模块
下面演示的是安装在windows环境中apache

1. 在apache安装主目录中找到“conf”文件夹下面的"httpd.conf"文件。
2. 打开文件，定位到`#LoadModule rewrite_module modules/mod_rewrite.so`。
3. 看到这句知道该怎么做了吧，删去前面的`#`，`#`注释标志。
4. 重启`apache server`。
5. 现在就能在刚才的页面看到`mod_rewrite`模块已经开启了。