### Spin up Elasticsearch

```bash
docker-compose up
```

### Create index

```bash
curl -s -XPUT http://localhost:9200/book-index-1 --data @book_basic_schema.json -H "Content-Type: application/json"
```

### Upload data

```bash
curl -s -XPOST http://localhost:9200/book-index-1/_bulk --data-binary @bulkdata.txt -H "Content-Type: application/json"
```

### Verify upload (using Kibana)

```
GET /book-index-1/_search
{
  "size": 0,
  "track_total_hits": true
}
```

### Delete index

```bash
curl -s -XDELETE http://localhost:9200/book-index-1
```
