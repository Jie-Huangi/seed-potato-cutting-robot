[English Version](./README.md)

# CuTo-Robot: An automated potato cutting robot system
> **Title: Design and implementation of a seed potato cutting robot using deep learning and delta robotic system with accuracy and speed for automated processing of agricultural products**
>
> 视频介绍：[【自制】马铃薯种薯切块机器人！【硬核】](https://youtu.be/niPWDtM_0C8)
>
> Video : [An automated potato cutting robot system - YouTube](https://youtu.be/niPWDtM_0C8)

![](Docs/1.CuTo-Robot.png)

![](Docs/2.Delta.png)


 ## 关于马铃薯切块机器人：从2022年9月到2025年4月

马铃薯切块机器人项目从2022年8月份，我研一那个暑假开始的。那年暑假，我从零开始设计机械结构，开学后和师弟们一起搭实验台，到9月底，我们的第一代原型机就出来了。

![](Docs/3.Version-1.1-Robot.gif)

当时我用舵机串联做了个机械臂，想着能从不同角度去切，切出更完美的马铃薯块。
想法是美好的，现实是残酷的。我为这个串联臂的设计挣扎了差不多两个月，大概到11月份。认识到自己造的机械臂肯定行不通，买工业臂又没那个条件。
中途还想过用ROS控制、搞强化学习避开芽眼这些听起来高大上的东西，但折腾了一把又一把头发，发现技术难度、时间成本都让我觉得，这条路在我这里走不通。

意识到多角度切割这条路行不通后，我不得不调整思路。我开始想，如果降低要求，只做直上直下的切割呢？
也许切块质量会差点，但至少能把切割动作执行起来。这个念头一出来，我下意识就想到了Delta并联机械臂，感觉可行性一下大了很多，毕竟它的结构适合快速的垂直运动，负载能力也很强。

刚好那时候（大概11月底），我在网上看到有分享开源Delta机械臂的资料。当时又因为疫情放开学校要求学生回家，但我为了把这个新方向的机械臂组装好，申请了留校。
折腾了一个月左右，到12月底，我终于组装好了第一台Delta臂，并且能用Arduino Mega 2560控制它动起来。

![](Docs/4.Version-1.2-Robot.gif)

回家过完年后，2023年开年事情就顺畅多了。1-2月在家写了篇识别芽眼的中文论文（5月发表），4月模仿那个开源机械臂重新设计了一款Delta臂，4月底，切块机械臂拉到江苏大学参加了比赛。
那时候的设备还不太稳定，切块动作只能单方向切割，不能根据马铃薯姿态调整末端执行器的位置。随后我设计一个简易的切块决策机制，基本上可以使用。到了暑假7、8月份，项目搁置。

进入博士阶段（2023年9月），我又期望重新点燃我的设备。我把原来的开环驱动换成了带光耦的闭环驱动，让运动更稳定精确。视觉方面，我尝试了用语义分割加PCA来算马铃薯姿态。9月30号凌晨12点撰写好了论文大纲，
准备二天写具体内容。事与愿违，我第2天乃至于随后的200天都没有来得及写。

到了2023年12月份左右，我把目光投向了旋转目标检测，研究了一阵子，改了改YOLO的损失函数，终于可以直接稳定地预测出马铃薯带角度的边界框了。这段经历也提升了我的代码能力。
基于这个旋转目标检测的成果，我1、2、3这几个月准备了篇SCI论文，2024年4月投出去，年底12月份online。另外，8月份还写了一篇关于决策算法的文章，一直在投稿。

2024年底11月份，我重新拾起了23年9月底就计划要写的系统集成文章。到了2025年1月份，初稿基本完成。
过完年后，从2月份开始，我又对设备进行了重大修改和实验：更新了底层算法、换了摄像头和输送带，还改进了切割决策的机制。我现在正在写的这篇论文，就是基于这次最新的软硬件升级和实验结果。

从2022年9月到现在（2025年4月），这快两年七个月的时间里，我的马铃薯切块机器人在软硬件上经历了三次大的升级：从串联臂到并联臂，从开环驱动到闭环驱动，以及控制和视觉算法的不断强化。
期间也产出了4篇相关的论文：一篇关于矩形框检测的中文核心，一篇关于旋转目标检测的SCI一区，还有两篇关于决策算法和系统集成的文章正在投稿中。


> **感谢以下项目作者：**
>
> * [机械臂入门教程：机械臂视觉抓取从理论到实战 (bilibili.com)](https://www.bilibili.com/video/BV1zP4y1S7yy)
> * [B站UP主革命的草鞋 (bilibili.com)](https://www.bilibili.com/video/BV18S4y1A76F)
> * [Delta-X-Firmware (github.com)](https://github.com/deltaxrobot/Delta-X-Firmware)
> * [Dummy-Robot (github.com)](https://github.com/peng-zhihui/Dummy-Robot)


## Citation
If you find our work useful in your research, please consider citing:
```
@article{POD-YOLO,
    journal = {Engineering Applications of Artificial Intelligence},
    issn = {0952-1976},
    author = {Jie Huang and Xiangyou Wang and Chengqian Jin and Fernando Auat Cheein and Xinyu Yang},
    title = {Estimation of the orientation of potatoes and detection bud eye position using potato orientation detection you only look once with fast and accurate features for the movement strategy of intelligent cutting robots},
    year = {2025},
    doi = {10.1016/j.engappai.2024.109923},
}
