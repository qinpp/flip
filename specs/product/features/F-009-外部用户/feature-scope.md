# F-009 外部用户

**最后更新**: 2026-03-11 | **状态**: stable

## 功能范围

**外部用户**的接入与管理，支持非平台内部用户参与面授。

### 核心能力

| 能力 | 描述 |
|------|------|
| 外部用户配置 | 为面授配置外部用户接入规则 |
| 外部用户列表 | 分页查询外部用户 |
| 新增外部用户 | 批量添加外部用户 |
| 删除外部用户 | 单条/批量删除 |
| 查询外部用户 | 按机构/面授/用户 ID 查询 |
| 外部用户权限验证 | 通过 Facade 接口验证（受保护） |

### 相关实体

- `FlipExternalUserEntity` — 外部用户
- `FlipExternalUserConfigEntity` — 外部用户配置

## API 路由（Facade，受保护）

基础路径：`/facade/flip`

| 方法 | 路径 | 说明 |
|------|------|------|
| POST | /flipAuth/checkExternalUserAuth/{flipId}/{userId}/{orgId} | 验证外部用户权限 |
| GET | /externalUserConfig/get/{flipId}/{orgId} | 获取外部用户配置 |
| POST | /externalUserConfig/saveOrUpdate | 保存配置 |
| POST | /externalUser/listPage | 分页查询 |
| POST | /externalUser/deleteBatch | 批量删除 |
| POST | /externalUser/delete | 单条删除 |
| POST | /externalUser/saveOrUpdateBatch | 批量新增/更新 |
| GET | /externalUser/get/{orgId}/{flipId}/{userId} | 查询单个用户 |

## 边界与依赖

- **依赖**: F-001（外部用户属于某面授）
- **对外接口**: 上述 Facade 端点受保护，不可修改
