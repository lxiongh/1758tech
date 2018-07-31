---
title: 数据驱动下的图像场景分析
date: 2014-07-30 21:56:19
tags:
  - Scene Parsing
  - Image Understanding
---

Data-Driven Scene Understanding by Adaptive Exemplar Retrieval, Xionghao Liu, Wei Yang, Liang Lin, and Jian-Huang Lai, Proc. of IEEE International Conference on Multimedia and Expo (ICME), 2014.

> 注：ICME是多媒体计算领域的知名国际会议，被中国计算机学会(CCF)推荐为B类学术会议

{% asset_img ICME_Demo.gif demo %}

<!--more-->

## Abstract

> 
1. Data-Driven Scene Understanding by Adaptive Exemplar Retrieval, Xionghao Liu, Wei Yang, Liang Lin, and Jian-Huang Lai, Proc. of IEEE International Conference on Multimedia and Expo (ICME), 2014.

2. Data-Driven Scene Understanding with Adaptively Retrieved Exemplars, Xionghao Liu, Wei Yang, Liang Lin, Qing Wang, Zhaoquan Cai, Jianhuang Lai, MultiMedia, IEEE (Volume:PP , Issue: 99 )

This article studies a data-driven approach for semantically scene understanding, without pixelwise annotation and classifier pre-training. Our framework parses a target image with two steps: (i) retrieving its exemplars (i.e. references) from an image database, where all images are unsegmented but annotated with tags; (ii) recovering its pixel labels by propagating semantics from the references. We present a novel framework making the two steps mutually conditional and bootstrapped under the probabilistic Expectation-Maxima (EM) formulation. In the first step, the references are selected by jointly matching their appearances with the target as well as the semantics. We process the second step via a combinatorial graphical representation, in which the vertices are superpixels extracted from the target and its selected references. Then we derive the potentials of assigning labels to one vertex of the target, which depends upon the graph edges that connect the vertex to its spatial neighbors of the target and to its similar vertices of the references. Two steps can be both solved analytically, and the inference is conducted in a self-driven fashion. In the experiments, we validate our approach on two public databases, i.e. MSRC-21 and PASCAL VOC 2007, and demonstrate superior performances over the state-of-the-arts methods.


## Framwork

A glance of our framework is shown in below, where we semantically segment the target image in a self-driven fashion: The algorithm iterates to retrieve (c) the exemplars matching with the target from (b) the auxiliary data , and (a) parse the target image in the virtue of the strength of the selected exemplars.

{% asset_img framework.jpg framework %}

## Experiment

Table below shows the average accuracies for our approach incomparison with other competitive algorithms, from whichwe clearly see that our algorithm outperforms the others. Benefit from the semantic constraints incorporated in our approach, we achieve a significant improvements for certain difficult classes, e.g., chair and cat. Serveral visualized results with the corresponding ground-truths are presented in Fig. 4, and more semantic segmentation results are in supplementary material as to the limited space of article.

{% asset_img result.jpg result %}

The most semantic segmentation results are shown below

{% asset_img s0.jpg detail0 %}

{% asset_img s1.jpg detail1 %}

{% asset_img s2.jpg detail2 %}

The more semantic segmentation results are available in supplementary material please refer to the site: http://lxiongh.qiniudn.com/scene_parsing_supplementary_material.pdf
