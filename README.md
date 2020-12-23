[![Downloads](https://img.shields.io/nuget/dt/Quartz)](#)
[![Build status](https://ci.appveyor.com/api/projects/status/d9ahvu9u77qjhx9r/branch/master?svg=true)](https://ci.appveyor.com/project/lahma/quartznet-6fcn8/branch/master)
[![NuGet](http://img.shields.io/nuget/v/Quartz.svg)](https://www.nuget.org/packages/Quartz/)
[![NuGet pre-release](http://img.shields.io/nuget/vpre/Quartz.svg)](https://www.nuget.org/packages/Quartz/)
[![MyGet pre-release](https://img.shields.io/myget/quartznet/vpre/Quartz)](#)
[![Join the chat at https://gitter.im/quartznet/quartznet](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/quartznet/quartznet?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

# Quartz.NET - Job Scheduler for the .NET Platform

[http://www.quartz-scheduler.net/](http://www.quartz-scheduler.net/)

## Introduction

This is the README file for Quartz.NET, .NET port of Java Quartz. It supports .NET Core/netstandard 2.0 and .NET Framework 4.6.1 and later.

Quartz.NET is an opensource project aimed at creating a free-for-commercial use Job Scheduler, with enterprise features.

## Installation

* [Stable builds from NuGet](https://www.nuget.org/packages?q=owner%3AQuartz.NET)
* Pre-release builds from MyGet feed: https://www.myget.org/F/quartznet/api/v3/index.json

## Building

* You can build the code by running `build.cmd` (Windows) or `build.sh` (*nix platform)
* You need MSBuild 16 and .NET Core SDK 3.1 to build - easiest to [download Visual Studio 2019 Community](https://www.visualstudio.com/downloads/)
* You need Visual Studio 2019 to open the solution, [Community version](https://www.visualstudio.com/downloads/) should suffice

## Acknowledgements

Following components are being used by core Quartz:

* [LibLog](https://github.com/damianh/LibLog) (MIT) as bridge between different logging frameworks


## License

Licensed under the Apache License, Version 2.0 (the "License"); you may not 
use this file except in compliance with the License. You may obtain a copy 
of the License [here](http://www.apache.org/licenses/LICENSE-2.0).

For API documentation, please refer to [Quartz.NET site](http://quartznet.sourceforge.net/apidoc/3.0/html/).

## 排除某些时间
CronCalendar:使用表达式排除某些时间段不执行
DailyCalendar：指定的时间范围内的每一天不执行
HolidayCalendar：排除节假日
MonthlyCalendar：排除月份中的数天
WeeklyCalendar：排除星期中的一天或多天

- [](.\\src\Quartz.Examples\08_ExcludeTimePeriodsUsingCalendars\ExcludeTimePeriodsUsingCalendarsExample.cs)
- [](.\quartznet\src\Quartz\Impl\Calendar)



## 源码分析
![quartznet\src\Quartz\Core\QuartzSchedulerThread.cs]  job调度
![quartznet\src\Quartz\Simpl\TaskSchedulingThreadPool.cs] SemaphoreSlim 信号量 task 
![quartznet\src\Quartz\Util\QueuedTaskScheduler.cs]  216 线程调度方法



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
- [](https://gitee.com/tm2002/FI.BatchJob)支持Windows，linux，和Docker 部署 比较完整
- [YANGKANG01/QuartzNetJob](https://www.cnblogs.com/miskis/p/8484252.html)   https://github.com/YANGKANG01/QuartzNetJob
[ice-ko/QuartzNetJob](https://www.cnblogs.com/miskis/p/8487634.html)  https://github.com/ice-ko/QuartzNetJob
[](https://github.com/cq-panda/Quartz.NetUI)  vue 
[](https://github.com/demirermustafa/Quartz.Extensions.Microsoft.DependencyInjection) 使用简单
[](https://github.com/ypxf369/TaskManagerQuartzNetCore) 基于Quartz.Net 3.0的分布式Asp.Net Core的任务调度管理平台	

支持Cron 表达式设置任务，支持任务暂停，任务状态实时更新，和任务失败邮件通知功能。 支持传入任务参数，任务执行Notes。 内置的sqlite 数据库保存任务和任务执行的历史记录。
内置的历史记录定期清除功能，内置邮件发送队列，内部集成的Dapper 可以用来处理任务数据。
内置了2个例子任务,可以参照他们完成其他复杂的任务。
[](https://github.com/zhaopeiym/quartzui)  docker 前端不好用
[](https://github.com/hey-hoho/ScheduleMasterCore) ScheduleMaster是一个开源的分布式任务调度系统，它基于.NET Core 3.1平台构建，支持跨平台多节点部署运行
[](https://github.com/fluentscheduler/FluentScheduler)简单调度，没有cronExpression
[](https://github.com/kdcllc/CronScheduler.AspNetCore)
[])(https://github.com/dahall/taskscheduler)  wrapper for the Windows Task Scheduler. It aggregates the multiple versions, provides an editor and allows for localization
Separate, functionally identical, libraries for .NET 2.0, 3.5, 4.0, 4.52 and .NET Standard 2.0  调用cmd 没有cronExpression
[](https://github.com/R-Suite/R.Scheduler)