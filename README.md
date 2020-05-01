# ZeeQS Helm Chart

DO NOT USE

Now part of the official [zeebe-io](https://github.com/zeebe-io/zeebe-zeeqs-helm) helm charts.

This functionality is in beta and is subject to change. The design and code is less mature than official GA features and is being provided as-is with no warranties. Beta features are not subject to the support SLA of official GA features.

## Requirements

- [Helm](https://helm.sh/) >= 2.8.0
- Kubernetes >= 1.8
- Minimum cluster requirements include the following to run this chart with default settings. All of these settings are configurable.
  - Three Kubernetes nodes to respect the default "hard" affinity settings
  - 1GB of RAM for the JVM heap

## Usage notes and getting started

## Installing

- Add the official zeebe helm charts repo
  ```
  helm repo add zeebe https://helm.zeebe.io
  ```
- Install it

  ```
  helm install --name zeeqs zeebe/zeeqs --set global.hazelcast=<YOUR HAZELCAST CLUSTER NAME>
  ```

## Configuration

| Parameter          | Description                                                     | Default        |
| ------------------ | --------------------------------------------------------------- | -------------- |
| `global.hazelcast` | Hazelcast Cluster to connect ZeeQS to                           | hazelcast:5701 |
| `global.hazelcast` | The port that the deployment is running on                      | 9000           |
| `global.replicas`  | How many replicas                                               | 1              |
| `service.type`     | What type of service to use (ClusterIP, LoadBalancer, NodePort) | ClusterIp      |
| `service.port`     | The port exposed by the service                                 | 9000           |
