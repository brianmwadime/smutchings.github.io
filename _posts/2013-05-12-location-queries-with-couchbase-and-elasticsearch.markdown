---
layout: post
title: Location queries with Couchbase and Elasticsearch
date: 2013-05-12 18:53:10.000000000 +02:00
---
I recently changed my geolocation queries from <a href="http://couchbase.com">Couchbase</a> GeoCouch to <a href="http://www.elasticsearch.org">Elasticsearch</a> since Elasticsearch offers more flexibility with the search parameters. However, the switch was not as easy as I thought so with some help from <a href="https://twitter.com/clintongormley">Clinton</a> I wrote together some information on how to replicate from Couchbase to Elasticsearch and write a first geo query.

There is a <a href="http://www.couchbase.com/docs/couchbase-elasticsearch/index.html">good tutorial on how to install the Couchbase-Elasticsearch-Plugin</a> and configure the XDCR (Cross Datacenter Replication), which is required to get started.

The first thing that didn't really work for me in Elasticsearch was the PUT update of an index with the geolocation properties, so it is required to DELETE the current index and create (POST) a new one with the JSON below:

<code><pre>{
   "mappings" : {
      "couchbaseDocument" : {
         "properties" : {
            "doc" : {
               "type" : "object",
               "properties" : {
                  "location" : {
                     "lat_lon" : 1,
                     "type" : "geo_point"
                  }
               }
            }
         }
      }
   }
}</pre></code>

Response:
<code><pre>{
   "ok": true,
   "acknowledged": true
}</pre></code>

After that re-create the replication from Couchbase to make sure the index is up to date.

This maps the "location" attribute to a lat_lon index in Elasticsearch. Your Couchbase document should look something like this:

<code><pre>{
    "type": "location",
    "location": {
      "lat": 41.387008,
      "lon": 2.170036
    }
}</pre></code>

To query for objects around <a href="http://maps.google.com/maps?q=41.387008,2.170036&amp;num=1&amp;t=h&amp;z=17">Pl. Catalunya in Barcelona</a>, use the following query:

<code><pre>{
   "query": {
      "filtered": {
         "query": {
            "match_all": {}
         },
         "filter": {
            "geo_distance": {
               "distance": "5km",
               "doc.location": {
                  "lat": 41.387008,
                  "lon": 2.170036
               }
            }
         }
      }
   }
}</pre></code>

Hope this helps.
