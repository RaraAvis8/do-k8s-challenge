# do-k8s-challenge
https://www.digitalocean.com/community/pages/kubernetes-challenge

# How to setup

## Setup k8s cluster
```bash
doctl kubernetes cluster kubeconfig save <config-id>
kubectl cluster-info
```

## Create Elasticsearch
```bash
kubectl create -f kube-logging.yaml
kubectl create -f elasticsearch_svc.yaml
kubectl create -f elasticsearch_statefulset.yaml
```

# Test
```bash
kubectl port-forward es-cluster-0 9200:9200 --namespace=kube-logging
```

in another tab:
```bash
curl http://localhost:9200/_cluster/state?pretty
```
