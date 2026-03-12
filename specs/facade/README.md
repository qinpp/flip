# 服务门面（Facade）

**最后更新**: 2026-03-11

## 说明

本目录描述 Flip 系统对外提供的服务接口。有外部客户在使用，**所有能力只能新增，不能修改或删除**。

## 基础路径

所有对外接口统一前缀：`/facade/flip`

## 兼容性承诺

标记 `backward_compatible: true` 的接口：
- 路径不可变更
- HTTP 方法不可变更
- 请求/响应字段不可减少（可新增）
- HTTP 状态码语义不可变更

## 目录结构

```
facade/
├── README.md              # 本文件
├── capabilities/          # 按功能分组的能力描述 YAML
│   ├── flip-core.yaml     # 面授核心 CRUD
│   ├── external-user.yaml # 外部用户管理
│   ├── flip-scene.yaml    # 场次管理
│   ├── flip-stats.yaml    # 统计与报表
│   └── flip-satisfaction.yaml # 满意度
├── entities/
│   └── core-entities.yaml # 核心实体与状态定义
└── validation.md          # 交叉验证报告
```
