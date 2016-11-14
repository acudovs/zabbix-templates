# *elastic*. Template App Elasticsearch - Elasticsearch cluster monitoring

Template App Elasticsearch is Zabbix template for monitoring of Elasticsearch
clusters.

This template discovers and monitors the entire Elasticsearch cluster state and
all nodes state. To not overwhelm Zabbix database with duplicate data link this
template to a single host which will monitor the entire cluster or use discovery
parameter 'node=local' or 'node=HOSTNAME' to create only local node items or
create items on specified node only.

## Requires

python-elasticsearch
