## 查询文档

### 查询单个文档

```
GET blog_index/user/7XcMIW4BmdCR56kZ_30N
```
响应如下时表示查询成功：

```
{
  "_index" : "blog_index",
  "_type" : "user",
  "_id" : "7XcMIW4BmdCR56kZ_30N",
  "_version" : 1,
  "found" : true,
  "_source" : {
    "title" : "manager1",
    "name" : "Tom1",
    "age" : 35
  }
}

```


### 批量查询文档

```
GET blog_index/user/_search
```
响应如下时表示查询成功：
```
{
  "took" : 3,
  "timed_out" : false,
  "_shards" : {
    "total" : 5,
    "successful" : 5,
    "skipped" : 0,
    "failed" : 0
  },
  "hits" : {
    "total" : 6,
    "max_score" : 1.0,
    "hits" : [
      {
        "_index" : "blog_index",
        "_type" : "user",
        "_id" : "LZUHIW4BV7zpY8wX5j3q",
        "_score" : 1.0,
        "_source" : {
          "title" : "manager2",
          "name" : "Tom2",
          "age" : 36
        }
      },
      {
        "_index" : "blog_index",
        "_type" : "user",
        "_id" : "7XcMIW4BmdCR56kZ_30N",
        "_score" : 1.0,
        "_source" : {
          "title" : "manager1",
          "name" : "Tom1",
          "age" : 35
        }
      },
      {
        "_index" : "blog_index",
        "_type" : "user",
        "_id" : "LpUHIW4BV7zpY8wX5j3q",
        "_score" : 1.0,
        "_source" : {
          "title" : "manager3",
          "name" : "Tom3",
          "age" : 37
        }
      }
    ]
  }
}

```
