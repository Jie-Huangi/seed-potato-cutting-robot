[中文版](./README.zh.md) | [English Version](./README.md)

# CuTo-Robot: An Automated Potato Cutting Robot System
> **Title: Design and implementation of a seed potato cutting robot using deep learning and delta robotic system with accuracy and speed for automated processing of agricultural products**
>
> Video Introduction (Chinese): [【自制】马铃薯种薯切块机器人！【硬核】](https://youtu.be/niPWDtM_0C8) (Homemade Potato Seed Cutting Robot! [Hardcore])
>
> Video (English): [An automated potato cutting robot system - YouTube](https://youtu.be/niPWDtM_0C8)

![](Docs/1.CuTo-Robot.png)

![](Docs/2.Delta.png)

## About the Potato Cutting Robot: From September 2022 to April 2025

The potato cutting robot project started in August 2022, during the summer of my first year of master's studies. That summer, I designed the mechanical structure from scratch. After the semester began, my junior colleagues and I built the experimental platform, and by the end of September, our first-generation prototype was ready.

![](Docs/3.Version-1.1-Robot.gif)

At that time, I used serially connected servo motors to create a robotic arm, hoping to cut potatoes from different angles for more perfect pieces.
The idea was good, but reality was harsh. I struggled with this serial arm design for about two months, until around November. I realized that the arm I built wouldn't work, and buying an industrial arm was not an option.
I also considered using ROS for control and reinforcement learning to avoid the potato eyes—things that sounded advanced—but after much effort, I found the technical difficulty and time cost were too high for me to pursue this path.

Realizing that multi-angle cutting was not feasible, I had to adjust my approach. I started thinking, what if I lowered the requirements and only performed top-down cutting?
The quality of the cut pieces might be slightly worse, but at least the cutting action could be performed. As soon as this idea came to mind, I instinctively thought of the Delta parallel robot. The feasibility seemed much higher, as its structure is suitable for fast vertical movements and has a strong load capacity.

Around that time (late November), I found open-source Delta robot materials online. Due to the pandemic, the university required students to return home, but I applied to stay on campus to assemble this new robotic arm.
After about a month of work, by the end of December, I finally assembled the first Delta arm and could control its movement using an Arduino Mega 2560.

![](Docs/4.Version-1.2-Robot.gif)

After returning home for the New Year, things went much smoother in early 2023. From January to February, I wrote a Chinese paper on potato eye recognition (published in May). In April, I redesigned a Delta arm based on the open-source model. By the end of April, the cutting robot was taken to Jiangsu University for a competition.
At that time, the equipment was not very stable. The cutting action could only be performed in one direction, and the end-effector's position could not be adjusted according to the potato's posture. Later, I designed a simple cutting decision mechanism, which was basically usable. The project was put on hold during the summer months of July and August.

Upon starting my PhD program (September 2023), I hoped to revive my equipment. I replaced the original open-loop drive with a closed-loop drive with optocouplers, making the movement more stable and precise. For vision, I tried using semantic segmentation plus PCA to calculate the potato's posture. On September 30th, around midnight, I drafted the paper outline, planning to write the detailed content the next day. Unfortunately, I didn't manage to write it on the second day, nor for the following 200 days.

Around December 2023, I turned my attention to rotated object detection. After some research and modifying YOLO's loss function, I could finally stably predict the potato's bounding box with an angle. This experience also improved my coding skills.
Based on this rotated object detection achievement, I prepared an SCI paper in January, February, and March, submitted it in April 2024, and it went online in December. Additionally, in August, I wrote an article on decision algorithms, which is still under review.

In November 2024, I revisited the system integration article I had planned to write at the end of September 2023. By January 2025, the first draft was basically complete.
After the New Year, starting in February, I made significant modifications and experiments on the equipment: updated the underlying algorithms, replaced the camera and conveyor belt, and improved the cutting decision mechanism. The paper I am currently writing is based on these latest hardware and software upgrades and experimental results.

From September 2022 to April 2025, nearly two years and seven months, my potato cutting robot has undergone three major upgrades in hardware and software: from a serial arm to a parallel arm, from open-loop drive to closed-loop drive, and continuous enhancement of control and vision algorithms.
During this period, four related papers were produced: one Chinese core journal paper on rectangular box detection, one SCI Q1 journal paper on rotated object detection, and two articles on decision algorithms and system integration, which are currently under review.

> **Acknowledgements to the following project authors:**
>
> * [Robotic Arm Tutorial: From Theory to Practice of Visual Grasping (bilibili.com)](https://www.bilibili.com/video/BV1zP4y1S7yy)
> * [Bilibili UP Master "Revolutionary Straw Sandals" (bilibili.com)](https://www.bilibili.com/video/BV18S4y1A76F)
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
