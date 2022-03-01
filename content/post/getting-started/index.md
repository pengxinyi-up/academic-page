---
title: A lightweight object-level data association and change detection method for robot map
subtitle: In this paper, an object-level data association method is proposed to construct object-level map for lightweight and low-cost application scenarios. And we propose a change detection method for autonomous updating of robot map. 

# Summary for listings and search engines
summary: In this paper, an object-level data association method is proposed to construct object-level map for lightweight and low-cost application scenarios. And we propose a change detection method for autonomous updating of robot map. 

# Link this post with a project
projects: []

# Date published
date: "2022-03-01T00:00:00Z"

# Date updated
lastmod: "2022-03-01T00:00:00Z"

# Is this an unpublished draft?
draft: false

# Show this page in the Featured widget?
featured: true

# Featured image
# Place an image named `featured.jpg/png` in this page's folder and customize its options here.
image:
  caption: 'Image credit: [**Unsplash**](https://github.com/pengxinyi-up/academic-page/blob/master/images/fig_system-structure.png)'
  focal_point: ""
  placement: 2
  preview_only: false

authors:
- admin
- 陈果
- 李帆

tags:
- 数据关联
- 变化检测
- 地图更新
- vSLAM

categories:
- Demo
- 教程
---

## Overview

Autonomous mobile robots usually need an object-level map for better reasoning and decision-making.  However, the changes of scene objects make it difficult to reuse map and lack of lightweight system solutions.  In this paper, an object-level data association method is proposed to construct object-level map for lightweight and low-cost application scenarios.   Specifically, we maintain a sparse point cloud map using only a monocular camera.  Based on the feature tracking information of ORB-SLAM2, this method introduces semantic information to associate data in parallel and reduce the extra computational burden. 
Then, we propose a change detection method for autonomous updating of robot map. We are pioneering in the object level of the environment change detection and map update, to achieve the unity of object level mapping and update.  which ensures the consistency and integrity of updated parts.  The proposed method has been extensively tested on multiple public data sets and a real robot.  The results show that the effect of data association reaches the latest level and is superior to the similar methods in time and space complexity.  And the detection rate of object change reached 83.75\%.  In addition, we have implemented a lightweight robot system.  Frame rate reached 20 FPS when using only half the system resources.  

The contributions of this paper are as follows: 

1. A lightweight data association method.  Using the spatial relation of map points and combining with the mutex table we proposed.  
2. A lightweight change detection and map update method.  Object-level updates ensure the consistency and integrity of updates.  
3. A real-time system.  For object-level semantic awareness tasks and low-cost hardware platform requirements, the unification of map building, change detection and update is realized. 
4. Our method was deployed and extensively tested on a robot with a low-power embedded platform.  The validity, lightness and excellence of the method are proved.

{{< figure src="https://github.com/pengxinyi-up/academic-page/blob/master/images/fig_system-structure.png" title="The template is mobile first with a responsive design to ensure that your site looks stunning on every device." >}}