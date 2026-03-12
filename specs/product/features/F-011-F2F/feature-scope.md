# F-011 F2F（面对面课堂）

**最后更新**: 2026-03-11 | **状态**: stable

## 功能范围

**面对面课堂**专项功能，包含 F2F 学习、审核、评分、证书等。

### 核心能力

| 能力 | 描述 |
|------|------|
| F2F 学习管理 | 管理面对面学习记录 |
| 审核 | F2F 结果审核（FlipAuditController） |
| 评分排名 | 学员评分与排名（FlipScoreRankDetailController） |
| 证书 | 学员证书管理（FlipUserCertificateController） |
| 惯常地址 | 管理常用上课地址（FlipUsualAddressController） |
| 消息重试 | 消息重发机制（FlipRetryMessageController） |

### Controller（f2f 目录）

| Controller | 职责 |
|------------|------|
| FlipF2FController | F2F 主流程 |
| FlipF2FStudyController | F2F 学习管理 |
| FlipAuditController | 审核 |
| FlipScoreRankDetailController | 评分排名 |
| FlipUserCertificateController | 证书 |
| FlipUsualAddressController | 惯常地址 |
| FlipRetryMessageController | 消息重试 |
| FlipCustomController | 自定义功能 |

## 边界与依赖

- **依赖**: F-001（F2F 属于某面授）、F-004（权限）
