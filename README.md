root@master01:~/kube-prometheus# kubectl get hpa -n monitoring
NAME             REFERENCE               TARGETS   MINPODS   MAXPODS   REPLICAS   AGE
sample-app-hpa   Deployment/sample-app   0/5       2         10        2          19m

root@master01:~/kube-prometheus# kubectl get --raw "/apis/custom.metrics.k8s.io/v1beta1/namespaces/monitoring/pods/*/http_requests_per_second" | jq .
{
  "kind": "MetricValueList",
  "apiVersion": "custom.metrics.k8s.io/v1beta1",
  "metadata": {},
  "items": [
    {
      "describedObject": {
        "kind": "Pod",
        "namespace": "monitoring",
        "name": "sample-app-6f68c6f5b4-sfgmt",
        "apiVersion": "/v1"
      },
      "metricName": "http_requests_per_second",
      "timestamp": "2026-04-30T13:10:45Z",
      "value": "0",
      "selector": null
    },
    {
      "describedObject": {
        "kind": "Pod",
        "namespace": "monitoring",
        "name": "sample-app-6f68c6f5b4-vtf98",
        "apiVersion": "/v1"
      },
      "metricName": "http_requests_per_second",
      "timestamp": "2026-04-30T13:10:45Z",
      "value": "0",
      "selector": null
    }
  ]
}
