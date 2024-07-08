# k8s-kafka-cluster
A simple, non-production-ready Kafka cluster Helm chart based on https://strimzi.io/
## It is not production ready, if you want deploy kafka cluster for production in k8s, I woud recomend you kafka cluster from [Bitnami](https://github.com/bitnami/containers/blob/main/bitnami/kafka/README.md).
## Steps to deploy
```sh
kubectl create secret generic Values.kafka.clustername-creds \
  --from-literal=Values.kafka.username='somepassword' \
  --namespace=Values.kafka.namespace
git clone https://github.com/ismoilovfk/k8s-kafka-cluster.git
cd k8s-kafka-cluster
helm install my-kafka-cluster .
```

