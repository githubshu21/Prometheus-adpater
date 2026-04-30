root@master01:~/kube-prometheus# kubectl get hpa -n monitoring
NAME             REFERENCE               TARGETS   MINPODS   MAXPODS   REPLICAS   AGE
sample-app-hpa   Deployment/sample-app   0/5       2         10        2          19m

root@master01:~/kube-prometheus# kubectl get --raw "/apis/custom.metrics.k8s.io/v1beta1/namespaces/monitoring/pods/*/http_requests_per_second" | jq .

#编写while循环访问对于的网站，实时查看pod变化
root@master01:~/kube-prometheus# kubectl get pod -n monitoring -w
NAME                                 READY   STATUS    RESTARTS   AGE
prometheus-6977c89cdf-lvttk          1/1     Running   0          165m
prometheus-adapter-7ddff4778-b27v9   1/1     Running   0          19m
sample-app-6f68c6f5b4-sfgmt          1/1     Running   0          165m
sample-app-6f68c6f5b4-vtf98          1/1     Running   0          11m
