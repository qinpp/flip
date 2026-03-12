# F-006 投票

**最后更新**: 2026-03-11 | **状态**: stable

## 功能范围

面授课堂内的**实时投票互动**功能。

### 核心能力

| 能力 | 描述 |
|------|------|
| 发起投票 | 讲师创建并发起投票 |
| 提交投票 | 学员选择并提交投票选项 |
| 查询投票 | 查询用户投票记录 |
| 查询投票详情 | 查看投票明细 |
| 刷新投票 | 更新实时投票结果 |
| 查看结果 | 查看投票汇总结果 |
| 结束投票 | 讲师关闭投票 |

### 相关实体

- `FlipCfgVoteEntity` — 投票配置
- `FlipUserVoteEntity` — 学员投票记录
- `FlipUserVoteResp` — 投票响应

## API 路由

基础路径：`/flip/flipcfgvote`

| 方法 | 路径 | 说明 |
|------|------|------|
| POST | /save | 创建投票 |
| POST | /saveUserVote | 提交投票 |
| POST | /queryUserVote | 查询用户投票 |
| POST | /queryUserVoteDetail | 查询投票详情 |
| POST | /refresh | 刷新结果 |
| POST | /result | 查看结果 |
| POST | /teacherExit | 讲师结束投票 |

## 边界与依赖

- **依赖**: F-001（投票属于某面授）
