---
layout: post
title: First steps with Node.js and CouchDB
date: 2011-09-30 11:45:54.000000000 +02:00
---
<p>Since there is a lot of new fancy stuff around beside Ruby on Rails, I decided to evaluate <a href="http://nodejs.org/">Node.js</a> together with <a href="http://www.couchbase.com/">Couchbase CouchDB</a>. Node is a server-side JavaScript solution to respond to HTTP requests, CouchDB a document-oriented database.</p>

<p>To get them playing along, I chose <a href="http://expressjs.com/">Express</a> as Framework and <a href="https://github.com/dscape/nano">nano</a> as CouchDB connector.</p>

<p><a href="https://github.com/joyent/node/wiki/Installation">Install node.js</a>, then express and nano:<code>
npm install -g express
npm install connect
npm install nano
npm install -d
</code></p>

<p>This is a little example based on the Express application template on how to get data from a CouchDB view. Run the server with node app.js:</p>

<code><pre>
/**
 * Module dependencies.
 */

var express = require('express');
var connect = require('connect');
var nano = require('nano')('http://127.0.0.1:5984')
  , db      = nano.use('test');
var request = require('request');

var app = module.exports = express.createServer();

// Configuration

app.configure(function(){
  app.set('views', __dirname + '/views');
  app.set('view engine', 'jade');
  app.use(connect.logger());
  app.use(express.bodyParser());
  app.use(express.methodOverride());
  app.use(app.router);
  app.use(express.static(__dirname + '/public'));
});

app.configure('development', function(){
  app.use(express.errorHandler({ dumpExceptions: true, showStack: true })); 
});

app.configure('production', function(){
  app.use(express.errorHandler()); 
});


// Routes

app.get('/', function(req, res) {
  data = db.view("hello", "world", {"include_docs":"true"}, 
    function (_,data) {
        console.log(data.rows);
        res.render('helloworld.jade', {data: data.rows});
  });
});

app.listen(3000);

console.log("Express server listening on port %d in %s mode", app.address().port, app.settings.env);
</pre></code>

<p>The corresponding <a href="http://jade-lang.com/">jade</a> template could look like this:</p>

<code><pre>
- for (var k in data)
  each val, key in data[k]
    p #{key}: #{val}
    - if(key == 'value')
      each val2, key2 in val
        p #{key2}: #{val2}
</pre></code>

<p>It was a bit tricky to get the code for the params together, but with <a href="http://stackoverflow.com/questions/1475307/including-documents-in-the-emit-vs-include-docs-true-for-couchdb">include_docs=true</a> you can build fancy database joins and complex applications. For more examples on Nano see <a href="http://writings.nunojob.com/2011/09/getting-started-with-nodejs-and-couchdb.html">this article</a>. Enjoy.</p>
