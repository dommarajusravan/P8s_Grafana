# Prometheus

## To install prometheus:

```console
$ cd prometheus
$ helm dependency update
$ cd ..
$ helm install prometheus -f prometheus/values-custom.yml --namespace telemetry --name telemetry-prometheus --wait
```

# Grafana

## To install grafana:

```console
$ helm install grafana -f grafana/values-custom.yml --namespace telemetry --name telemetry-grafana --wait
```

We can access grafana dashboard using EXTERNAL-IP from telemetry namespace under services.

```console
$ kubectl get svc -n telemetry
```

# Uninstall P8s and Grafana

```console
$ helm del --purge telemetry-prometheus

$ helm del --purge telemetry-grafana
```
