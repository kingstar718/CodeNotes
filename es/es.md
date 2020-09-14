#Elastic Search

## 基本概念

### Node和Cluster
es本质上是一个分布式数据库，允许多台服务器协同工作，每台服务器可以运行多个Elastic实例。
单个Elastic实例称为一个节点（node）。一组节点构成一个集群。

### Index
Elastic 会索引所有字段，经过处理后写入一个反向索引（Inverted Index）。查找数据的时候，直接查找该索引。

所以，Elastic 数据管理的顶层单位就叫做 Index（索引）。它是单个数据库的同义词。每个 Index （即数据库）的名字必须是小写。

下面的命令可以查看当前节点的所有 Index。
```shell
$ curl -X GET 'http://localhost:9200/_cat/indices?v'
```

### Document
Index 里面单条的记录称为 Document（文档）。许多条 Document 构成了一个 Index。

Document 使用 JSON 格式表示，下面是一个例子。
```json
{
  "user": "张三",
  "title": "工程师",
  "desc": "数据库管理"
}
```
同一个 Index 里面的 Document，不要求有相同的结构（scheme），但是最好保持相同，这样有利于提高搜索效率。

## 新建和删除Index

新建 Index，可以直接向 Elastic 服务器发出 PUT 请求。下面的例子是新建一个名叫`weather`的 Index。

```shell
$ curl -X PUT 'localhost:9200/weather'
```

服务器返回一个 JSON 对象，里面的`acknowledged`字段表示操作成功。

```json
{
  "acknowledged":true,
  "shards_acknowledged":true
}
```
然后，我们发出 DELETE 请求，删除这个 Index。

```shell
$ curl -X DELETE 'localhost:9200/weather
```
