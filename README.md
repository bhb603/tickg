# TICK/G Stack

The "TICK Stack" is a real-time monitoring/analytics solutions from [influxdata](https://www.influxdata.com/). It includes:
- Telegraf: a plugin-driven server agent for collecting & reporting metrics
- InfluxDB: a time-series database
- Chronograf: a web dashboard for data visualization and monitoring
- Kapacitor: a framework for ETL jobs and alerts

[Grafana](https://grafana.com/) is an independent application for data analytics, visualization, and alerting. It can read from InfluxDB (basically replacing Chronograf and Kapacitor in the TICK stack), as well as other data sources.

This project is a docker-compose implementation of the above tools, meant for experimentation and local development.


## Quickstart

```
docker-compose up -d
```

**Notes**
- Grafana: http://localhost:3000
- Chronograf: http://localhost:8888
- Access the InfluxDB CLI directly with:
  ```
  docker-compose exec influxdb influx
  ```
- Telegraf is setup as a [StatsD](https://github.com/influxdata/telegraf/tree/master/plugins/inputs/statsd) server. Send metrics with UDP protocol to port 8125:
  ```
  echo "foo:1|c" | nc -u -w0 127.0.0.1 8125
  ```
