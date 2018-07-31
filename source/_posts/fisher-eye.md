---
title: 鱼眼恢复
date: 2013-03-20
tags:
---

{% asset_img before.jpg 处理之前 %}
{% asset_img after.jpg 处理之后 %}

<!--more-->

算法的基本思想如下图所示。即以图（a）中点为中心，以R1为半径，将图像分为n等份的扇形，后将扇形以逆时针方向 展开（b）。图（b）至图（c）进行图的径向伸缩变换，图（c）至图（d）进行图的水平伸缩变换。

{% asset_img fw.jpg 算法流程 %}

``` matlab

function [ img ] = fisheye3( im, R1, R2, N )
%FISHEYE2 Summary of this function goes here
%   Detailed explanation goes here

theta0 = pi/N;
[row,col,ch] = size(im);

center_x = floor(col/2);
center_y = floor(row/2);
D = floor(2*R2*tan(theta0));
img = uint8(zeros(R2-R1+1,D*N,ch));

[Y,X] =  meshgrid(R1:size(img,1)+R1-1,1:size(img,2));
% tic;
for i=1:numel(X)
    x1= X(i);
    y1 = Y(i);
    
    n = floor(x1/D) + 1;
    a = floor(D/2) + (n-1)*D + 1;
    b = 1;
    c = (n-1)*D + 1;
    d = floor(a - y1*tan(theta0)) + 1;
    
    k1 = y1/R2;
    y2 = y1;
    x2 = (x1-c)*k1 + d;
    
    dx2 = x2 - a;
    dy2 = y2 - b;
    theta2 = atan(dx2/(dy2+eps));
    rho2 = sqrt(dx2^2 + dy2^2);
    
    k2 = cos(theta2);
    rho3 = rho2*k2;
    theta3 = theta2;
    
    rho4 = rho3;
    theta4 = theta3 + (n-1)*2*theta0;
    
    x4 = floor(center_x + rho4*sin(theta4));
    y4 = floor(center_y + rho4*cos(theta4));
  
    if ch==3
        img(y1-R1+1,x1,:) = [im(y4,x4,1), im(y4,x4,2), im(y4,x4,3)];
    else
        img(y1-R1+1,x1) = im(y4,x4);
    end
end
% toc;
```


