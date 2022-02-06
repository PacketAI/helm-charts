# PacketAI Helm Charts

![License](https://img.shields.io/badge/License-PacketAI-blue.svg)

## Usage

[Helm](https://helm.sh) must be installed to use the charts.
Please refer to Helm's [documentation](https://helm.sh/docs/) to get started.

Once Helm is set up properly, add the repo as follows:

```console
helm repo add packetai https://packetai.github.io/helm-charts
helm repo update
# install packetai-agent helm chart 
helm install packetai packetai/packetai-agent --set global.xPaiToken=abc --set global.paiApiKey=xyz \
  --set global.apiUrl=https://api-gcpstage.packetai.co  --set global.clusterName=testcluster
```

You can then run `helm search repo packetai` to see the charts.

## Configuration

### Whitelisting namespaces 
- PacketAI agent supports to monitor all resources in a particular namespace, for example if we have the following k8s namespaces, kube-sytem, customns1, customns2, customns3
- If we want to monitor only customns1 and customns2. we could use `--set global.whitelistNamespaces="customns1\,customns2"`, this will ignore all the other namespaces. 
- This configuration only works for namespace level metrics, and logs. For cluster level metrics like api-server, kube-proxy will be collected by PacketAI agent.
### Blacklisting of containers
- PacketAI agent supports to drop metrics and logs of a particular k8s containers
- If we don't want monitor k8s conatiner istio-proxy, secret-container1, we could use `--set global.blacklistContainers="istio-proxy\,secret-container1"`, we will drop the all logs and metrics of kube containers matching istio-proxy or secret-container1
### kube state metrics
- PacketAI agent helm chart depends on kube state metrics helm chart. We could use existing kube state metrics on k8s cluster.
- we could disable the installing of kube state metrics with `--set global.kubeStateMetrics.enabled=false` and setting the existing kube state metrics URL to global.kubeStateMetrics.url="kube-state-metrics-existin-service:8080"

## Contributing

The source code of `PakcetAI` [Helm](https://helm.sh) chart can be found on Github: <https://github.com/packetai/helm-charts/tree/main/charts>


## License

<!-- Keep full URL links to repo files because this README syncs from main to gh-pages.  -->
PacketAI License.

## Helm charts build status

![Release Charts](https://github.com/packetai/helm-charts/workflows/Release%20Charts/badge.svg?branch=main)
