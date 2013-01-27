---
layout: post
status: publish
published: true
title: 修补bug，继续search
author: Kurten
author_login: kurchan
author_email: chinkurten@gmail.com
author_url: http://kurchan.com
wordpress_id: 25
wordpress_url: http://kurchan.com/?p=25
date: 2011-07-29 03:45:49.000000000 +08:00
categories: []
tags: []
comments: []
---
昨天，因为<a href="http://www.djangoproject.com/" target="_blank">django</a>，于是又查看了一下<a href="http://sourceforge.net/projects/mysql-python/" target="_blank">mysqldb</a>无法使用的问题，原来啊，是不支持mysql5.5。今天，换了5.1。对于mac下root啥的密码设置，我原先走了些弯路，其实mysql官方文档有很详细的<a href="http://dev.mysql.com/doc/refman/5.1/zh/installing.html" target="_blank">说明的</a>。（关于我如何在mac上卸载mysql，请看<a href="http://blog.merlyle.com/?p=34" target="_blank">这里</a>）试了一下，果然可以了。人生就是有那么些杯催事，<a href="http://nginx.org/" target="_blank">nginx</a>与php-cgi配置也是如此，换成了从源代码安装，然后配置一下就可以玩了（配置方式见<a href="http://blog.s135.com/post/297/" target="_blank">这里</a>）。

说起<a href="http://nginx.org/" target="_blank">nginx</a>还是相当不错的一个<a href="http://en.wikipedia.org/wiki/Web_server" target="_blank">web server</a>。只不过，对于python，部署起来还是比较麻烦。虽然有uwsgi，但是总体上还是比<a href="http://www.php.net/" target="_blank">php</a>发布部署麻烦许多，只是，对于其他部署方式会好许多吧。不知道google对于<a href="http://www.python.org/" target="_blank">python</a>的app部署，有什么好的方法。

发觉个事，我租的justhost的主机貌似不支持<a href="http://www.python.org/" target="_blank">python</a>，不过用了优惠50％的，还是很赞了的。以后每年续费都是42美刀，还算划算。

近来<a href="http://www.w3.org/html/logo/" target="_blank">html5</a>越来越火热了，各大浏览器都开始支持<a href="http://www.w3.org/html/logo/" target="_blank">html5</a>，总体上，silverlight与flash还是很杯具的。在我看来，ms花在开发silverlight的时间上，还不如多花点时间把IE折腾好。富客户端神马的，都是浮云。浏览器引擎才是王道啊。

现在么，都是平台互相PK，其实啊，app才是王道。

搞了一年多GIS二次开发，厌烦了。前几天去创维面试，也是搞二次开发的，那总工说，二次开发神马的，就是调调别人的接口，没什么的。也对啊，二次开发么，专注于业务了，技术神马的，除非大项目，否则么，就这么过去了。

喜欢的么，web方向的，产品经理啥的，没人要啊。杯催。搞服务器端的开发也行啊。给点时间，哥就可以上手的么。待遇神马的都是浮云啊，男人么，干自己喜欢的事情，最重要！
