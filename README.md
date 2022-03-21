# Grafana Monitoring
This Project will setup basic monitoring possibilities.

This Setup includes
- Prometheus at Port 9090
- Grafana at Port 3000

## Requirements
- Docker and Docker-Compose - make sure to allow your docker setup
    at minimum 2GB RAM for this docker setup.

## Setup
Create prometheus file. It's currently ignored because I do have a
knowledge lag on handling env vars here and I do not want to expose
hosts and passwords.

```bash
cp ./etc/prometheus/prometheus.example.yml ./etc/prometheus/prometheus.yml
```

Add Jobs to Scrape configs. Here is an example:
```yaml
scrape_configs:
  # The job name is added as a label `job=<job_name>` to any timeseries scraped from this config.
  - job_name: 'kafka'

    # metrics_path defaults to '/metrics'
    # scheme defaults to 'http'.

    static_configs:
    - targets: ['jmx-kafka101:5556','jmx-kafka102:5556', 'jmx-kafka103:5556']
```


```bash
docker-compose up -d
```

As soon as your containers are running, go to
`http://{{GRAFANA_HOST}}:3000` and sign in with
- username: admin
- password: admin


**Note** The Kafka Dashboards are copied from another repository:
https://github.com/streamthoughts/kafka-monitoring-stack-docker-compose

I love Open Source! :heart:
