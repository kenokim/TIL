# Prometheus
## prometheus server
- retrieval: pulls metrics data from targets, such as applications, services
- storage: stores metrics data, time series data
- HTTP server: accepts PromQL queries, then query storage

## targets
- server, tomcat, applications, database, services, ...

## metrics
- metric entry: help + type
  - type: 3 types, counter, gauge, histogram
 
## exporters
- ex. node exporter, mysql exporter

## client libraries
- java libraries, ...

## push vs. pull
- AWS cloudwatch, new relic: push
- prometheus: pull
- pushgateway: for jobs to push metrics
