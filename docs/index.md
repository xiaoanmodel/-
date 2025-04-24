# Welcome to MkDocs

For full documentation visit [mkdocs.org](https://www.mkdocs.org).

## Commands

* `mkdocs new [dir-name]` - Create a new project.
* `mkdocs serve` - Start the live-reloading docs server.
* `mkdocs build` - Build the documentation site.
* `mkdocs -h` - Print help message and exit.

## Project layout

```
docs/
├── README.md                        # 文档首页，项目简介与导航
├── 0_project_overview/             # 项目概述
│   ├── background.md               # 研究背景与动机（问题1）
│   ├── related_work.md             # 研究进展/文献综述（问题2）
│   ├── problem_statement.md        # 明确提出研究问题
│   └── contribution_summary.md     # 创新点总览（问题4）
├── 1_system_design/                # 系统设计
│   ├── architecture.md             # 系统架构图与模块功能说明
│   ├── client_design.md            # 鸿蒙客户端设计
│   ├── server_design.md            # Flask 服务端设计
│   ├── sensor_fusion.md            # 多模态数据融合与PCA分析
│   └── algorithms.md               # 核心算法说明（问题3）
├── 2_implementation/              # 系统实现细节
│   ├── hardware_assumptions.md     # 无硬件改造的设计考量
│   ├── monocular_depth.md          # 单目深度估计实现
│   ├── instance_segmentation.md    # Mask RCNN替代vLLM的具体实现
│   ├── pointcloud_generation.md    # 点云构建逻辑
│   └── inference_pipeline.md       # 端到端推理流程说明
├── 3_experiments/                 # 实验设计与评估
│   ├── experiment_plan.md          # 实验方案总览（问题5）
│   ├── dataset_description.md      # 自建数据集说明
│   ├── evaluation_metrics.md       # 指标定义与评估标准
│   ├── baseline_comparison.md      # 对标方案比较分析
│   └── result_analysis.md          # 实验结果与分析（问题6）
├── 4_appendices/                  # 附录
│   ├── glossary.md                 # 名词术语表
│   ├── references.bib              # 核心参考文献BibTeX
│   ├── figures/                    # 所有插图（架构图、实验图等）
│   └── questions_answered.md      # 常见答辩/开题问题汇总
```
