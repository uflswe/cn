# 变更配置
云搜索Elasticsearch支持用户跟进业务需要，动态调整节点规格、存储规格、节点数量、专用主节点规格、协调节点规格和数量，其中节点数量支持缩容，其他参数仅支持扩容操作，且一次仅支持修改其中一个属性，如您想要修改多个配置属性，请对应多次进行修改。变更配置后可以通过查询集群详细信息看是否变配成功。

## 前提条件
1. 实例为运行状态
2. 节点数量的缩容还需要同时保证专有主节点已开启和集群状态为绿色

## 注意事项

- 本地盘ES升级规格，必须要专有主节点；

- 减少数据节点数量，必须要专有主节点；

- 数据节点数量只可增加不能减少；

- 专有主节点，可以升级和降低规格，数量不可修改；
- 协调节点，可以升级和降低规格，以及增加和减少节点数量；

## 操作步骤

1. 登录[云搜索Elasticsearch 控制台](https://es-console.jdcloud.com/clusters)。</br>
2. 在云搜索Elasticsearch集群列表页，选择要扩容的集群，点击“操作-更多-变更配置”进行集群参数变更的设置。
 
 ![查询1](https://github.com/jdcloudcom/cn/blob/es-2021/image/Internet-Middleware/JCS%20for%20Elasticsearch/变配_2020.png)


