---
layout: post
title:  "Learn Laravel"
date:   2016-06-14 19:00:00 +0100
categories: PHP 
---
<h1>关于Laravel</h1>
Laravel是较新而且方便的PHP框架。开始接触Laravel纯粹是因为实习原因需要快速搭建一个站点。本文记录Laravel使用的心得。然而并不会从入门开始介绍，仅仅介绍这个MVC框架中一些自己摸索了许久的关键概念。

<h2>模块和数据表</h2>

在Laravel里，可以使用ORM进行便捷的数据访问。即把每一个数据表转为一个PHP对象，通过：**$对象名->属性** 来访问 **$表名->字段**

为了使得Laravel知道哪个模块应该和哪个数据表对应，在命名数据表和对象的时候有一定限制。
例子：创建一个商品(id，名字，价格，描述)在数据库中，并在网页里可以访问。

<strong>Step1:</strong>
	
	php artisan make:model product

这条语句在Laravel里创建了一个模块，名字为product

<strong>Step2:</strong>

	php artisan make:migration create_products_table
这条语句在Laravel里创建了一个数据迁移。

⚠️数据迁移的命名最好是create_xxx_table，这样生成的数据迁移的名字将会是CreateXxxTable 

⚠️数据迁移是一个特殊的类，继承自Migration。

⚠️数据迁移整一个文件不容易删除，但是数据迁移里的数据库表的结构可以轻易使用migrate 和rollback 修改

<strong>Step3:</strong>

此时我们有了数据迁移和模块，便能够以对象的方式直接操纵数据。

（未完）
