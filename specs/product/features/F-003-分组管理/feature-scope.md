# F-003 分组管理

**最后更新**: 2026-03-11 | **状态**: stable

## 功能范围

面授学员的**分组管理**，支持手动和自动两种分组方式。

### 核心能力

| 能力 | 描述 |
|------|------|
| 创建分组 | 为面授创建学员分组 |
| 删除分组 | 删除指定分组 |
| 查询分组列表 | 获取面授下所有分组 |
| 查询分组成员 | 获取分组内学员列表（支持分页） |
| 手动分组 | 管理员手动指定分组 |
| 自动分组 | 系统按规则自动分配学员到分组 |
| 更新分组成员 | 调整学员所属分组 |
| 更新分组名称 | 重命名分组 |
| 开启分组看板 | 展示分组协作看板 |

## API 路由

基础路径：`/flipGroup`

| 方法 | 路径 | 说明 |
|------|------|------|
| POST | /saveFlipGroup | 创建分组 |
| POST | /deleteFlipGroup | 删除分组 |
| POST | /getFlipGroupList | 查询分组列表 |
| POST | /getFlipGroupMemberList | 查询分组成员列表 |
| GET | /getFlipGroupMemberPageList | 分页查询成员 |
| POST | /manualFlipGroup | 手动分组 |
| POST | /autoFlipGroup | 自动分组 |
| POST | /updateFlipGroupMember | 更新成员分组 |
| POST | /updateGroupName | 更新分组名称 |
| PUT | /open/board | 开启看板 |
| GET | /check/permission | 检查权限 |
| GET | /get/group/board/info | 获取看板信息 |

## 边界与依赖

- **依赖**: F-001（分组属于某面授）、F-004（权限验证）
