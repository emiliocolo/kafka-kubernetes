# kafka-kubernetes

Experiment on Kafka Strimzi Operator and Kubernetes Monitoring

# Send
kubectl -n kafka run kafka-producer -ti --image=quay.io/strimzi/kafka:0.25.0-kafka-2.8.0 --rm=true --restart=Never -- bin/kafka-console-producer.sh --broker-list my-cluster-kafka-bootstrap:9092 --topic my-topic
# Receive
kubectl -n kafka run kafka-consumer -ti --image=quay.io/strimzi/kafka:0.25.0-kafka-2.8.0 --rm=true --restart=Never -- bin/kafka-console-consumer.sh --bootstrap-server my-cluster-kafka-bootstrap:9092 --topic my-topic --from-beginning

## Monitoring
# Prometheus Operator
https://github.com/prometheus-operator/prometheus-operator
https://github.com/prometheus-community/helm-charts/tree/main/charts/kube-prometheus-stack
https://github.com/prometheus-community/helm-charts/blob/main/charts/kube-prometheus-stack/values.yaml

# Grafana
https://strimzi.io/docs/operators/latest/deploying.html#proc-metrics-grafana-dashboard-str

# Grafana Dashboards
https://grafana.com/grafana/dashboards/10000
https://github.com/pivotal-cf/charts-grafana
# Disk
https://grafana.com/grafana/dashboards/13646
https://grafana.com/grafana/dashboards/12740

# Performance Test
https://medium.com/metrosystemsro/apache-kafka-how-to-test-performance-for-clients-configured-with-ssl-encryption-3356d3a0d52b
