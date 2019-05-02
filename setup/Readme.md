To create the ServiceAccount:

```shell
$ kubectl create -f traefik-service-acc.yaml 
serviceaccount "traefik-ingress" created
```

Create the cluster role for Traefik:

```shell
$ kubectl create -f traefik-cr.yaml
clusterrole.rbac.authorization.k8s.io "traefik-ingress" created
```
