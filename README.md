# About
A Docker Engine API Proxy for Prometheus/Promtail service discovery

## Usage

```yml
services:

  prometheus-service-discovery:
    image: swarmlibs/prometheus-service-discovery:0.1.0-rc.1
    hostname: prometheus-service-discovery.internal
    networks:
      prometheus_gwnetwork:
    volumes:
      - type: bind
        source: /var/run/docker.sock
        target: /var/run/docker.sock
        read_only: true

networks:
  prometheus_gwnetwork:
    name: prometheus_gwnetwork
    external: true
```
