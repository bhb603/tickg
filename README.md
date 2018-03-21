# TIG

The TIG Stack (Telegraf, InfluxDB, Grafana) implemented in `docker-compose`.

## Quickstart

```
docker-compose up -d
```

**Notes**
- Grafana will be available at http://localhost:3000
- Access the InfluxDB CLI directly with:
  ```
  docker-compose exec influxdb influx
  ```
- Data volumes in the influxdb and grafana containers are mounted to `./influxdb` and `./grafana` respectively, so data and configuration changes should persist through docker restarts
- Telegraf is setup as a [StatsD](https://github.com/influxdata/telegraf/tree/master/plugins/inputs/statsd) server. Send metrics with UDP protocol to port 8125:
  ```
  echo "foo:1|c" | nc -u -w0 127.0.0.1 8125
  ```
