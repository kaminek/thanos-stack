# Quickstart for Thanos

Get up and running with Thanos, Prometheus, Grafana, Alertmanager, cAdvisor and Node Exporter with a `docker-compose.yaml` file in less than 5 minutes.

## Running the example

```bash
docker-compose up -d
```

The following services will be installed (and some are accessible via browser):

| Component                     | Description                                                               | URL                           |
| -----------------------       | ------------------------------------------------------                    | ----------------------------- |
| prometheus-1                  | Prometheus Server 1 (labels: cluster=paris, replica=r1)                   | <http://localhost:9081/>      |
| prometheus-2                  | Prometheus Server 2 (labels: cluster=paris, replica=r2)                   | <http://localhost:9082/>      |
| thanos-sidecar-1              | Thanos Sidecar for Prometheus Server 1                                    | not accessible via browser    |
| thanos-sidecar-2              | Thanos Sidecar for Prometheus Server 2                                    | not accessible via browser    |
| thanos-query-frontend         | Thanos Query Frontend                                                     | <http://localhost:10901/>     |
| thanos-querier                | Thanos Querier                                                            | <http://localhost:10902/>     |
| thanos-ruler                  | Thanos Ruler                                                              | <http://localhost:10903/>     |
| thanos-bucket-web             | Thanos Bucket Web                                                         | <http://localhost:10904/>     |
| thanos-store-gateway          | Thanos Store Gateway                                                      | not accessible via browser    |
| thanos-compactor              | Thanos Compactor                                                          | not accessible via browser    |
| minio (disabled)              | Minio - Amazon S3 Compatible Object Storage                               | <http://localhost:9000/>      |
| alertmanager                  | Alertmanager                                                              | <http://localhost:9093/>      |
| grafana                       | Grafana                                                                   | <http://localhost:3000/>      |
| cadvisor                      | cAdvisor                                                                  | <http://localhost:8080/>      |
| node-exporter (localhost)     | Node Exporter                                                             | <http://localhost:9100/>      |

## Credentials

Grafana:

```bash
username - admin
password - admin (Password is stored in the `/grafana/config monitoring` env file)
```
  
Minio (disabled):

```bash
Access Key - smth
Secret Key - Need8Chars (Keys are stored in the `docker-compose.yaml` file)
```

## Explore metrics

* Explore metrics via Grafana <http://localhost:3000/explore> or the Thanos Query Frontend <http://localhost:10901>
