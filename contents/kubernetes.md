# Kubernetes

### Creating a service

```
$ kubectl create namespace ${namespace_name}
$ kubectl create -f ${kubernetes_config}.yaml
$ kubectl get pods --namespace ${namespace_name}
```

### Services

Showing state and port mappings of a service

```
$ kubectl get service --namespace jenkins
```

Deleting a StatefulSet

```
$ kubectl delete sts ${image_name} --namespace=${namespace_name}
```

SSHing to a container

```
$ kubectl --namespace=${namespace_name} exec -it ${instance_name} -- /bin/bash
