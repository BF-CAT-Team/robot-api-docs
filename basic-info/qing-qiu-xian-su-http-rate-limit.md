---
description: 请求API时的限速
---

# 请求限速  HTTP Rate Limit

#### 为了防止滥用API以及节约成本, 所有的API均有速率限制, 除了特殊标注的API以外, 都遵循以下速率限制

#### 速率限制以单个API为统计单位, 速率限制单位为RPM (Requests Per Minute)

| 速率限制类别 Rate Limit Type | 速率上限 Rate Limit |
| ---------------------- | --------------- |
| 基本查询 Basic Search      | 10RPM           |
| 批量查询 Batch Search      | 10RPM           |
| 核心操作 Core Operation    | 1RPM            |
| 已缓存 Cache              | No Limit        |

#### 如果您拥有token, 则速率上限最大将会支持以下限制

<table><thead><tr><th width="533">速率限制类别 Rate Limit Type</th><th>速率上限 Rate Limit</th></tr></thead><tbody><tr><td>基本与批量查询 Basic And Batch Search</td><td>10000RPM*</td></tr><tr><td>核心操作 Core Operation</td><td>100RPM*</td></tr><tr><td>跳过缓存 Skip Cache</td><td>No Limit</td></tr></tbody></table>

_\*此数据为持有token的请求最高支持的速率, 不代表持有token即可达到此限制_
