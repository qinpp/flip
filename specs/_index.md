# Flip — SDD 规格索引

**最后更新**: 2026-03-11 | **adopt 状态**: Phase 2 完成

## 产品

- [产品愿景](product/product-vision.md)
- [Feature 路线图](product/feature-roadmap.md)

## Feature 列表

| Feature | 状态 | feature-scope |
|---------|------|--------------|
| F-001 课程管理 | stable | [链接](product/features/F-001-课程管理/feature-scope.md) |
| F-002 字段设置 | stable | [链接](product/features/F-002-字段设置/feature-scope.md) |
| F-003 分组管理 | stable | [链接](product/features/F-003-分组管理/feature-scope.md) |
| F-004 用户认证 | stable | [链接](product/features/F-004-用户认证/feature-scope.md) |
| F-005 考试 | stable | [链接](product/features/F-005-考试/feature-scope.md) |
| F-006 投票 | stable | [链接](product/features/F-006-投票/feature-scope.md) |
| F-007 问答 | stable | [链接](product/features/F-007-问答/feature-scope.md) |
| F-008 问卷调查 | stable | [链接](product/features/F-008-问卷调查/feature-scope.md) |
| F-009 外部用户 | stable | [链接](product/features/F-009-外部用户/feature-scope.md) |
| F-010 考勤 | stable | [链接](product/features/F-010-考勤/feature-scope.md) |
| F-011 F2F | stable | [链接](product/features/F-011-F2F/feature-scope.md) |

## 工程规格

- [系统架构](engineering/system-architecture.md)
- [共享 Domain](engineering/shared-domains.md)

## 测试

- [测试策略](test/test-strategy.md)

## adopt 进度

| Phase | 状态 |
|-------|------|
| Phase 1: 扫描与理解 | ✅ 完成 |
| Phase 2: 全量规格提取 | ✅ 完成 |
| Phase 3: 测试安全网 | ✅ 完成（18 单元测试全绿，API 契约规格已记录） |
| Phase 4: 服务门面 | ✅ 完成 |

## 服务门面

- [Facade README](../facade/README.md)
- [面授核心能力](../facade/capabilities/flip-core.yaml)（15 个端点）
- [外部用户能力](../facade/capabilities/external-user.yaml)（8 个端点）
- [场次能力](../facade/capabilities/flip-scene.yaml)（4 个端点）
- [满意度能力](../facade/capabilities/flip-satisfaction.yaml)（6 个端点）
- [核心实体定义](../facade/entities/core-entities.yaml)
- [交叉验证报告](../facade/validation.md)
