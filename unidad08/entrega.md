Deploy:

```sh
kubectl -f 00_ejercicio.yml
```

List pv & pods:
```sh
kubectl get pv,pods -n k8s4arch-hotels
---
NAME                                                        CAPACITY   ACCESS MODES   RECLAIM POLICY   STATUS   CLAIM                                 STORAGECLASS      REASON   AGE
persistentvolume/pvc-593259b8-aae9-4c05-aba9-66449d8d10e0   1Gi        ROX            Retain           Bound    k8s4arch-hotels/k8s4arch-hotels-pvc   ceph-rbd-retain            7m48s

NAME                                            READY   STATUS    RESTARTS   AGE
pod/k8s4arch-hotels-backend-b65c8dd97-pdhx9     1/1     Running   0          8m2s
pod/k8s4arch-hotels-backend-b65c8dd97-x9dmt     1/1     Running   0          8m2s
pod/k8s4arch-hotels-frontend-78b9d995cf-cm4hq   1/1     Running   0          8m3s
pod/k8s4arch-hotels-frontend-78b9d995cf-qp988   1/1     Running   0          8m3s
```

Check backend pods are attaching the volumen success:
```
kubectl describe pod -n k8s4arch-hotels k8s4arch-hotels-backend-b65c8dd97-pdhx9 | grep "SuccessfulAttachVolume"
----
Normal   SuccessfulAttachVolume  10m    attachdetach-controller  AttachVolume.Attach succeeded for volume "pvc-593259b8-aae9-4c05-aba9-66449d8d10e0"
```