# F-001 课程管理 API 契约测试规格

**最后更新**: 2026-03-11

## 内部 API 契约

### TC-01 创建面授

```
When:  POST /flip/createFlipInfo
Body:  { flipName: "测试面授", orgId: "xxx", ... }
Then:  HTTP 200, body = Long (新建 ID)
```

### TC-02 查询面授详情

```
When:  GET /flip/{id}?bizId=xxx
Then:  HTTP 200
       body 包含 { id, flipName, publishState, enableAttend, enableSignIn }
```

### TC-03 更新发布状态

```
When:  PUT /flip/{publishState}
Body:  { flipIds: [...], orgId: "xxx" }
Then:  HTTP 200
```

### TC-04 删除面授

```
Given: publishState = 0 (草稿)
When:  DELETE /flip/{flipId}
Then:  HTTP 200
```

### TC-05 面授报表列表

```
When:  POST /flip/report/list
Body:  { page: 1, pageSize: 10, orgId: "xxx" }
Then:  HTTP 200, body 包含分页结构 { total, list }
```

### TC-06 检查是否可评价

```
When:  POST /flip/check/can/evaluate
Then:  HTTP 200, body = FlipCanEvaluateResp
```

## 单元测试（无需基础设施）

已实现文件：
- `FlipStatusEnmuTest.java` — 状态流转逻辑
- `FlipDetailEntityTest.java` — 实体字段完整性
- `FlipEnumsTest.java` — 枚举值合法性
