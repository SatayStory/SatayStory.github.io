---
layout: post
title:  "Windows云主机远程连接不上？"
date:   2019-04-08 09:00:00 +0800
categories: config
---
开始→运行→输入`gpedit.msc`, 打开组策略（Group Policy）

在左侧菜单栏

`计算机配置`→`管理模板`→`Windwos组件`→`远程桌面服务`→`远程桌面会话主机`→`安全`

远程（RDP）连接要求使用指定的安全层  

设定为`已启用`，安全层设置为：`RDP`