Deploy:

Part1:
```sh
kubectl -f 00_part1.yml
```

Part2:
```sh
kubectl -f 00_part2.yml
```


Troubleshooting top metrics:
```sh
kubectl top pods -n k8s4arch-hotels
---
NAME                                 CPU(cores)   MEMORY(bytes)   
hotels-deployment-564c54bc7c-rvq67   1m           21Mi            
hotels-deployment-564c54bc7c-snzfc   1m           20Mi   
```
> metrics example used by default"