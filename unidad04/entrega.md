Deploy:

Part1:
```sh
kubectl
```

Part2 & 3:
```sh
kubectl
```

Part4:
```sh
kubectl
```

Troubleshooting job:
```sh
kubectl create job k8s4arch-hotels-job-manual --from=cronjob/k8s4arch-hotels-cronjob -n k8s4arch-hotels
---
kubectl get pods -n k8s4arch-hotels 
---
NAME                                 READY   STATUS              RESTARTS   AGE
hotels-deployment-67fd755bf4-l7dcn   0/1     Running             0          2m17s
hotels-deployment-67fd755bf4-ws4r4   0/1     Running             0          2m17s
k8s4arch-hotels-job-manual-6rzwb     1/1     Running   0          8s
```
> after few seconds, the status will be "completed"

```bash
k8s4arch-hotels-job-manual-6rzwb     0/1     Completed   0          30s
```