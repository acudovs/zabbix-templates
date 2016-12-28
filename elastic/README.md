# *elastic*. Template App Elasticsearch - Elasticsearch cluster monitoring

Template App Elasticsearch is Zabbix template for monitoring of Elasticsearch
clusters.

This template discovers and monitors the entire Elasticsearch cluster state and
all nodes state. To not overwhelm Zabbix database with duplicate data link this
template to a single host which will monitor the entire cluster or use discovery
parameter 'node=local' or 'node=HOSTNAME' to create only local node items or
create items on specified node only. For node parameter to work node.name in
elasticsearch.yml should match server hostname or fqdn.

To collect more metrics just create new item prototypes in Zabbix Web UI:
Templates -> Template App Elasticsearch ->
    Discovery rules -> Item prototypes of Elasticsearch nodes discovery

To find item names execute the following commands in server console:
```
./elastic localhost:9200 --help
./elastic localhost:9200 /nodes/stats/nodes
./elastic localhost:9200 /nodes/stats/nodes/<NODE_ID>
./elastic localhost:9200 /nodes/stats/nodes/<NODE_ID>/jvm/mem -d
./elastic localhost:9200 /nodes/stats/nodes/<NODE_ID>/jvm/mem metric=jvm -d
```

General form is:
```
./elastic localhost:9200 <metric_path> metric=<metric_name>
```

## Requires

python-elasticsearch
