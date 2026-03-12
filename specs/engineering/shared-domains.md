# 共享 Domain

**最后更新**: 2026-03-11

## Domain 列表

| Domain | 路径 | 被哪些 Feature 使用 |
|--------|------|-------------------|
| flip | `flipapp/entity/FlipDetailEntity` | F-001、F-002、F-004、F-009 |
| group | `flipapp/entity/FlipGroupEntity` | F-003 |
| user | `flipapp/entity/FlipHasUserEntity` | F-001、F-003、F-004 |
| exam | `flipapp/entity/FlipUserExamEntity` | F-005 |
| vote | `flipapp/entity/FlipCfgVoteEntity` | F-006 |
| qa | `flipapp/entity/FlipUserQaEntity` | F-007 |
| survey | `flipapp/entity/FlipUserSurveyEntity` | F-008 |
| external-user | `flipapp/entity/FlipExternalUserEntity` | F-009 |
| attend | `attendeng/entity/*` | F-010 |
| f2f | `flipapp/controller/f2f/*` | F-011 |

## 共享实体

- `UdpLiteUserEntity` / `UdpFullLiteUserEntity` — 用户轻量信息（跨模块共享）
- `FlipDetailEntity` — 面授主体（大部分 Feature 依赖）
