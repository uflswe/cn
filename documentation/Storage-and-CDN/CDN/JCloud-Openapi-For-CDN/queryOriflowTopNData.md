# queryOriflowTopNData


## 描述
回源带宽topN数据

## 请求方式
POST

## 请求地址
https://cdn.jdcloud-api.com/v1/console:oribdwtopN


## 请求参数
|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**startTime**|String|True| |查询起始时间,UTC时间，格式为:yyyy-MM-dd'T'HH:mm:ss'Z'，示例:2018-10-21T10:00:00Z|
|**endTime**|String|True| |查询截止时间,UTC时间，格式为:yyyy-MM-dd'T'HH:mm:ss'Z'，示例:2018-10-21T10:00:00Z|
|**domain**|String|False| |需要查询的域名, 必须为用户pin下有权限的域名|
|**area**|String|False| | |
|**isp**|String|False| | |
|**groupBy**|String|True| |分组字段,domainType代表按业务类型分组|
|**topCount**|Integer|False| |topN|
|**period**|String|False| |时间粒度，可选值:[oneMin,fiveMin,followTime],followTime只会返回一个汇总后的数据|


## 返回参数
|名称|类型|描述|
|---|---|---|
|**result**|[Result](#result)| |
|**requestId**|String| |

### <div id="Result">Result</div>
|名称|类型|描述|
|---|---|---|
|**oribandwidthTopN**|[OribandwidthTopItem[]](#oribandwidthtopitem)| |
|**oriflowTopN**|[OriflowTopItem[]](#oriflowtopitem)| |
|**oripvTopN**|[OripvTopItem[]](#oripvtopitem)| |
### <div id="OripvTopItem">OripvTopItem</div>
|名称|类型|描述|
|---|---|---|
|**name**|String| |
|**hitpv**|Long| |
|**pv**|Long| |
|**oripv**|Long| |
|**oripvPercent**|String| |
### <div id="OriflowTopItem">OriflowTopItem</div>
|名称|类型|描述|
|---|---|---|
|**name**|String| |
|**oriflow**|Double| |
|**hitflow**|Double| |
|**flow**|Double| |
|**flowPercent**|String| |
### <div id="OribandwidthTopItem">OribandwidthTopItem</div>
|名称|类型|描述|
|---|---|---|
|**name**|String| |
|**total**|Double| |
|**details**|[OriBandwithDetailItem[]](#oribandwithdetailitem)| |
### <div id="OriBandwithDetailItem">OriBandwithDetailItem</div>
|名称|类型|描述|
|---|---|---|
|**timeStamp**|Long| |
|**avgoribandwidth**|Double| |

## 返回码
|返回码|描述|
|---|---|
|**200**|OK|
