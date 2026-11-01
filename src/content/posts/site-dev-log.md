---
title: 个人网站开发日志
published: 2026-11-01T12:00:00+08:00
description: 这是我在开发过程中的各种细节
tags: [网站]
category: 网站
draft: true
---
## 2026-10-31 第一次部署：失败了两次

**做了什么：** 把网站推送到 GitHub，用 GitHub Actions 自动发布到 guanbangtong.github.io。

**为什么用 GitHub Pages：** 免费，不用自己租服务器。写完文章推送上去，网站一两分钟后自动更新。

**踩的坑：**

1. lockfile 对不上。`package.json` 是依赖清单，`package-lock.json` 是实际安装的精确版本记录。
   我本地用 `npm install` 装的时候，它会自动凑合解决小冲突；GitHub 上用的 `npm ci` 要求两份严格一致，不一致就直接报错。
   解决：重新生成 lockfile。
2. 配置文件格式不对。关掉"编辑此页"功能时，我把 `enabled` 改成了 `false`，下面的 url 却还留着。
   模板规定关掉以后不能再写 url，本地预览不检查这一项，GitHub 发布前的检查却会报错。
   解决：删掉那一行。

**收获：** 本地能跑，不等于发布能过。发布前的检查比本地严格。而且这次是更加懂了怎么使用上github了，包括推送和pull以及修复bug。看到网站上的那个时候还是比较开心的，但是还只是一个框架，可能还需要不断地完善，挺有成就感的。

---
