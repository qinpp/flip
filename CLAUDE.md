# CLAUDE.md - Flip

**最后更新**: 2026-03-11

---

## 项目概述

Flip 是一个面授管理平台，支持面授课程的创建、管理与字段设置。Monorepo 结构，包含：
- `flipapp/` — Java 后端（两个子模块：`flipapp` 核心业务 + `attendeng` 考勤引擎）
- `flipstu-pc/` — Vue.js 前端（学生端 PC Web，83 个组件）
- `yxt-design.pen` — UI 设计规范文件（Pencil）

### 功能模块

| 模块 | 职责 |
|------|------|
| 课程管理（Flip） | 面授课程创建、发布、管理（核心主流程） |
| 字段设置 | 面授相关字段自定义配置 |
| 分组（Group） | 学生分组管理 |
| 用户/认证（User/Auth） | 用户认证与权限 |
| 考试（Exam） | 课堂考试/测验 |
| 投票（Vote） | 课堂投票互动 |
| 问答（QA） | 课堂问答互动 |
| 问卷（Survey） | 问卷调查 |
| 外部用户（External User） | 外部用户接入管理 |
| 考勤（Attend） | 考勤记录与审核（attendeng 子模块） |
| F2F | 面对面课堂功能 |

### 对外接口

`FacadeFlipController`（`/facade/flip/**`）— 有外部客户在使用，**只能新增，不能修改或删除**。

---

## Build & Development Commands

### flipstu-pc（前端）

| 用途 | 命令 |
|------|------|
| 安装依赖 | `npm run bootstrap` |
| 开发服务器 | `npm run dev` |
| 构建生产 | `npm run build` |
| Lint | `npm run lint` |
| Lint 修复 | `npm run lintfix` |

### flipapp（后端）

> Java Maven 项目，具体命令见 `flipapp/README.md`

**测试现状**：后端仅 5 个测试文件（覆盖率极低），前端无测试文件。

---

## UI 设计规范

**每次生成 UI 页面时，必须参考 `yxt-design.pen`（项目根目录）。**

> 详见 [.claude/rules/design.md](.claude/rules/design.md)

---

## SDD 流程

流程概要：`intake → backlog → define-feature → design → plan → implement → verify`

| 命令 | 用途 |
|------|------|
| `/sdd:setup` | 初始化项目 |
| `/sdd:adopt` | 存量项目接入评估 |
| `/sdd:create-feature` | 创建新 Feature |
| `/sdd:resume` | 断点续作 |
| `/sdd:progress` | 查看进度 |
| `/sdd:check` | 一致性检查 |

---

## 目录结构

```
specs/
├── intake/        # Layer 0: 需求入口
├── backlog/       # Layer 1: Product Backlog
├── product/       # PM: 需求与范围
├── ui/            # UI/UE: 界面设计
├── engineering/   # Dev: 架构与领域
├── test/          # QA: 验证与追溯
└── tasks/         # Sprint: 任务执行计划
```

---

## 变更历史

| 日期 | 版本 | 变更内容 |
|------|------|----------|
| 2026-03-11 | 1.0 | 初始版本，SDD 框架接入 |
