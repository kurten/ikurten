---
layout: post
status: publish
published: true
title: 阅读memcacheq源码记录
author: Kurten
author_login: kurchan
author_email: chinkurten@gmail.com
author_url: http://kurchan.com
wordpress_id: 95
wordpress_url: http://kurchan.com/?p=95
date: 2011-12-04 12:07:34.000000000 +08:00
categories:
- memcached
tags:
- memcacheq
- bdb
- memcached协议
comments: []
---
越来越觉着大学里学的谭浩强的《C语言程序设计》太狗血了，哎，悔不当初啊。

今天下午闲着看了一下<a href="http://memcachedb.org/memcacheq/">memcacheq</a>这个消息队列的源代码，存储引擎用得<a href="http://www.oracle.com/technetwork/database/berkeleydb/overview/index.html">bdb</a>，<a href="http://www.oracle.com/technetwork/database/berkeleydb/overview/index.html">bdb</a>支持队列方式的数据存储，只不过一个record必须fixed-length，具体能存多大的长度，我没再官方的doc中找到，不过，<a href="http://memcachedb.org/memcacheq/">memcacheq</a>作者说最大消息长度不能超过64K，而且，如果你超过了64K，消息队列就挂了，嗯，这个我碰到过了，超过64K，存入消息队列之后，整个消息队列就得重启。所以，如果你不确定以后业务变更会增加消息体的大小，那么我不建议你使用<a href="http://memcachedb.org/memcacheq/">memcacheq</a> :) 。

<a href="http://memcachedb.org/memcacheq/">memcacheq</a>在内存里维护一个队列的hash，memcacheq.c文件实现了memcached协议，bdb.c文件实现了对于bdb的读写，发觉消息队列持久化用bdb实现实在是很轻量、很简洁，item.c对协议层的封装，操作结构体item。

用<a href="http://libevent.org/">libevent</a>对收到的通信包做callback，包括对bdb做增、删、存操作。bdb也用<a href="http://libevent.org/">libevent</a>，对<a href="http://libevent.org/">libevent</a>没有研究，略过N字 :)。

ps&nbsp;<a href="http://memcachedb.org/memcacheq/">memcacheq</a>测试使用的是python写的memcache.py。

简单，有效的持久化消息队列，性能过得去，抽空我得好好看看C语言，学习一下 :) 复习一下数据结构，以前的早忘记了，而且也没怎么好好学。老外写的<a href="http://book.douban.com/subject/1139336/">《C语言程序设计》</a>这本，不错的。
