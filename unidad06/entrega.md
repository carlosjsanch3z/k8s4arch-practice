Create from manifest:
```sh
kubectl apply -f 00_multi_containers.yml
```

After 2-3 minutes, check with the following command:

```sh
kubectl get pods -n k8s4arch-hotels

NAME                                 READY   STATUS    RESTARTS   AGE
hotels-deployment-6cbb65995c-2xkdq   2/2     Running   0          5m10s
hotels-deployment-6cbb65995c-hvhhm   2/2     Running   0          5m8s

kubectl exec -it -n k8s4arch-hotels pod/hotels-deployment-6cbb65995c-2xkdq -c k8s4arch-hotels-frontend -- curl http://localhost:5000/hotels
---
....
PGigB0m01RiXYUVpRVUbI1aZGUwR2J7iCARpPC7ST/AOQUAeKyBI/EEEthsQ0kRZOH4kgaMkkCauLW/pb4j+qAPEDUXhoAJmBAuhqqBVG6sD5qk1wtyTTGoyFgqjkmdfdUmyJ4ISOfmiZ2ymnlHeE0dT5AdUKL5vXLU4hu+iaSDeCb7a4r8GVnGT8pVaSeFeKFcTT3Q449ZCPap2xTohJO/wBTPRYBH/JV311mSUwnd8hOLXCsG+9GJJJvUm52bhS+aIQQpITgB/t9CnA8x6pouKg3ruVAL519Am1GaaJTYMC0JtDFU08fhQ7o3zQ+ck6TkASUSfTdmmn5xX6nIwN1fbumwFdEY1v84q5sRbzUninQE+eHrKujRGisFcef8LPXIGcU52UCLmQelY3k8lpPEdgEc4vulflpBQHHKBCMSJ3J3REdfRN6hMOqwcO6efC4TlUHbOBXIfwmkDaf4QxwgDYrCMZxQg8VEba+YzRJ8k4ztqv02yt76mmqEmOh+wwDq+fPkr58/jJfPnUL5/FxsRgozHrC+VW/kfZWnU0kHIYpn55cfRaKBSJvjPkhJwHz4VVx+UQpEfYIUZdPZCKhOx3LRjxG5IkzvurfOKio7fysh3RNTJ4XThvJVT07HmU+Oo6SFc5d0ECItvXwH0X/2Q==","price":1,"rooms":4,"slug":"campo-tinto"}]
```

> Hit backend from frontend container.