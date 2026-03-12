# 系统架构

**最后更新**: 2026-03-11

## 整体架构

```
外部系统
    │ /facade/flip/**（向下兼容，不可破坏）
    ▼
┌─────────────────────────────────────────┐
│              flipapp（后端）              │
│                                         │
│  controller/facade/   ← 对外 Facade     │
│  controller/api/      ← 内部 API        │
│  controller/f2f/      ← F2F 专项        │
│  controller/register/ ← 注册            │
│                                         │
│  service/  →  mapper/  →  entity/       │
│  manage/  （跨 Service 编排）            │
│                                         │
│  ┌──────────────┐                       │
│  │  attendeng   │ ← 考勤子模块（独立）   │
│  └──────────────┘                       │
└─────────────────────────────────────────┘
    │
    ▼
flipstu-pc（前端 Vue.js）
│  views/flip-mgmt/     ← 课程管理
│  views/flip-console/  ← 课程控制台
│  views/fields/        ← 字段设置
│  views/stu/           ← 学员视角
```

## 子模块说明

| 模块 | 路径 | 职责 |
|------|------|------|
| flipapp（后端核心） | `flipapp/flipapp/` | 课程管理全部业务逻辑 |
| attendeng（考勤引擎） | `flipapp/attendeng/` | 考勤独立子系统，通过 Wrapper 与主模块交互 |
| flipstu-pc（前端） | `flipstu-pc/` | 学生端 PC Web，Vue.js |

## 关键依赖

- `com.yxt.common.*` — 公共工具库（认证、分页、API 封装）
- MyBatis Plus — ORM
- Nacos — 服务注册与配置中心
- Sentinel — 限流熔断
- `UlcdArrangeFacade` — 外部培训计划对接

## 对外接口（受保护）

`FacadeFlipController` → `/facade/flip/**`，有外部客户在使用。
**所有端点只能新增，不能修改路径/方法/响应结构，不能删除。**
