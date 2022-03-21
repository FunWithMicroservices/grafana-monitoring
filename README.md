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

```bash
docker-compose up -d
```

As soon as your containers are running, go to
`http://{{GRAFANA_HOST}}:3000` and sign in with
- username: admin
- password: admin
