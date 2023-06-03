## 关键点检测的全流程实现

![img](images/3-1.png)

这一讲主要是子豪兄介绍关键点检测在openmmlab框架下训练预测的pipeline

采用的是自顶向下的算法逻辑，即先预测出框的位置，然后再在框内预测关键点位置；所以急需要mmpose也需要mmdetection算法库

视频中是以三角板最简单的一个单分类关键点检测举例的，采用mscoco数据格式

对于mmpose的训练预测主要关注配置py文件如图：
![img](images/3-2.png)