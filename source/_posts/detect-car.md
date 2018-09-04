---
title: 卡口汽车检测
date: 2015-02-4 20:38:56
tags:
---

利用了 X.L. Wang [NPIP 2014] (Deep Joint Task Learning for Generic Object Extraction)中的 Localization Network,输入为 227*227 的 RGB 图片,网 络输出为上下角的坐标(x1,y1,x2,y2)。 在 X.L. Wang [NIP 2014]的 Localization 网络模型(从 Imagenet 训练得到)的基础上, 利用 2500 张标定好的车辆数据进行 fine-tuning。其中 2000 张用于训练,剩下 500 张用于测试。

https://github.com/lxiongh/Caffe_Windows_Detection

<!--more-->

{% asset_img overview.png overview %}

