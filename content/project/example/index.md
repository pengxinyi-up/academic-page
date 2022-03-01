---
title: 基于RGB-D的移动抓取服务机器人的设计与实现
summary: 该项目基于ROS框架，仿真环境与真实机器人相结合，在Kobuki底座上设计并搭载了一条带有夹爪的六自由度手臂，基于Kinect相机获取RGB-D图像实现室内SLAM和导航规划功能，同时结合科大讯飞开放平台和OpenCV开源图像处理库，赋予机器人身份认证、语音命令识别、物体识别等功能，利用图像识别物体位姿并通过对机械臂进行运动学规划，构造一款可以抓取递送物品的服务机器人。
tags:
- RGB-D
- ROS
- 运动规划
- 移动抓取
- 服务机器人仿真
date: "2020-04-27T00:00:00Z"
# Optional external URL for project (replaces project detail page).
external_link: ""

image:
  # caption: Photo by rawpixel on Unsplash
  focal_point: Smart

# links:
# - icon: twitter
#   icon_pack: fab
#   name: Follow
#   url: https://twitter.com/georgecushen
url_code: "https://github.com/pengxinyi-up/mobile-grab-Robot"
url_pdf: "https://blog.csdn.net/qq_37372155/category_9650566.html"
url_slides: "https://blog.csdn.net/qq_37372155/category_9650566.html"
url_video: "https://www.bilibili.com/video/BV1WK4y147Rw?spm_id_from=333.999.0.0"

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides: example

categories:
- 机器人
- SLAM
---

## 摘要

&nbsp &nbsp &nbsp &nbsp 近年来，人工智能技术的发展推动了机器人的智能化进程，清洁、配送、陪护等服务机器人给人们生活带来的便利正在普及。人类的眼睛和手臂配合可以完成复杂的抓取行为。同理，视觉传感器能帮助机器人捕获丰富的环境信息，机械臂可以完成类人的抓取任务。因此本课题基于RGB-D深度视觉和开源的ROS系统，开展移动抓取机器人的仿真环境和软硬件的设计与实现，主要分为建图导航和机械臂的识别抓取两部分。
&nbsp &nbsp &nbsp &nbsp 首先，基于D-H参数建立了机器人的模型并在RVIZ下可视化，基于Ros_control配置了底盘的差速控制器和机械臂的关节位置控制器，在Gazebo仿真平台建立了机器人的物理仿真模型和演示场景。
&nbsp &nbsp &nbsp &nbsp 在建图导航部分，基于Kobuki底盘和Kinect v1深度相机搭建了移动导航平台，借助ROS Navigation导航框架，利用Gmapping功能包和Amcl功能包完成SLAM任务，利用Move\_base功能包基于Dijkstra算法和DWA算法完成导航任务。
&nbsp &nbsp &nbsp &nbsp 在识别抓取部分，在底盘上搭载了一台六自由度机械臂，Arduino UNO微处理器和PCA9685驱动作为机械臂的控制硬件，利用Find\_object\_3d功能包基于oFast和rBRIEF算法完成目标的识别定位，使用MoveIt配置助手通过Trac\_ik插件基于牛顿收敛法和SQP方法完成了机械臂的逆运动学规划。
&nbsp &nbsp &nbsp &nbsp 最后，在仿真环境下进行了综合演示实验，结合人脸身份认证和语音指令导航，机器人能够完成移动抓取任务。并且针对建图定位偏移、抓取规划不稳定等问题，提出了硬件结构和规划方法的改进方向，通过抓取改进实验减少了机械臂与场景的碰撞。



## ROS机器人（仿真+实物）
![system_structure](https://raw.githubusercontent.com/pengxinyi-up/mobile-grab-Robot/master/photos/system_structure.png "系统结构") 

## 模型建立及仿真场景
![simulation_model](https://raw.githubusercontent.com/pengxinyi-up/mobile-grab-Robot/master/photos/simulation_model.png "仿真模型") 

## 硬件连接及实物图
![hardware_system](https://raw.githubusercontent.com/pengxinyi-up/mobile-grab-Robot/master/photos/hardware_system.png "硬件系统") 

## 系统结构
![system_structure](https://img-blog.csdnimg.cn/20200622104500776.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM3MzcyMTU1,size_16,color_FFFFFF,t_70 "系统结构") 


* Simulation design and Realization of face recognition, voice control, autonomous movement, recognition and grasping robot based on ROS
* Thanks for the great work: [find-object](https://github.com/introlab/find-object), [face_recognition](https://github.com/procrob/face_recognition)and[古月居](https://www.guyuehome.com/)
* Video: [`Bilibili`](https://www.bilibili.com/video/BV1WK4y147Rw?spm_id_from=333.999.0.0)

### [详细内容，点此链接可以去我的`CSDN博客`!](https://blog.csdn.net/qq_37372155/category_9650566.html) 
