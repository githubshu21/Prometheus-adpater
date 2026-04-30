root@master01:~/kube-prometheus# kubectl get hpa -n monitoring
NAME             REFERENCE               TARGETS   MINPODS   MAXPODS   REPLICAS   AGE
sample-app-hpa   Deployment/sample-app   0/5       2         10        2          19m

root@master01:~/kube-prometheus# kubectl get --raw "/apis/custom.metrics.k8s.io/v1beta1/namespaces/monitoring/pods/*/http_requests_per_second" | jq .
