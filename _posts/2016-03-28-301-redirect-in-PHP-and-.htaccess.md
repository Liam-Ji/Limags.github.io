---
title: 在PHP和.htaccess中实现301重定向
layout: post
tags:
  - redirect
  - PHP
  - .htaccess
  - 301
---


### 什么是301重定向？

一般来说，搜索引擎收录网站上面的页面时都会给网页评级，PR(PageRank)值也是搜索引擎测评一个网页“重要性”的一种方法。你在搬迁网站的过程中会把文件转移到一个新的域名下，这种情况，访问旧域名的访客获取不到你的网站文件，只会看到“Error 404 – File not found”页面，有一段时间你的网站评级会因此遭受损失。解决办法就是通知旧域名的“来访者”你的网站已经永久迁移了（301重定向）。这是最有效率的，也是搜索引擎和用户友好的网页重定向方法。

### 为什么需要301重定向？

当你用浏览器访问"baidu.com"的时候发生了什么？你的浏览器重定向到了"www.baidu.com"，这就是使用了301重定向的效果。那么问题来了，为什么会需要这种功能呢？加入不使用301重定向，那么"baidu.com"和"www.baidu.com"会是两个完全不同的域名。这种情况下，搜索引擎爬虫会从两个不同的URL爬到完全一样的内容，会触发搜索引擎的重复内容惩罚机制。

### 在PHP中实现301重定向

如果想让某个网页重定向到其他文件，将下面的代码放在你的源文件（未转移之前的旧文件）的头部。

	<?php
	header('HTTP/1.1 301 Moved Permanently');
	header('Location: http://www.new-domain.com/new-file-name.php');
	?>

如果想让不带'www'前缀的URL重定向到带'www'前缀的域名需要将下面的代码插入到网站所有页面的的头部。

	<?php
	if (substr(getenv('HTTP_HOST'),0,3) != 'www')
	{
	    header('HTTP/1.1 301 Moved Permanently');
	    header('Location:http://www.'.$_SERVER['HTTP_HOST'].$_SERVER['REQUEST_URI']);
	}
	?>

### 使用.htaccess文件实现301重定向

将下面的代码插入到网站根目录下的.htaccess文件。注意该文件只在apche服务器上搭建的网站中有用。

	RewriteEngine On
	RewriteCond %{HTTP_HOST} ^domain\.com
	RewriteRule (.*) http://www.domain.com/$1 [R=301,L]