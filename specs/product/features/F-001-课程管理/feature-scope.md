# F-001 课程管理

**最后更新**: 2026-03-11 | **状态**: stable

## 功能范围

面授课程的**全生命周期管理**，是平台核心主流程。

### 核心能力

| 能力 | 描述 |
|------|------|
| 创建面授 | 填写面授名称、说明、讲师、时间、场次等信息，创建面授课程 |
| 编辑面授 | 修改面授基本信息和配置 |
| 删除面授 | 删除未发布的面授 |
| 发布/下架 | 控制面授发布状态（草稿→发布→下架） |
| 查询面授 | 分页列表查询、按 ID 查询、简要信息查询 |
| 面授报表 | 查看面授参与情况报表 |
| 同步讲师 | 从外部系统同步讲师信息 |
| 同步时间 | 同步面授场次时间 |
| 评价检查 | 检查学员/讲师是否可以评价 |
| 预约会议 | 关联视频会议 |
| 学时核验 | 核验学员学时 |

### 配置项（FlipDetailEntity 关键字段）

| 字段 | 类型 | 含义 |
|------|------|------|
| flipName | String | 面授名称 |
| description | String | 富文本说明 |
| instructors | String | 讲师 ID（逗号分隔） |
| inTimeOfAllowLate | Integer | 允许迟到分钟数 |
| enableAttend | Integer | 是否开启考勤 |
| enableSignIn/Out | Integer | 是否开启签到/签退 |
| enableFlipAppraise | Integer | 是否开启评价 |
| stuSatisfactionRule | Integer | 学员满意度计算规则（0/1/2） |
| instSatisfactionRule | Integer | 讲师满意度计算规则 |
| studyScore | BigDecimal | 学分 |
| point | Integer | 积分 |
| durationPushMode | Integer | 学时推送模式（0:即学即推 1:核实下发） |
| expectDuration | Integer | 预计时长 |
| outOfRangeProcess | Integer | 超范围签到处理（0:记录异常 1:拒绝签到） |

### 面授状态流转

```
草稿（draft）→ 已发布（published）→ 已下架（unpublished）
```

## 边界与依赖

- **依赖**: 用户认证（F-004）、外部培训计划（UlcdArrangeFacade）
- **被依赖**: 分组（F-003）、考试（F-005）、投票（F-006）、问答（F-007）、问卷（F-008）、考勤（F-010）
- **对外接口**: `/facade/flip/**`（FacadeFlipController，受保护）

## API 路由（内部）

基础路径：`/flip`

| 方法 | 路径 | 说明 |
|------|------|------|
| POST | /createFlipInfo | 创建面授 |
| PUT | /updateFlipInfo | 更新面授 |
| PUT | /updateFlipInfos | 批量更新 |
| DELETE | /{flipId} | 删除面授 |
| PUT | /{publishState} | 更新发布状态 |
| GET | /{id} | 查询面授详情 |
| GET | /simple/{id} | 查询简要信息 |
| GET | /o2o/{id} | O2O 查询 |
| POST | /getFlipInfos | 批量查询 |
| POST | /report/list | 报表列表 |
| POST | /check/can/evaluate | 检查是否可评价 |
| GET | /check/flip/status | 查询面授状态 |
| POST | verify/duration | 学时核验 |
| GET | fetch/meeting/info/{flipId} | 获取会议信息 |
| POST | reserve/meeting | 预约会议 |
