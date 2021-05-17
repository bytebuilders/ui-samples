# kubedb-samples

```bash
# generate kustomization.yaml for the handwritten samples
# cd ~/go/src/kmodules.xyz/kustomizer
# go run gen/main.go ~/go/src/github.com/appscode/kubedb-samples/.kustomizer/mongodb

# generate kustomize bases from handwritten sample yamls
kustomizer ~/go/src/github.com/appscode/kubedb-samples/.kustomizer/mongodb ~/go/src/github.com/appscode/kubedb-samples/.kustomize/mongodb

# build final sample yamls
cd ~/go/src/kmodules.xyz/kustomizer
go run build/main.go ~/go/src/github.com/appscode/kubedb-samples/.kustomize/mongodb ~/go/src/github.com/appscode/kubedb-samples/mongodb

# determine the most complex configuration
go run stats/main.go ~/go/src/github.com/appscode/kubedb-samples/mongodb
```

## Complex Configurations

### MongoDB

```
sharded/prometheus.io/backupconfiguration/stash/tls/custom-auth/sharded                 12
sharded/backupconfiguration/stash/tls/custom-auth/sharded                               11
sharded/prometheus.io/backupblueprint/stash/tls/custom-auth/sharded                     11
```
