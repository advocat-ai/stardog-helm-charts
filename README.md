Stardog Helm Charts
===================

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![<ORG_NAME>](https://circleci.com/gh/stardog-union/helm-charts.svg?style=shield&circle-token=213cf9bca0acf5d3945dfd5d746b48f1c2d436e0)](https://app.circleci.com/pipelines/gh/stardog-union/helm-charts)

These charts install the Stardog Knowledge Graph platform on Kubernetes.

Stardog documentation: https://www.stardog.com/docs

Highlights
----------

As of version 2.0.0 of the Stardog Helm charts, ZooKeeper 3.5.7 is now deployed
with the [Bitnami](https://github.com/bitnami/charts/tree/master/bitnami/zookeeper)
ZooKeeper chart. Stardog 7.4.2 includes preview support for ZooKeeper 3.5.x so you
must be running that version of Stardog or later. Please see the Stardog chart
[README](https://github.com/stardog-union/helm-charts/blob/master/charts/stardog/README.md)
for instructions on how to upgrade from version 1.x of the charts to version 2.

We strongly recommend that the charts request at least 2 CPUs or more for Stardog.
By default the Stardog chart requests 2 CPUs. This value can be configured in the
`values.yaml` file.

Prerequisites
-------------

- Stardog Cluster license file
- Helm v3
- Persistent volume support
- Load balancer service
- Familiarity with Stardog Cluster
- Familiarity with Apache ZooKeeper

Installing
----------

```
$ kubectl -n <your-namespace> create secret generic stardog-license --from-file stardog-license-key.bin=/path/to/stardog-license-key.bin
$ helm repo add stardog https://stardog-union.github.io/helm-charts/
$ helm install <helm-release-name> --namespace <your-namespace> stardog/stardog
```

See the Stardog chart's [README](https://github.com/stardog-union/helm-charts/blob/master/charts/stardog/README.md)
for a list of configuration parameters.

Deleting
--------

```
$ helm delete <helm-release-name> --namespace <your-namespace>
```

Usage
-----

[Helm](https://helm.sh) must be installed to use the charts.  Please refer to
Helm's [documentation](https://helm.sh/docs) to get started.

Once Helm has been set up correctly, add the repo as follows:

  helm repo add <alias> https://<orgname>.github.io/helm-charts

If you had already added this repo earlier, run `helm repo update` to retrieve
the latest versions of the packages.  You can then run `helm search repo
<alias>` to see the charts.

To install the <chart-name> chart:

    helm install my-<chart-name> <alias>/<chart-name>

To uninstall the chart:

    helm delete my-<chart-name>