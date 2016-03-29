---
title: 使用URL重写来隐藏.php扩展名文件
layout: post
tags:
  - .htaccess
  - .php
  - URL
---



> 如何让用户在实际访问<font color='#800080'>product.php</font>文件时，地址栏上显示的确是<font color='#800080'>product.html</font>?或者将<font color='#800080'>product.php?id=5</font>显示成<font color='#800080'>product-5.html</font>?

---

### URL重写有什么好处？

当搜索引擎访问到带有类似<font color='#800080'>product.php?id=5</font>字符串的URL时，并不会给这种URL多少权重，因为它是动态的URL。因此我们希望将动态的URL形式转换成静态的URL。使用URL重写就能够实现，实际访问<font color='#800080'>product.php?id=5</font>文件的同时，地址栏上显示的是<font color='#800080'>product-5.html</font>。这种静态URL也叫做SEO友好URL。

### URL重写的前提

你的apache server必须已经载入[mod_rewrite](http://httpd.apache.org/docs/1.3/mod/mod_rewrite.html)模块，FollowSymLinks选项处于开启状态，否则会遇到<font color='#800080'>500 Internal Sever Error</font>错误。如果你不知道mod_rewrite请看[如何检查和打开apache中的mod_rewrite模块](http://programmemo.com/blog/2016/03/23/257/)。

---

### 利用URL重写实现SEO有好的URL

在你网站的根目录下面找到<font color='#800080'>.htaccess</font>文件，没有的话新建一个，插入下面的内容。

	Options +FollowSymlinks
	RewriteEngine on
	RewriteRule ^(.*)\.htm$ $1.php [nc]

里面一串奇怪的字符是正则表达式匹配字符串的内容，这段代码将会把对html文件的访问定位到同名的php文件。举个例子，当浏览器地址栏显示URL为http://localhost/test.htm，实际上访问的文件是http://localhost/test.php。RewriteRule中包含一个正则表达式（^和$之间的内容），和字符串$1(表示本条RewriteRule中第一个正则表达式)，最后<font color='#800080'>[NC]</font>表示忽略大小写。

	Options +FollowSymlinks
	RewriteEngine on
	RewriteRule ^product-([0-9]+)\.html$ products.php?id=$1

上面的内容就可以把<font color='#800080'>product.php?id=5</font>文件重写到<font color='#800080'>product-5.html</font>。例如，当浏览器地址栏显示URL为http://localhost/product-5.html，实际上访问的文件是http://localhost/product.php?id=5。

通过上面的两个小例子可以看出，这个重写功能非常实用，几乎可以任意改变我们网站的文件和目录结构，只要修改.htaccess文件就可以使用原来的URL，有利于搜索引擎的搜录。