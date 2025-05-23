# 问题陈述

随着城市化进程的加速和两轮电动车的普及，城市交通管理面临新的挑战。当前两轮电动车停车存在以下主要问题：

1. **停车秩序混乱**：大量电动车无序停放，占用人行道、消防通道等，严重影响城市交通秩序和市容环境。
2. **违规停车普遍**：由于缺乏有效监管与直观引导，违规停车现象频发，增加了执法难度和市民不便。
3. **管理方式落后**：目前依赖人工巡查，存在效率低、成本高、反应慢等问题，难以满足日益增长的城市管理需求。
4. **停车区域划分不明确**：缺少可视化、智能化的停车区域引导，导致用户缺乏有效指引，进一步加剧乱停乱放现象。

面对以上问题，现有技术存在明显局限：
- 多数传统停车检测依赖固定摄像头和简单图像识别，缺乏复杂场景（如遮挡、光照变化、不同地形等）下的高鲁棒性。
- 现有模型识别精度不足，难以达到实际应用所需的高准确率。
- 通用视觉模型未针对两轮电动车停车细节（如车辆与道路边缘的夹角、占道情况）进行优化，导致检测结果不稳定，无法直接用于城市管理场景。
- 缺少面向用户的实时停车引导功能，仅关注违规检测，忽略了用户体验提升需求。

**本项目的具体问题定义如下：**

在城市公共区域，尤其是非机动车停车区域，需要通过**视觉大模型**（或其它人工智能技术），在不同天气、光照、地形条件下，准确识别两轮电动车是否规范停放，具体包括：
- 判断电动车是否停在划定区域内；
- 检测电动车与地面边界（如马路牙子）之间的夹角是否合理；
- 判断是否存在超范围、占道或阻碍通行的行为；
- 在用户停车时提供实时引导与规范反馈。

**项目的核心场景与约束条件包括：**
- 识别对象：两轮电动车为主，兼顾少量三轮车；
- 环境条件：自然光变化（白天、夜晚、阴雨天）、遮挡（人流、绿植）、地形起伏等复杂城市环境；
- 精度要求：停车规范检测准确率需≥99%，误报率≤1%；
- 资源约束：需兼顾在移动设备（手机端）或轻量级终端上的部署，保证推理速度快、计算资源占用低；
- 用户体验要求：识别速度快（延迟<1s），界面友好，指引直观易懂；
- 成本控制：通过减少人工巡查投入，实现整体管理成本降低至少30%。
