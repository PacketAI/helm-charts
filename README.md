# PacketAI Helm Charts

![License](https://img.shields.io/badge/License-PacketAI-blue.svg)

## Usage

[Helm](https://helm.sh) must be installed to use the charts.
Please refer to Helm's [documentation](https://helm.sh/docs/) to get started.

Once Helm is set up properly, add the repo as follows:

```console
helm repo add packetai https://packetai.github.io/helm-charts
# install packetai-agent helm chart 
helm install packetai packetai/packetai-agent
```

You can then run `helm search repo packetai` to see the charts.

## Contributing

The source code of `PakcetAI` [Helm](https://helm.sh) chart can be found on Github: <https://github.com/packetai/helm-charts/tree/main/charts>


## License

<!-- Keep full URL links to repo files because this README syncs from main to gh-pages.  -->
PacketAI License.

## Helm charts build status

![Release Charts](https://github.com/packetai/helm-charts/workflows/Release%20Charts/badge.svg?branch=main)