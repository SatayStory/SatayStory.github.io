---
layout: post
title:  "Jekyll build warning"
date:   2019-04-08 09:00:00 +0800
categories: jekyll update
---

## Jekyll的_config文件配置报错

Jekyll 搭建博客时, 修改完`_config.yml`文件后就收到了github的build error邮件.

大致内容如下:
```$xslt
did not find expected key while parsing a block mapping at line 16 column 1
```

经过排查, 发现是`description`标签的问题
```$xslt
description: >- # this means to ignore newlines until "baseurl:"
  一个关于日常笔记的个人博客
  ---
  A personal blog about daily notes
#  Write an awesome description for your new site here. You can edit this
#  line in _config.yml. It will appear in your document head meta (for
#  Google search results) and in your feed.xml site description.
```
这里的注释不能放在`description`的下一行.

