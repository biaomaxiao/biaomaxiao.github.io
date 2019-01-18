---
layout:     post
title:      Windows下搭建Git服务器
subtitle:   一起来看看怎么搭建一个git服务器吧
date:       2019-1-18
author:     abiao
header-img: img/post-bg-universe.jpg
catalog: true
tags:
    - Git
---


## 前言

Git没有客户端服务器端的概念，但是要共享Git仓库，就需要用到SSH协议（FTP , HTTPS , SFTP等协议也能实现Git共享，此文档不讨论），但是SSH有客户端服务器端，所以在windows下的开发要把自己的Git仓库共享出去的话，就必 须做SSH服务器
Git服务现在独树一帜，相比与SVN有更多的灵活性，最流行的开源项目托管网站Github上面，如果托管开源项目，那么就是免费使用的，但是闭源的项目就会收取昂贵的费用，如果你不缺$，那么不在本文讨论的范围内，既然这样，我们可以自己搭建我们的Git服务器。
国内使用Windows Server平台的用户占大多数，那么本文就来讨论如何在Windows平台下搭建Git服务器。


### 1.下载Java，下载地址 [http://www.java.com/zh_CN/](http://www.java.com/zh_CN/)
根据系统位数下载，32的下载32的，64的下载64的,下载之后配置环境变量，进入dos命令，键入java，javac查看是否
成功配置。
### 2.下载Gitblit.下载地址：[http://www.gitblit.com/](http://www.gitblit.com/)
![mark](http://plii5zn2f.bkt.clouddn.com/image/20190118/qzBBfWq3OOdG.png?imageslim)
解压缩下载的压缩包即可，无需安装。
![mark](http://plii5zn2f.bkt.clouddn.com/image/20190118/tTVSEIsjA0Yc.png?imageslim)

### 3.创建用于存储资料的文件夹
![mark](http://plii5zn2f.bkt.clouddn.com/image/20190118/TQrsDSLkzNxs.png?imageslim)

### 4.配置gitblit.properties 文件

1. 找到Git目录下的data文件下的defaults.properties文件，“记事本”打开。
![mark](http://plii5zn2f.bkt.clouddn.com/image/20190118/iSDFShw9PqU8.png?imageslim)
2. 找到git.repositoriesFolder(资料库路径)，赋值为第七步创建好的文件目录。
![mark](http://plii5zn2f.bkt.clouddn.com/image/20190118/1iNyOMNaikcb.png?imageslim)
3. 找到server.httpPort，设定http协议的端口号。
![mark](http://plii5zn2f.bkt.clouddn.com/image/20190118/KGvLDdJQHBuJ.png?imageslim)
4. 找到server.httpBindInterface，设定服务器的IP地址。这里就设定你的服务器IP或本地IP。
![mark](http://plii5zn2f.bkt.clouddn.com/image/20190118/M30QlalYwweQ.png?imageslim)
5. 找到server.httpsBindInterface，设定为localhost。
![mark](http://plii5zn2f.bkt.clouddn.com/image/20190118/MmBihOJnJDJT.png?imageslim)
6. 保存，关闭文件。

### 5.运行gitblit.cmd 批处理文件
1、找到bitblit目录中的gitblit.cmd文件，双击。
![mark](http://plii5zn2f.bkt.clouddn.com/image/20190118/jNjc0j9R8VKz.png?imageslim)
2.运行结果如下，运行成功。
![mark](http://plii5zn2f.bkt.clouddn.com/image/20190118/Er0HgeSnVDR9.png?imageslim)

### 6.在浏览器中打开,现在就可以使用GitBlit了
![mark](http://plii5zn2f.bkt.clouddn.com/image/20190118/B0KmlUnsIWaz.png?imageslim)

