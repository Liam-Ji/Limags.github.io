---
title: 5个实用的.htaccess重写方法
layout: post
tags:
- redirect
- .htaccess
- url
---
如果你在找有关URL重写的方法，这篇短文有可能能帮到你。下面你会学到利用.htaccess文件进行URL重写的5个小例子。如果你还不熟悉URL重写的概念请参考[使用URL重写来隐藏.php扩展名文件using .htaccess](http://limags.com/2016/03/24/Hide-php-extension-with-url-rewriting.html)。

现在让我们来看看这些例子是如何实现的。

### 1.重写“test.php?id=10”文件到“test.php?id=10”文件

这个简单的重定向将带.php扩展名的文件从浏览器地址栏掩藏，并且把动态URL(带“？”字符)转变成静态URL。

	RewriteEngine on
	RewriteRule ^test-([0-9]+)\.html$ test.php?id=$1

### 2.重写“test.php?id=10”文件到“mysite/test/10.html”文件

SEO专家建议将主要关键词显示在URL中。这个技巧就是教会你如何在URL中显示你网页的名字

	RewriteEngine on
	RewriteRule ^test/([a-zA-Z0-9_-]+)/([0-9]+)\.html$ test.php?id=$2

### 3.将不带“wwww”前缀的URL重定向到带“www”前缀的URL

你在浏览器地址栏输入“google.com”时，会被重定向到“www.google.com”。想要在自己的网站上实现同样的效果只需把下面的代码插入到.htaccess文件。这种重定向有什么作用呢？请参看[在PHP和.htaccess中实现301重定向](http://limags.com/2016/03/28/301-redirect-in-PHP-and-.htaccess.html)。	

	RewriteEngine On
	RewriteCond %{HTTP_HOST} ^optimaxwebsolutions\.com$
	RewriteRule (.*) http://www.optimaxwebsolutions.com/$1 [R=301,L]
	
### 4.重写yoursite.com/index.php?username=admin到yoursite.com/xyz

实现这样的效果只需要加入下面这段

	RewriteEngine On
	RewriteRule ^([a-zA-Z0-9_-]+)$ user.php?username=$1
	RewriteRule ^([a-zA-Z0-9_-]+)/$ user.php?username=$1

### 5.将域名重定向到网站根目录下的子文件夹里面的文件

假设你重新调整了你的网站结构，将原来根目录下的文件移动到根目录下的new文件夹。新的网站可以用“test.com/new”域名来访问。在网站根目录下新建.htaccess文件添加如下代码，可以实现输入“test.com”域名就能访问new文件夹下的内容。

	RewriteEngine On
	RewriteCond %{HTTP_HOST} ^test\.com$ [OR]
	RewriteCond %{HTTP_HOST} ^www\.test\.com$
	RewriteCond %{REQUEST_URI} !^/new/
	RewriteRule (.*) /new/$1
