# F-008 问卷调查

**最后更新**: 2026-03-11 | **状态**: stable

## 功能范围

面授**满意度问卷调查**，支持学员和讲师两个维度。

### 核心能力

| 能力 | 描述 |
|------|------|
| 学员问卷 | 学员对面授满意度评价 |
| 讲师评价 | 讲师对面授反馈 |
| 外部问卷 | 引用外部调查做满意度（outSurveySatisfaction 字段控制） |
| 满意度计算 | 按问卷平均分或维度单题平均分计算 |

### 相关实体

- `FlipUserSurveyEntity` — 学员问卷记录
- `FlipEvaluateSatisfactionEntity` — 满意度评价

### 前端视图

- `views/flip-console/appraise/stu-survey-track` — 学员问卷跟踪
- `views/flip-console/appraise/tea-survey-track` — 讲师问卷跟踪

### Controller

- `FlipUserSurveyStudentController` — 学员端
- `FlipEvaluateSatisfactionController` — 满意度

## 边界与依赖

- **依赖**: F-001（满意度规则配置在 FlipDetailEntity）
