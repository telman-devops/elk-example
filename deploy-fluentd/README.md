### Deploy Fluentd | Configure collecting and visualising logs

##### install Fluentd
    helm repo add bitnami https://charts.bitnami.com/bitnami
    helm install fluentd bitnami/fluentd

- run on every node
- processes collected data

In deamonset volumes, we can see path for scraping

```yaml
hostPath:
  path: /var/lib/docker/containers
  type: ''
```

_fluentd-config_ show how fluentd should process the logs
[fluentd-config.yaml](fluentd-config-3.yaml)

