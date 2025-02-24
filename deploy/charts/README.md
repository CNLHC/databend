## Run in Kubernetes using Helm
### Dependencies

1. Clone:

```text
git clone https://github.com/datafuselabs/databend.git
```

2. Make sure you have [Kubernetes](https://kubernetes.io/) cluster running

### Build Image

`make docker` to build image `datafuselabs/databend-query`

###  Run Helm 

`make run-helm` in project root directory,

when successful install you will get a note like this,

```
NOTES:
1. connect to databend-query mysql port:
export MYSQL_PORT=$(kubectl get --namespace default -o jsonpath="{.spec.ports[0].nodePort}" services databend)
mysql -h127.0.0.1 -P$DATABEND_MYSQL_PORT

export HTTP_PORT=$(kubectl get --namespace default -o jsonpath="{.spec.ports[2].nodePort}" services databend)
curl http://127.0.0.1:$DATABEND_HTTP_PORT/v1/configs
```

More to see [building-and-running.md](../../docs/overview/building-and-running.md)
