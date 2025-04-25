# GitHub 协同工作流指南（基于 Issues 和 Pull Requests）

## 🧭 目的

本指南旨在规范项目协作流程，帮助团队成员高效利用 GitHub 的 Issues 和 Pull Requests 功能进行任务管理、代码开发、审查与合并。

---

## 🗂 工作流概览

```
Issue → 分支 → 开发 → Pull Request → 代码审查 → 合并 → 关闭 Issue
```

---

## 1️⃣ 创建 Issue（问题/任务）

### 用途

- 记录 **新功能需求**
- 报告 **Bug**
- 规划 **重构/优化**
- 讨论 **技术方案** (建议相关问题的讨论**集中在对应的 Issue 中**)
- 追踪 **任务进度**
- 记录 **文档更新**
- 其他 **项目相关问题**

### 建议格式

- 标题：简明扼要说明问题
- 内容：
  - 描述问题或需求
  - 补充截图、链接、上下文信息
  - 指定 `labels`（如 `bug`, `enhancement`, `discussion`）
  - 如可行，指定负责人 (`Assignees`)

---

## 2️⃣ 新建分支（基于 Issue）

### 命名规范

```bash
# 一般格式：issue编号-描述
git checkout -b feature/123-add-login
git checkout -b fix/145-fix-crash
```

#### 文档相关命名规范

| 类型 | 命名规范 |
|------|----------|
| 分支名 | `feature/<issue编号-章节名>` 或 `fix/<issue编号-修复点>` |
| PR 标题 | `[章节] 内容更新 - your_name` |
| Issue 标签 | `task`、`in-progress`、`review-needed` 等 |

> 💡 分支名建议包含 issue 编号，方便关联追踪。

---

## 3️⃣ 开发阶段

在新建的分支上进行开发：

- 保持提交原子化、语义清晰（如：`fix: 修复登陆页面崩溃的问题`）
- 多人协作时注意同步远程分支：`git pull origin main`

---

## 4️⃣ 提交 Pull Request（合并请求）

### 目的

- 提交代码以供审查
- 触发 CI 流程
- 最终合并到主分支（`main` 或 `dev`）

### 操作步骤

1. 推送分支：`git push origin feature/123-add-login`
2. 在 GitHub 上发起 PR，填写说明：
   - 引用相关 Issue：`Closes #123`（或 `Fixes`, `Resolves`）
   - 简要说明改动内容
   - 标明是否需要其他人审查（可指定 Reviewer）

### PR 模板（可选）

可添加 `.github/pull_request_template.md` 文件作为 PR 默认内容，确保信息完整。

---

## 5️⃣ 代码审查（Code Review）

### 审查要点

- 代码风格是否统一
- 是否有逻辑漏洞
- 是否影响已有功能
- 是否包含必要的测试

### 审查意见

可通过 GitHub 的 Review 功能：

- `Comment`：提供建议
- `Approve`：同意合并
- `Request changes`：需改进后再审查

---

## 6️⃣ 合并与清理

### 合并方式

- `Squash and merge`：保持主分支简洁，适合多人贡献的小变更(暂时pr强制使用squash and merge）)
- `Rebase and merge`：保持线性提交历史
- 避免使用 `Merge commit`（除非确有必要）

### 清理工作

- PR 合并后自动关闭对应 Issue
- 删除已合并的分支（可在 PR 页面一键操作）

---

## ✅ 最佳实践

- 每个功能/问题一个 Issue，对应一个 PR
- 强制 Review：所有 PR 必须至少有 1 名 Reviewer 审查通过
- 配置自动化检查（CI）：如代码格式、单元测试、构建检查等
- 保持沟通，鼓励在 Issue 和 PR 中写评论、反馈、建议

---

## 🔧 推荐配置（可选）

- **分支保护规则**：
  - 禁止向 `main` 直接推送
  - 合并需通过 CI + 审查
- **Labels 标签分类**：
  - `bug`, `enhancement`, `question`, `wontfix`, `refactor`
- **PR 模板**：统一格式，提高质量
- **自动关联脚本**（GitHub Actions）：
  - 合并 PR 自动关闭 Issue
  - 自动分配 Reviewer

---

## 📎 示例

### Issue 示例

```
标题：登录页面报错（TypeError）
内容：
- 报错信息：TypeError: Cannot read property 'value' of null
- 浏览器：Chrome v110
- 复现步骤：
  1. 打开登录页面
  2. 立即点击登录
  3. 页面崩溃
```

### PR 示例

```
标题：[Fix] 修复登录页面 null 报错 (#123)
内容：
- 问题原因：表单未初始化就调用 `value`
- 解决方案：添加 null 检查
- 相关 Issue：Closes #123
```
