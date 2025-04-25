# 📚 文档协作与贡献指南

欢迎参与本项目文档的撰写与维护！为保障协作效率，请遵循以下流程与约定。

## 🛠 环境准备

1. 安装 `Python3` 和 `pip`
2. 安装 MkDocs 及其插件（推荐使用 `mkdocs-material`）：

```bash
pip install mkdocs-material
```

3. 本地预览文档：

```bash
mkdocs serve
```

## 🗂 项目结构概览

文档目录结构如下：

```
docs/
├── 0_project_overview/
├── 1_system_design/
├── 2_implementation/
├── 3_experiments/
├── 4_appendices/
└── README.md
```

各文件说明请参考 [index.md](./index.md)。

## 👤 角色分工

| 角色 | 职责描述 |
|------|----------|
| 项目负责人 | 管理整体结构、技术路线与任务分配 |
| 系统设计 | 撰写系统结构、架构图、客户端/服务端设计 |
| 算法实现 | 编写核心算法逻辑、推理流程说明 |
| 实验分析 | 设计实验方案，分析评估指标与结果 |
| 文献维护 | 更新参考文献、术语、研究综述等 |
| 审校校对 | 负责语言、格式、术语一致性审核,负责文档的分工协调工作 |

## 📝 编写与提交规范

- 使用 Markdown 编写内容，建议使用 [VSCode](https://code.visualstudio.com/)
- 所有提交通过 PR（Pull Request）完成，合并前需至少一人 Review
- 引用文献请更新 `references.bib`
- 图片请统一放置于 `docs/4_appendices/figures/` 目录

## 🔁 工作流程

>  详细的工作流程请参考 [GitHub Workflow](./github_workflow.md)。

1. 在 GitHub 创建 Issue，认领章节任务（可使用模板）
2. 创建分支并撰写内容
3. 提交 Pull Request
4. 审核通过后合并到主分支
5. 自动或手动部署至 GitHub Pages

## ✅ 参考命名与标签规范

| 类型 | 命名规范 |
|------|----------|
| 分支名 | `feature/<章节名>` 或 `fix/<修复点>` |
| PR 标题 | `[章节] 内容更新 - your_name` |
| Issue 标签 | `task`、`in-progress`、`review-needed` 等 |

---

有任何问题，请在 Issue 区进行反馈或联系项目负责人 🙌
