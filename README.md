# Monitoring FIO QoS parameters using Prometheus Grok Exporter, InfluxDB and Grafana
Flexible IO tester (FIO) is an open-source synthetic benchmark tool. FIO can generate various IO workloads: sequential reads or random writes, synchronous or asynchronous, all based on the options provided by the user. FIO is the easiest and versatile tool to quickly perform IO performance tests on storage system, and allows you to simulate different types of IO loads. 
 
Prometheus is an open source monitoring solution that stores all its data in a time series database. Prometheus has a multi-dimensional data-model and a powerful query language that is used to generate reports of the resources being monitored. Grafana allows you to query, visualize, alert on and understand your metrics no matter where they are stored. Grok is a tool to parse crappy unstructured log data into something structured and queryable to Prometheus server.

![high-level-figure](https://github.com/sumitshatwara/prometheus-grafana-grok-fio-influxdb/blob/master/Screenshots/high-level-figure.png)

FIO tool generates an unstructured output that is not recognized by Prometheus. That is where Grok-exporter appears, which will the help fetching the required QoS parameters (IOPS, Latency and Bandwidth), and transform them into metric name and key/value pairs. Once the data is queryable to Prometheus and it can be visualized with the help of Grafana dashboard.

However, Prometheus storage engine is designed for keeping mainly the short-term data. This gap can be filled in by InfluxDB time-series database having it to store the long-term data and perform monitoring from Grafana dashboard utilizing InfluxDB as a data source.

All the commands, grok config file, setup guide with detailed steps, Grafana dashboard json files and screenshots are attached here for your reference.

For monitoring Ceph Storage cluster as well, Grafana dashboard json and other files are added in Ceph folder.

