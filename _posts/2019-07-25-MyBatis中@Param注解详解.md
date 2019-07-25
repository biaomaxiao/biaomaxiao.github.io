---
layout:     post
title:      Mybatis的@Param注解
subtitle:   @Param注解
date:       2019-07-25
author:     abiao
header-img: img/1560822104796.jpg
catalog: true
tags:
    - mybatis
---


## 前言

@Param注解相信都有使用过。但是什么需要添加，何时又不需要添加呢？也许有人会说多个参数需要加，单个不需
要。这样是可能会出现异常的，所以今天和大家讨论这个@Param注解。下面列举几种使用形式：

#### 第一种：方法有多个参数，需要@Param注解
![](/img/20190725104609.png)  
对应XML：
![](/img/20190725104812.png)

#### 第二种：方法参数要使用别名，需要@Param注解
![](/img/20190725104940.png)  
对应XML：
![](/img/20190725105038.png)

#### 第三种：xml中使用了${}，需要@Param注解
![](/img/20190725105122.png)  
对应XML：
![](/img/20190725105201.png)

#### 第四种：动态SQL中使用了参数做条件判断，也需要@Param注解，即使只有一个参数也需要
![](/img/20190725105230.png)  
对应XML：
![](/img/20190725105309.png)
