# addLiveStreamAppRecord


## 描述
添加应用级别直播录制配置
- 添加应用级别的直播录制模板配置


## 请求方式
POST

## 请求地址
https://live.jdcloud-api.com/v1/recordApps:config


## 请求参数
|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**publishDomain**|String|True| |推流域名|
|**appName**|String|True| |应用名称|
|**template**|String|True| |录制模版|


## 返回参数
|名称|类型|描述|
|---|---|---|
|**requestId**|String|requestId|


## 返回码
|返回码|描述|
|---|---|
|**200**|OK|
|**400**|Invalid parameter|
|**401**|Authentication failed|
|**404**|Not found|
|**500**|Internal server error|
|**503**|Service unavailable|

## 请求示例
POST
```
https://live.jdcloud-api.com/v1/recordApps:config
```

```
{
    "appName": "yourapp", 
    "publishDomain": "push.yourdomain.com", 
    "template": "yourrecordtemplate"
}
```

## 返回示例
```
{
    "requestId": "bgvmivir54gddpgi764se9f4kfr7ge41"
}
```
