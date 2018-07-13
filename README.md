Stolen from [stateful app tutorial](https://github.com/kubernetes/kubernetes.github.io/tree/master/docs/tutorials/stateful-application)

# What?

I need a cluster of (generally 3) redis instances with sentinel failover.  Masters must persist across restarts, which means that redis needs to be able to write to its config file and the config needs to remain stable.

# How?

```
oc apply -f redis-configmap.yaml 
oc apply -f redis-sentinel-configmap.yaml
oc apply -f redis-services.yaml
oc apply -f redis-statefulset.yaml
oc apply -f redis-sentinel-statefulset.yaml
```

