# F-010 考勤

**最后更新**: 2026-03-11 | **状态**: stable

## 功能范围

面授**考勤签到/签退**及考勤审核，由独立子模块 `attendeng` 提供。

### 核心能力

| 能力 | 描述 |
|------|------|
| 签到 | 学员签到（支持地理位置验证） |
| 签退 | 学员签退 |
| 考勤记录查询 | 查看个人/全员考勤记录 |
| 考勤审核 | 管理员审核异常考勤 |
| 抽奖 | 考勤抽奖功能（AttendLottery） |
| 考勤完成规则 | 配置考勤完成判定规则（AttendCompleteRule） |

### 相关实体（attendeng 模块）

- `AttendanceDetailEntity` — 考勤详情
- `UserAttendanceInfoEntity` — 用户考勤信息
- `AttendUserAudit` — 考勤审核
- `AttendConfig` — 考勤配置
- `AttendLottery` / `AttendLotteryRound` / `AttendLotteryResult` — 抽奖
- `AttendCompleteRule` — 完成规则
- `AttendAttachment` — 考勤附件

### FlipDetailEntity 考勤相关字段

| 字段 | 含义 |
|------|------|
| enableAttend | 是否开启考勤 |
| enableSignIn | 是否开启签到 |
| enableSignOut | 是否开启签退 |
| inTimeOfAllowLate | 允许迟到分钟数 |
| inTimeOfAllowBefore | 允许提前签到分钟数 |
| outOfRangeProcess | 超范围签到处理方式 |

## 边界与依赖

- **依赖**: F-001（考勤开关配置在 FlipDetailEntity）
- 通过 `AttendWrapper` 与主模块交互
