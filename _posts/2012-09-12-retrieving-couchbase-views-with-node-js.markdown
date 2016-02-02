---
layout: post
title: Retrieving Couchbase views with node.js
date: 2012-09-12 11:05:08.000000000 +02:00
---
<p>Couchbase is open source NoSQL for mission-critical systems. If you switch from CouchDB to Couchbase or get started with CouchBase with CouchDB as key-value store, you can use the <a href="https://github.com/elbart/node-memcache">node-memcache</a> library from <a href="https://github.com/elbart">Tim Eggert</a> to get and set documents.</p>
<p><strong>The memcache library only handles strings</strong>, so you have to use JSON.stringify(data) to add a document to the server and JSON.parse(data) after retrieving one.</p>
<p>Unfortunately, the memcache library doesn't work with design documents and views, so you can use <a href="https://github.com/PatrickHeneise/baseview">baseview</a> to add and delete design documents and retrieve view data.</p>
<p>
<code><pre>
npm install baseview

var baseview = require('baseview')('http://127.0.0.1:8092');
baseview.view('design_doc', 'view_name', function(error, data) {
  console.log(error, data);
});
</pre></code>
</p>
<p>baseview also works with spatial views, to retrieve only documents which have a location within a given bounding box. These bounding boxes (bbox) can be imagined as a rectangle on Google Maps. If the document latitude and longitude are within the rectangle, they are returned by the view, otherwise not.</p>

<p>
<code><pre>
baseview.spatial('geo', 'points', {bbox: bbox}, function(error, points) {
    console.log(error, points);
  });</pre></code>
</p>

<p>To get a bounding box from a given location and radius, there's <a href="https://github.com/PatrickHeneise/sparta">sparta</a>, a small library for geo calculations.</p>

<p>
<code><pre>
npm install sparta

sparta = require('sparta')
sparta.boundingBox(41.386549,2.170004,1);
</pre></code>
</p>
<p>This returns a bbox with the center at Plaza Catalunya, Barcelona, Spain with a radius of 1km.</p>
