# Prometheus Container for DMM Metrics

This folder contains a minimal Docker image setup for Prometheus that scrapes:

- `https://dmm.nrp-nautilus.io/metrics`

## Files

- `Dockerfile`: Builds a Prometheus image with the provided config.
- `prometheus.yml`: Scrape configuration.

## Build

```bash
docker build -t dmm-prometheus -f etc/prometheus/Dockerfile etc/prometheus
```

## Run

```bash
docker run --rm -p 9090:9090 --name dmm-prometheus dmm-prometheus
```

Then open Prometheus at:

- `http://localhost:9090`

## Notes

- The scrape job uses `scheme: https` and `metrics_path: /metrics`.
- If your environment requires custom TLS settings, update `prometheus.yml` accordingly.
