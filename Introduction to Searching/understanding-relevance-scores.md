#Difference in query and filter:
  query gives the relevance score and apply relevance logics for searching the document. Filter does not apply relevance for searching, its checks if value is present or not like boolean. Don't use query if relevance score is not required.
# Understanding relevance scores

```
GET /products/_search
{
  "explain": true,
  "query": {
    "term": {
      "name": "lobster"
    }
  }
}
```
