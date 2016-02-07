---
published: true
layout: post
title: "Play with Apache Solr"
tags:
    - apache
    - solr
comments: True
---

Okay, Solr. It's the first time I play with Solr. I will never know about it if I don't join this company. Let's start with selecting index.

## Select

We can select an index using this command:

``` shell
curl http://localhost:8983/solr/{core}/select?q=id:{id}
```

## Insert / Update

There are two commands to insert or update index. Just remember, the structure should be identical.

### Insert / Update with JSON

``` shell
curl http://localhost:8983/solr/{core}/update?commit=true -H 'Content-type:application/json' -d 
'[
    { 
        "id":"{id}",
        "desc":"{description}"
    }
]'
```

### Insert / Update with XML

``` shell
curl http://localhost:8983/solr/{core}/update?commit=true -H "Content-Type: text/xml" --data-binary 
'<add>
    <doc>
        <field name="id">{id}</field>
        <field name="desc">{description}</field>
    </doc>
</add>'
```

## Delete

There are also two commands to delete index.

### Delete with JSON

``` shell
curl http://localhost:8983/solr/{core}/update?commit=true -H 'Content-type:application/json' -d 
'{
    "delete":{
        "id":"{id}"
    },
    "delete":{
        "query":"id:{id}"
    }
}'
```

### Delete with XML

``` shell
curl http://localhost:8983/solr/{core}/update?commit=true -H "Content-Type: text/xml" --data-binary 
    '<delete>
        <id>{id}</id>
        <query>id:{id}</query>
    </delete>'
```
