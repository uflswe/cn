# updateCategory


## 描述
修改分类

## 请求方式
PUT

## 请求地址
https://vod.jdcloud-api.com/v1/categories/{categoryId}

|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**categoryId**|Long|True| |分类ID|

## 请求参数
|名称|类型|是否必需|默认值|描述|
|---|---|---|---|---|
|**name**|String|False| |分类名称|
|**parentId**|Long|False| |父分类ID，取值为 0 或 null 时，表示该分类为一级分类<br>|
|**description**|String|False| |分类描述信息|


## 返回参数
|名称|类型|描述|
|---|---|---|
|**result**|[Result](updatecategory#result)|修改分类结果|
|**requestId**|String|请求ID|

### <div id="result">Result</div>
|名称|类型|描述|
|---|---|---|
|**id**|Long|分类ID|
|**name**|String|分类名称|
|**level**|Integer|分类级别。取值范围为 [0, 3]，取值为 0 时为虚拟根节点<br>|
|**parentId**|Long|父分类ID，取值为 0 或 null 时，表示该分类为一级分类<br>|
|**description**|String|分类描述信息|
|**createTime**|String|创建时间|
|**updateTime**|String|修改时间|

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
PUT
```
https://vod.jdcloud-api.com/v1/categories/1

```

```
{
    "description": "电视台", 
    "name": "TV", 
    "parentId": 0
}
```

## 返回示例
```
{
    "requestId": "edfc74ea-be4c-418b-b841-31ddd2b33203", 
    "result": {
        "createTime": "2019-04-16T15:51:32Z", 
        "description": "电视台", 
        "id": 1, 
        "level": 1, 
        "name": "TV", 
        "parentId": 0, 
        "updateTime": "2019-04-16T15:51:32Z"
    }
}
```
