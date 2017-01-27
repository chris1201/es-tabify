# es-tabify

A function that converts ElasticSearch results into a table data structure. The returned table data structure is similar to that returned by [d3-dsv](https://github.com/d3/d3-dsv). Inspired by [Kibana's tabify implementation](https://github.com/elastic/kibana/blob/master/src/ui/public/agg_response/tabify/tabify.js). Compatible with the [official ElasticSearch JavaScript client](https://www.elastic.co/guide/en/elasticsearch/client/javascript-api/current/quick-start.html). Works with `hits` style responses as well as nested aggregations.

# Usage

`npm install es-tabify`

```js
var tabify = require('es-tabify');
var elasticsearch = require('elasticsearch');
var client = new elasticsearch.Client({
  host: 'localhost:9200',
  log: 'trace'
});

client.search({
  q: 'pants'
}).then(function (response) {
  var data = tabify(response);
}, function (error) {
  console.trace(error.message);
});
```
