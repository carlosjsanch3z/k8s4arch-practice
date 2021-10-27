Deploy:

```sh
cd unidad03 && kubectl apply -f .
```

Check deployment, namespace & replicaset are created:
```sh
kubectl get all -n k8s4arch-hotels

---

NAME                                    READY   STATUS    RESTARTS   AGE
pod/hotels-deployment-d8d76c444-bs525   1/1     Running   0          2m30s
pod/hotels-deployment-d8d76c444-wjlcf   1/1     Running   0          2m30s

NAME                                READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/hotels-deployment   2/2     2            2           2m31s

NAME                                          DESIRED   CURRENT   READY   AGE
replicaset.apps/hotels-deployment-d8d76c444   2         2         2       2m31s
```

Check if it's running:

```sh
kubectl port-forward pod/hotels-deployment-<random_hex> 8000:80 -n k8s4arch-hotels
```

