If the value in document is "Lobster", second query will not give result but 1st and 3rd query will give. 
When the String value is indexed the standard analyizer convert the string to lowercase and store in inverted index. So 2nd one don't match.
3rd one matches because match queries also goes to the standard analyzer and hence converted to lowercase and hence matches with the value stored in inverted index. 
Term level queries are better for exact match for numbers etc.

# Full text queries vs term level queries

## Term level queries are not analyzed

```
GET /products/_search
{
  "query": {
    "term": {
      "name": "lobster"
    }
  }
}
```

```
GET /products/_search
{
  "query": {
    "term": {
      "name": "Lobster"
    }
  }
}
```

## Full-text queries are analyzed

```
GET /products/_search
{
  "query": {
    "match": {
      "name": "Lobster"
    }
  }
}
```
