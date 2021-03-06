# MariaDB 创建备份
云数据库 MariaDB 实例的备份触发方式支持自动备份和手动备份两种方式；您可以通过修改备份策略来设置自动备份触发的时间点，具体操作请参考 [备份策略](../Backup-Policy/MariaDB-Backup-Policy.md)。
实例的备份会存放在京东云的云存储服务上，目前京东云暂不收取备份所产生的空间占用费用。

对于采用云盘的数据库实例，还支持采用 **“云盘快照”** 的方式进行备份。云盘快照是利用云盘的机制，对数据进行备份、恢复以及扩容，跟传统备份方式相比，**云盘快照备份性能可提升5-10倍以上**。

|特性|传统物理备份|云盘快照备份|
|-|-|-|
|备份、恢复性能|一般|高，通常比传统方式高5-10倍以上|
|跨地域备份同步|支持|仅非加密云盘支持|
|备份下载|支持|不支持|
|根据备份创建|存储空间必须大于实际数据量|存储空间必须大于等于当前存储空间|
|根据时间点创建|存储空间必须大于实际数据量|存储空间必须大于等于当前存储空间|


开启云盘快照备份后，系统会自动将使用云盘的实例切换到快照备份的模式。为确保实例的可恢复性，会有7天的并行窗口时间，期间传统的物理备份和快照备份都会进行。前7天，只展示物理备份；7天后，展示快照备份。

## 创建手动备份
1. 登录 [云数据库 RDS 控制台](https://rds-console.jdcloud.com/database) 。
2. 选择需要进行设置手动备份的目标实例，点击目标实例的名称，进入到实例详情页。
3. 选择 **备份管理** 标签，点击 **创建备份** 按钮，创建备份弹出框参数说明如下：
    * 备份名称：允许重复，名称的长度和字符有一定限制，具体以控制台为准。
    * 点击 **确认**按钮，完成创建备份的操作。
    * 点击 **取消**按钮，放弃创建备份的操作。

    ![创建备份](../../../../../../image/RDS/Create-Backup.png)

4. 点击 **确定** 按钮，返回到备份列表页，手动备份开始创建。
