Implementation of the test task.

The chart is based on kube-prometheus-stack with the addition of prometheus-blackbox-exporter. 
In the settings kube-prometheus-stack (./values.yaml) are disabled: 
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
./values.yaml prometheus.prometheusSpec.additionalScrapeConfigs

Password for Grafana admin is set "unitest123".
./values.yaml grafana.adminPassword


DEPLOY CHART

Requirements:
 - Kubernetes cluster (minikube)
 - Helm

'git clone '

'helm install monitoring monitoring --namespace unitest --create-namespace'

