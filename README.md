[![Build status](https://ci.appveyor.com/api/projects/status/d9ahvu9u77qjhx9r/branch/master?svg=true)](https://ci.appveyor.com/project/lahma/quartznet-6fcn8/branch/master)
[![NuGet](http://img.shields.io/nuget/v/Quartz.svg)](https://www.nuget.org/packages/Quartz/)
[![NuGet](http://img.shields.io/nuget/vpre/Quartz.svg)](https://www.nuget.org/packages/Quartz/)
[![Join the chat at https://gitter.im/quartznet/quartznet](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/quartznet/quartznet?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

# Quartz.NET - Job Scheduler for the .NET Platform

[http://www.quartz-scheduler.net/](http://www.quartz-scheduler.net/)

## Introduction

This is the README file for Quartz.NET, .NET port of Java Quartz. It supports .NET Core/netstandard 2.0 and .NET Framework 4.5.2 and later.

Quartz.NET is an opensource project aimed at creating a
free-for-commercial use Job Scheduler, with 'enterprise' features.

## Building

* You can build the code by running `build.cmd` (Windows) or `build.sh` (*nix platform)
* You need MSBuild 15 and .NET Core SDK 2.0 to build - easiest to [download Visual Studio 2017 Community](https://www.visualstudio.com/downloads/)
* You need Visual Studio 2017 to open the solution, [Community version](https://www.visualstudio.com/downloads/) should suffice


## Acknowledgements

Following components are being used by core Quartz:

* [LibLog](https://github.com/damianh/LibLog) (MIT) as bridge between different logging frameworks


## License

Licensed under the Apache License, Version 2.0 (the "License"); you may not 
use this file except in compliance with the License. You may obtain a copy 
of the License [here](http://www.apache.org/licenses/LICENSE-2.0).

For API documentation, please refer to [Quartz.NET site](http://quartznet.sourceforge.net/apidoc/3.0/html/).



## 源码分析
![quartznet\src\Quartz\Core\QuartzSchedulerThread.cs]  job调度
![quartznet\src\Quartz\Simpl\TaskSchedulingThreadPool.cs] SemaphoreSlim 信号量 task 



## 新功能
Quartz.NET是一个开源的作业调度框架，是OpenSymphony 的 Quartz API的.NET移植，它用C#写成，可用于winform和asp.net应用中。它提供了巨大的灵活性而不牺牲简单性。你能够用它来为执行一个作业而创建简单的或复杂的调度。它有很多特征，如：数据库支持，集群，插件，支持cron-like表达式等等。
https://www.cnblogs.com/miskis/p/8487634.html
现在Quartz.NET3.0已支持Asp.Net Core，3.0新功能如下：

新功能

具有异步/等待支持的基于任务的作业，内部以异步/等待方式工作
支持.NET Core / netstandard 2.0和.NET Framework 4.5.2及更高版本
通过提供程序名称SQLite-Microsoft支持Microsoft.Data.Sqlite，旧的提供程序SQLite也仍然有效
增加了SQL Server内存优化表和Quartz.Impl.AdoJobStore.UpdateLockRowSemaphoreMOT的初步支持
Common.Logging从相关性中删除
从ILMerge进程中删除的C5集合不再需要
在插件启动时添加对作业调度XML文件的急切验证的支持
在TimeZoneUtil中添加对额外的自定义时区解析器功能的支持
变化

作业和插件现在位于独立的程序集NuGet包Quartz.Jobs和Quartz.Plugins中
ADO.NET提供者名称已被简化，提供者名称没有版本，例如SqlServer-20 => SqlServer
API方法已被重新使用，主要使用IReadOnlyCollection，这隐藏了两个HashSets和List小号
LibLog一直隐藏于内部（ILog等），就像它原本打算的那样
SimpleThreadPool消失了，旧的拥有的线程消失了
调度程序方法已更改为基于任务，请记住等待它们
IJob接口现在返回一个任务
一些IList属性已更改为IReadOnlyList以正确反映意图
SQL Server CE支持已被删除
DailyCalendar现在将日期时间用于排除的日期，并具有ISet接口来访问它们
IObjectSerializer有新的方法，void Initialize（），必须实现
IInterruptableJob取消了上下文的CancellationToken
Quartz API的关键接口和类是：

IScheduler - 与调度程序交互的主要API。
IJob - 您希望由调度程序执行的组件实现的接口。
IJobDetail - 用于定义作业的实例。
ITrigger - 定义执行给定Job的时间表的组件。
JobBuilder - 用于定义/构建定义作业实例的JobDetail实例。
TriggerBuilder - 用于定义/构建触发器实例



## link
[YANGKANG01/QuartzNetJob](https://www.cnblogs.com/miskis/p/8484252.html)   https://github.com/YANGKANG01/QuartzNetJob
[ice-ko/QuartzNetJob](https://www.cnblogs.com/miskis/p/8487634.html)  https://github.com/ice-ko/QuartzNetJob
[](https://github.com/cq-panda/Quartz.NetUI)  vue 
[](https://github.com/demirermustafa/Quartz.Extensions.Microsoft.DependencyInjection) 使用简单