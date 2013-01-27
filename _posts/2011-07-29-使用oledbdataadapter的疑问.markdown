---
layout: post
status: publish
published: true
title: 使用oledbdataadapter的疑问
author: Kurten
author_login: kurchan
author_email: chinkurten@gmail.com
author_url: http://kurchan.com
wordpress_id: 15
wordpress_url: http://kurchan.com/?p=15
date: 2011-07-29 03:40:54.000000000 +08:00
categories: []
tags: []
comments: []
---

最近一个项目，在使用oledbdataadapter获取access数据库中的表数据时，无缘无故会丢失一个字段的数据(使用jet引擎)。同样的代码，调试的时候居然没有问题，但是直接运行，不进行断点调试没有问题。想不通到底是.net的问题，还是access的问题。找相关的资料居然没有。不过，总会是那个有问题的(呵呵，好像是废话)。

很类似的，以前在获取excel的数据时(也是使用jet引擎)，会丢失一些数据，那是因为这一列中既有数字和文本，jet无法识别，将单元格格式设置为文本就可以了。

不过，access数据库至少不会出现这样的问题。而且，明明都是文本数据，居然获取出来是空的，很伤脑筋。不过，还是另外找了种方法解决这个问题，呵呵。

PS：前几天看一个小学奥数题，大意是如果两个正整数的积可以整除他们的和，比如70和30，那么这一对数就称为好数，那么1到16之间有多少对好数？

我用python写了一个很简略的程序，算了一下：
<pre>#coding=gbk
'''
Created on 2011-2-18
求好数
@author: KURTEN
'''

i = 1
max = 16
xx=[]
while i &amp;lt; max:
         xx.append(i)
         i = i + 1

yy = xx
for x in xx:
    for y in yy:
        if x &amp;lt; y:
            if ((x * y) % (x + y) == 0):
                print "好数[%d,%d]" %(x,y)</pre>
由此可以计算出4对好数，程序是简单的，不过，如果离开计算机，让我去手算，估计我得弄半天吧。想想小朋友们还是真可怜，不过，我小时候也是，被奥数残害，其实啊，没多大意义。

能够简化复杂得工作，代码，确实是个好东西。码农得日子，也就这么单调得乐趣了。昨天元宵，吃了自己煮得芝麻馅的汤圆，总比不过在家的日子惬意。人，总要随着自己喜欢的道路走的，也要选择自己喜欢做的事情。就算离乡背井也无妨嘛。

20110512：这里查明原来不同的引擎同时访问access库，有可能得到的数据不一定一致。估计是因为内部缓存的问题，或者就是访问引擎内部bug，有或者是其他灵异事件。这个我也就不得而知了。
