# Facade API 契约测试规格

**最后更新**: 2026-03-11 | **保护级别**: 向下兼容，不可破坏

> 这些端点有外部客户在使用。测试目的：防止响应结构变化破坏外部客户。

## 测试用例

### TC-01 外部用户权限验证

```
Given: 合法的 flipId / userId / orgId
When:  POST /facade/flip/flipAuth/checkExternalUserAuth/{flipId}/{userId}/{orgId}
Then:  HTTP 200
       响应体包含权限结果（AuthResp 结构不变）
```

### TC-02 获取外部用户配置

```
Given: 合法的 flipId / orgId
When:  GET /facade/flip/externalUserConfig/get/{flipId}/{orgId}
Then:  HTTP 200
       响应体为 FlipExternalUserConfigVo（字段不可减少）
```

### TC-03 分页查询外部用户

```
Given: 合法的分页参数 { page, pageSize, flipId, orgId }
When:  POST /facade/flip/externalUser/listPage
Then:  HTTP 200
       响应体包含 { total, list, pageNum, pageSize }
```

### TC-04 创建面授（Facade）

```
Given: 合法的 Flip4CreateReq { flipName, orgId, ... }
When:  POST /facade/flip/createFlipInfo
Then:  HTTP 200
       响应体为 Long（新建面授 ID，非 null）
```

### TC-05 更新面授（Facade）

```
Given: 已存在的面授 ID + 合法更新参数
When:  PUT /facade/flip/updateFlipInfo
Then:  HTTP 200
       响应体为 Long（面授 ID）
```

### TC-06 删除面授（Facade）

```
Given: 已存在且未发布的面授
When:  DELETE /facade/flip/{flipId}/{orgId}
Then:  HTTP 200
```

### TC-07 查询面授详情（Facade）

```
Given: 已存在的面授 ID / orgId
When:  GET /facade/flip/{id}/{orgId}
Then:  HTTP 200
       响应体包含 { id, flipName, publishState, orgId }（字段不可减少）
```

## 运行前置条件

1. Nacos 配置中心可用
2. MySQL 数据库可用
3. 测试数据：至少一条有效面授记录

## 运行命令

```bash
cd flipapp/flipapp
mvn test -Dtest=FacadeFlipContractTest
```
