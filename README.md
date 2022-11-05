# MONITORING HELM CHART
Implementation of the test task.

The projector was developed and tested in minikube v1.26.1.

The chart is based on kube-prometheus-stack with the addition of prometheus-blackbox-exporter. 
In the settings kube-prometheus-stack `./values.yaml` are disabled: 
  - nodeExporter
  - alertmanager
  - kubeStateMetrics
  - kubeApiServer
  - kubelet
  - kubeControllerManager
  - coreDns
  - kubeEtcd
  - kubeScheduler
  - kubeProxy


For deploy the chart is used namespace "unitest".

As endpoint is selected www.google.com. 
`./values.yaml prometheus.prometheusSpec.additionalScrapeConfigs`

Password for Grafana admin is set "unitest123".
`./values.yaml grafana.adminPassword`


## DEPLOY CHART


### Prerequisites

- Kubernetes 1.16+
- Helm 3+

### Copy Helm Chart from GitHub

```console
git clone https://github.com/FaxIv/monitoring.git
```

### Install Helm Chart

```console
helm install monitoring monitoring --namespace unitest --create-namespace
```

### Access to the Grafana

```console
kubectl port-forward -n unitest service/monitoring-grafana 9099:80
```
In your browser, open the 127.0.0.1:9099 (Grafana web interface)
  - login: admin
  - password: unitest123



