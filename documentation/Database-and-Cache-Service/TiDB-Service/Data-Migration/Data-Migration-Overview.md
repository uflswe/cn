# 数据迁移概览

分布式数据库 TiDB 支持 MySQL 到 TiDB 的全量迁移，增量迁移，增量数据同步。

1. 全量迁移：方案和步骤可参考文档 [全量数据迁移](Full-Migration.md) 。
2. 增量迁移：需使用DTS进行，具体步骤可参考文档 [增量数据迁移](Incremental-Migration.md) 。
3. 增量数据同步：操作步骤同上，GTID可以从现有的 MySQL 选择一个GTID进行。

例如，如果要实现从 一个 MySQL 实例到 TiDB的在线的迁移，可以将全量迁移和增量迁移相结合。
1. 首先导出 MySQL 全量数据，进行全量迁移。 迁移完成后，验证 TiDB 数据正确性。
2. 然后记录下步骤1 的GTID，从该GTID开始进行 MySQL的增量迁移。迁移过程中可验证数据正确性。
3. 停止对 MySQL 的访问，将业务切换到 TiDB 。
