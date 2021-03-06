# data-assemble-engine
## 数据装配引擎功能描述：
1. 将分库分表的关系形数据库（Mysql|RDS）数据，通过binlog采集，将数据库表中的增、删、改的数据传入消息系统（Kakfa）
2. 后台管理通过一对多、多对多、多对一的业务配置文件，将kafka消息数据装配成非结构化json数据
3. 将非结构化数据Json文档落盘到搜索引擎、mongdb等非关系形数据库
4. 对外提供跨库、跨表关联查询的数据接口服务

## 解决痛点：
1. 采用微服务架构之后分库、分表关联查询性能差，数据库cpu飙升，查询接口经常超时的情况
2. 多表查询散落到各个业务方，没办法统一管理业务数据及实时计算指标
3. 每个业务组，消费其他业务组的数据，自己做数据冗余的表，开发周期长，没法统一维护、监控告警接入成本高

