# k8s-kafka-cluster
A simple, non-production-ready Kafka cluster Helm chart based on https://strimzi.io/

## Purpose
The goal of this chart is to provide a quick and simple way to deploy a Kafka cluster in Kubernetes. It is designed for development and testing purposes and is not intended for production use. If you need a production-ready Kafka cluster, I would recommend using the Kafka cluster from [Bitnami](https://github.com/bitnami/containers/blob/main/bitnami/kafka/README.md).

## Features
- Easy to deploy: Deploy a Kafka cluster with minimal configuration and effort.
- Based on Strimzi: Leverages the powerful Strimzi operator for Kafka.
- Ideal for Development: Perfect for local development and testing environments.

## Steps to Deploy

```sh
1. Install [operator](https://github.com/strimzi/strimzi-kafka-operator/blob/main/helm-charts/helm3/strimzi-kafka-operator/README.md)
helm install my-strimzi-cluster-operator oci://quay.io/strimzi-helm/strimzi-kafka-operator

2. Create secret for kafka-user
kubectl create secret generic Values.kafka.clustername-creds \
  --from-literal=Values.kafka.username='somepassword' \
  --namespace=Values.kafka.namespace

3.Clone repo and install kafka cluster
git clone https://github.com/ismoilovfk/k8s-kafka-cluster.git

cd k8s-kafka-cluster

helm install my-kafka-cluster .

```