# TIG

The TIG Stack (Telegraf, InfluxDB, Grafana) implemented in `docker-compose`.

## Quickstart

Start influxdb first, followed by the other services:
```
docker-compose up -d influxdb
docker-compose up -d telegraf grafana
```

Grafana dashboard will be available at http://localhost:3000.

Data volumes in the influxdb and grafana containers are mounted to `./influxdb` and `./grafana` respectively, so data and configuration changes should persist.
