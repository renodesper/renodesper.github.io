---
published: true
layout: post
title: "Querying Solr from Python with MySolr"
author: Boy Sandy Gladies Arriezona
categories:
    - data source
tags:
    - solr
    - mysolr
comments: True
---

## Introduction

MySolr is an API for Apache's Solr for python. You can install mysolr using your favorite package manager. In the last post I have showed you how to update, select, and delete index using curl. Today, I will show you how we do those things using mysolr.
Basic Configuration

There is nothing special with solr configuration. The first thing you should do is importing Solr from mysolr. If you have done that, you can set the connection. The default connection is http://localhost:8080. After that, we define what we want to query from solr and store it into a variable. You can print it afterward.
Solr Query Example

``` python
from mysolr import Solr

# We can also specify another connection like http://192.168.10.10:8983/solr/{core}
solr = Solr()

query = {'q':'*:*'}
response = solr.search(**query)

documents = response.documents
print documents
```

I've tried to make a summary for mysolr basic usage and this is what I got:

``` python
from mysolr import Solr

# We can also specify another connection like
# solr = Solr() or solr = Solr(auth=('admin', 'admin'))
solr = Solr("http://localhost:8983/solr/{core}")


def insertIndex():
    # Create documents
    documents = [
        {
            'id': 1,
            'field1': 'field content'
        },
        {
            'id': 2,
            'field2': 'field content'
        }
    ]

    # # Index using json with auto commit
    # solr.update(documents, 'json', commit=True)

    solr.update(documents, 'json', commit=False)  # Index using json
    solr.commit()  # Manual commit


def selectIndex(query):
    response = solr.search(**query)

    # For every document in response.documents print document
    for document in response.documents:
        print document


def updateIndex(query):
    response = solr.search(**query)

    # For every document in response.documents update title
    for document in response.documents:
        document['title'] = 'title'

    solr.update(response.documents, commit=True)


# Start here
query = {'q': '*:*'}

# # Inserting index
# insertIndex()

# Selecting index
selectIndex(query)

# # Updating index
# updateIndex(query)
```
