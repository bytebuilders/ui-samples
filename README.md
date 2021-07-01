# kubedb-samples

```bash
# generate kustomization.yaml for the handwritten samples
# cd ~/go/src/kmodules.xyz/kustomizer
# go run gen/main.go ~/go/src/github.com/appscode/kubedb-samples/.kustomizer/mongodb
# go run gen/main.go ~/go/src/github.com/appscode/kubedb-samples/.kustomizer/postgres
# go run gen/main.go ~/go/src/github.com/appscode/kubedb-samples/.kustomizer/mariadb

# generate kustomize bases from handwritten sample yamls
kustomizer ~/go/src/github.com/appscode/kubedb-samples/.kustomizer/mongodb ~/go/src/github.com/appscode/kubedb-samples/.kustomize/mongodb

kustomizer ~/go/src/github.com/appscode/kubedb-samples/.kustomizer/postgres ~/go/src/github.com/appscode/kubedb-samples/.kustomize/postgres

kustomizer ~/go/src/github.com/appscode/kubedb-samples/.kustomizer/mariadb ~/go/src/github.com/appscode/kubedb-samples/.kustomize/mariadb

# build final sample yamls
cd ~/go/src/kmodules.xyz/kustomizer
go run build/main.go ~/go/src/github.com/appscode/kubedb-samples/.kustomize/mongodb ~/go/src/github.com/appscode/kubedb-samples/mongodb

go run build/main.go ~/go/src/github.com/appscode/kubedb-samples/.kustomize/postgres ~/go/src/github.com/appscode/kubedb-samples/postgres

go run build/main.go ~/go/src/github.com/appscode/kubedb-samples/.kustomize/mariadb ~/go/src/github.com/appscode/kubedb-samples/mariadb

# determine the most complex configuration
go run stats/main.go ~/go/src/github.com/appscode/kubedb-samples/mongodb

go run stats/main.go ~/go/src/github.com/appscode/kubedb-samples/mariadb

go run stats/main.go ~/go/src/github.com/appscode/kubedb-samples/postgres
```

## Complex Configurations

### MongoDB

```
sharded/prometheus.io/backupconfiguration/stash/tls/custom-auth/sharded                 12
sharded/backupconfiguration/stash/tls/custom-auth/sharded                               11
sharded/prometheus.io/backupblueprint/stash/tls/custom-auth/sharded                     11
```

### MariaDB

```
cluster/prometheus.io/backupconfiguration/stash/tls/custom-auth/config-file                         9
standalone/prometheus.io/backupconfiguration/stash/tls/custom-auth/config-file                      9
cluster/backupconfiguration/stash/tls/custom-auth/config-file                                       8
cluster/prometheus.io/backupblueprint/stash/tls/custom-auth/config-file                             8
cluster/prometheus.io/backupconfiguration/script/tls/custom-auth/config-file                        8
```

### Postgres

```
cluster/prometheus.io/backupconfiguration/stash/tls/custom-auth/custom-auth-mode/custom-config/base                                         9
cluster/prometheus.io/backupconfiguration/stash/tls/custom-auth/custom-auth-mode/custom-config/custom-pg-coordinator/base                   9
cluster/prometheus.io/backupconfiguration/stash/tls/custom-auth/custom-auth-mode/custom-config/custom-pg-coordinator/custom-uid             9
cluster/prometheus.io/backupconfiguration/stash/tls/custom-auth/custom-auth-mode/custom-config/custom-uid                                   9
cluster/prometheus.io/backupconfiguration/stash/tls/custom-auth/custom-config/base                                                          9
cluster/prometheus.io/backupconfiguration/stash/tls/custom-auth/custom-config/custom-pg-coordinator/base                                    9
cluster/prometheus.io/backupconfiguration/stash/tls/custom-auth/custom-config/custom-pg-coordinator/custom-uid                              9
cluster/prometheus.io/backupconfiguration/stash/tls/custom-auth/custom-config/custom-uid                                                    9
standalone/prometheus.io/backupconfiguration/stash/tls/custom-auth/custom-auth-mode/custom-config/base                                      9
standalone/prometheus.io/backupconfiguration/stash/tls/custom-auth/custom-auth-mode/custom-config/custom-pg-coordinator/base                9
standalone/prometheus.io/backupconfiguration/stash/tls/custom-auth/custom-auth-mode/custom-config/custom-pg-coordinator/custom-uid          9
standalone/prometheus.io/backupconfiguration/stash/tls/custom-auth/custom-auth-mode/custom-config/custom-uid                                9
standalone/prometheus.io/backupconfiguration/stash/tls/custom-auth/custom-config/base                                                       9
standalone/prometheus.io/backupconfiguration/stash/tls/custom-auth/custom-config/custom-pg-coordinator/base                                 9
standalone/prometheus.io/backupconfiguration/stash/tls/custom-auth/custom-config/custom-pg-coordinator/custom-uid                           9
standalone/prometheus.io/backupconfiguration/stash/tls/custom-auth/custom-config/custom-uid                                                 9
```
