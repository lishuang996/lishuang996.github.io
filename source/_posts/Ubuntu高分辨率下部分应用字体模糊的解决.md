---
title: Ubuntu高分辨率下部分应用字体模糊的解决
date: 2025-10-14 00:42:25
tags: Linux
---

在安装Ubuntu后，我们会发现在高分辨率的显示器下，分数缩放会导致部分应用变得模糊。依据网上的搜索结果，发现修改应用启动参数后发现没有效果。本文使用 `gnome-tweaks` 作为替代方案。具体步骤如下：

1. 安装`gnome-tweaks`

   ```bash
   sudo apt install gnome-tweaks
   ```

2. 打开 `gnome-tweaks` 在字体一栏调整缩放比例

   

该方法的缺点：只能放大字体，对于其他的内容如图标无法正常缩放。
