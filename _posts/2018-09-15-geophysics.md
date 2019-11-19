---
layout:     post   				    # 使用的布局（不需要改）
title:      Segment salt deposits beneath the Earth's surface			# 标题 
subtitle:   Kaggle competation #副标题
date:       2018-08-10				# 时间
author:     Jiageng 						# 作者
header-img: img/salt.png   
catalog: true 						# 是否归档
tags:								#标签
    - machine learning
    - image processing
    
---

<script type="text/javascript" src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=default"></script>
# Segment salt deposits beneath the Earth's surface

# Task goal and metric
Several areas of Earth with large accumulations of oil and gas also have huge deposits of salt below the surface.
But unfortunately, knowing where large salt deposits are precisely is very difficult. 
Professional seismic imaging still requires expert human interpretation of salt bodies. 
This leads to very subjective, highly variable renderings. 
More alarmingly, it leads to potentially dangerous situations for oil and gas company drillers.
To create the most accurate seismic images and 3D renderings, TGS (the world’s leading geoscience data company) is hoping Kaggle’s machine learning community will be able to build an algorithm that automatically and accurately identifies if a subsurface target is salt or not.

The metric used in the project aims at evaluating on the mean average precision at different intersection over union (IoU) thresholds. The metric sweeps over a range of IoU thresholds, at each point calculating an average precision value. The threshold values range from 0.5 to 0.95 with step size of 0.05. 

At each threshold value t, a precision value is calculated based on the number of the true positives (TP), false negatives(FN), and false positives (FP) resulting from comparing the predicted object to all ground truth object.

![equation1](https://i.pinimg.com/originals/81/35/7f/81357f689807095b320e80470008f04b.jpg)

# Model
We tested several models for this project, containing basic U-net[[1]](), One-hundred layers Tiramisu [[2]](), deeplab-v2[[3]]().

The detail of One-hundred Layers Tiramisu is shown below:

![one-hundread](https://i.pinimg.com/originals/50/34/fa/5034faf208f6ee83ccc060b2b1a7290c.png)


The detail of deep-lab model is shown below:

![deep-lab](https://i.pinimg.com/originals/9f/4b/a3/9f4ba31e8748ad3a202ed711ae004724.png)


# Experiment result
The training process is shown below, where we set the threshold to be 0.9 calculate the IoU.
![training-result](https://i.pinimg.com/originals/1a/c6/10/1ac610988e3ea04a870e69d1c97fd264.png)

Some sample results of prediction can be seen here:
![sample-result](https://i.pinimg.com/originals/28/ff/0b/28ff0bc7e5addbac203b41c2d142e445.png)


