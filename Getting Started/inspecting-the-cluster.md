# Inspecting the cluster

## Checking the cluster's health

```
GET /_cluster/health
```

## Listing the cluster's nodes

```
GET /_cat/nodes?v
#v query parameter includes descriptive header in the output
```

## Listing the cluster's indices

```
GET /_cat/indices?v&expand_wildcards=all
```
