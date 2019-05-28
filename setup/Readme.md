First create the namespace:

```
$ kubectl create -f namespace.yaml
```

Or recreate the namespace:
```
$ kubectl apply -f namespace.yaml
```

To create the ServiceAccount:

```shell
$ kubectl create -f traefik-service-acc.yaml 
serviceaccount "traefik-ingress" created
```

Create a ClusterRole with a set of permissions which will be applied to the Traefik ServiceAccount. The ClusterRole will allow Traefik to manage and watch such resources as Services, Endpoints, Secrets, and Ingresses across all namespaces in the cluster:

```shell
$ kubectl create -f traefik-cr.yaml
clusterrole.rbac.authorization.k8s.io "traefik-ingress" created
```
To enable these permissions, we should bind the ClusterRole to the Traefik ServiceAccount. This can be done using the ClusterRoleBinding manifest:

https://supergiant.io/blog/using-traefik-as-ingress-controller-for-your-kubernetes-cluster/
