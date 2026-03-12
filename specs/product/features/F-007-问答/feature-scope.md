# F-007 问答（QA）

**最后更新**: 2026-03-11 | **状态**: stable

## 功能范围

面授课堂内的**问答互动**，讲师提问、学员作答。

### 核心能力

| 角色 | 能力 |
|------|------|
| 讲师 | 发起问答、查看学员作答情况 |
| 学员 | 提交答案 |

### 相关实体

- `FlipUserQaEntity` — 学员问答记录

### Controller

- `FlipUserQaStudentController` — 学员端
- `FlipUserQaTeacherController` — 讲师端

## 边界与依赖

- **依赖**: F-001（问答属于某面授）
