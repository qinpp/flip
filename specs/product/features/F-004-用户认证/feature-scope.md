# F-004 用户认证

**最后更新**: 2026-03-11 | **状态**: stable

## 功能范围

验证用户（讲师/学员/外部用户）对面授的访问权限。

### 核心能力

| 能力 | 描述 |
|------|------|
| 讲师权限验证 | 验证当前用户是否为面授讲师 |
| 学员权限验证 | 验证当前用户是否为面授学员 |
| 外部用户权限验证 | 验证外部用户对面授的访问权限 |

## API 路由

基础路径：`/flipAuth`

| 方法 | 路径 | 说明 |
|------|------|------|
| POST | /checkInstructorAuth | 验证讲师权限 |
| POST | /checkMemberAuth | 验证学员权限 |
| POST | /checkExternalUserAuthByFlipId/{flipId}/{userId} | 验证外部用户权限 |

## 边界与依赖

- **依赖**: F-001（需要知道面授信息）、F-009（外部用户表）
- **被依赖**: 几乎所有 Feature 均依赖权限验证
- 认证基础由 `com.yxt.common.service.AuthService` 提供
