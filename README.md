# elastic-search-useful-command
Some useful commands you would need while working with elastic search

* Get all docs
```
curl -XGET 'http://localhost:9200/_search?pretty'
```

* Get docs for an index(news_index_v1)
```
curl -XGET 'http://localhost:9200/index_name/_search?pretty'
```
* Get all indices
```
curl -XGET 'http://localhost:9200/_cat/indices?v'
```
* Delete an index
```
curl -XDELETE 'http://localhost:9200/index_name?pretty'
```
* Delete a doc
```
curl -XDELETE 'http://localhost:9200/index_name/type/{id}'
```
* Create index
```
curl -XPUT 'http://localhost:9200/index_name?pretty'
```
* Delete docs of index
```
curl -XDELETE 'http://localhost:9200/index_name?pretty'
```
* Index status
```
curl -XGET 'http://localhost:9200/index_name/_stats'
```
* search docs
```
curl -XGET 'http://localhost:9200/index_name/_search?pretty' -H 'Content-Type: application/json' -d'
{
  "query": {
    "multi_match" : {
      "query":      "super bowl",
      "type":       "most_fields",
      "fields":     [ "title", "description" ]
    }
  }
}'
```
