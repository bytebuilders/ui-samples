# kubedb-samples

```bash
# generate kustomization.yaml for the handwritten samples
# cd ~/go/src/kmodules.xyz/kustomizer
# go run gen/main.go ~/go/src/github.com/appscode/kubedb-samples/.kustomizer/mongodb

## .kustomizer/mongodb/custom-config/sharded/kustomization.yaml
apiVersion: kustomize.config.k8s.io/v1beta1
bases:
- ../../modes/sharded
kind: Kustomization
resources:
- mongodb-config-secret.yaml
- mongodb-configserver-config-secret.yaml
- mongodb-mongos-config-secret.yaml
- mongodb-shard-config-secret.yaml
- mongodb.yaml


# go run gen/main.go ~/go/src/github.com/appscode/kubedb-samples/.kustomizer/postgres
# go run gen/main.go ~/go/src/github.com/appscode/kubedb-samples/.kustomizer/mariadb
# go run gen/main.go ~/go/src/github.com/appscode/kubedb-samples/.kustomizer/elasticsearch
# go run gen/main.go ~/go/src/github.com/appscode/kubedb-samples/.kustomizer/mysql

# generate kustomize bases from handwritten sample yamls
kustomizer ~/go/src/github.com/appscode/kubedb-samples/.kustomizer/mongodb ~/go/src/github.com/appscode/kubedb-samples/.kustomize/mongodb

kustomizer ~/go/src/github.com/appscode/kubedb-samples/.kustomizer/postgres ~/go/src/github.com/appscode/kubedb-samples/.kustomize/postgres

kustomizer ~/go/src/github.com/appscode/kubedb-samples/.kustomizer/mariadb ~/go/src/github.com/appscode/kubedb-samples/.kustomize/mariadb

kustomizer ~/go/src/github.com/appscode/kubedb-samples/.kustomizer/elasticsearch ~/go/src/github.com/appscode/kubedb-samples/.kustomize/elasticsearch

kustomizer ~/go/src/github.com/appscode/kubedb-samples/.kustomizer/mysql ~/go/src/github.com/appscode/kubedb-samples/.kustomize/mysql

# build final sample yamls
cd ~/go/src/kmodules.xyz/kustomizer
go run build/main.go ~/go/src/github.com/appscode/kubedb-samples/.kustomize/mongodb ~/go/src/github.com/appscode/kubedb-samples/mongodb

go run build/main.go ~/go/src/github.com/appscode/kubedb-samples/.kustomize/postgres ~/go/src/github.com/appscode/kubedb-samples/postgres

go run build/main.go ~/go/src/github.com/appscode/kubedb-samples/.kustomize/mariadb ~/go/src/github.com/appscode/kubedb-samples/mariadb

go run build/main.go ~/go/src/github.com/appscode/kubedb-samples/.kustomize/elasticsearch ~/go/src/github.com/appscode/kubedb-samples/elasticsearch

go run build/main.go ~/go/src/github.com/appscode/kubedb-samples/.kustomize/mysql ~/go/src/github.com/appscode/kubedb-samples/mysql

# determine the most complex configuration
go run stats/main.go ~/go/src/github.com/appscode/kubedb-samples/mongodb

go run stats/main.go ~/go/src/github.com/appscode/kubedb-samples/mariadb

go run stats/main.go ~/go/src/github.com/appscode/kubedb-samples/postgres

go run stats/main.go ~/go/src/github.com/appscode/kubedb-samples/elasticsearch

go run stats/main.go ~/go/src/github.com/appscode/kubedb-samples/mysql
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
cluster/prometheus.io/backupconfiguration/stash/tls/custom-auth/config-file/base                                9
cluster/prometheus.io/backupconfiguration/stash/tls/custom-auth/config-file/customize-pod-template              9
standalone/prometheus.io/backupconfiguration/stash/tls/custom-auth/config-file/base                             9
standalone/prometheus.io/backupconfiguration/stash/tls/custom-auth/config-file/customize-pod-template           9
```

### Postgres

```
cluster/prometheus.io/backupconfiguration/stash/tls/custom-auth/custom-auth-mode/custom-config/base                                         9
cluster/prometheus.io/backupconfiguration/stash/tls/custom-auth/custom-auth-mode/custom-config/custom-pg-coordinator/base                   9
cluster/prometheus.io/backupconfiguration/stash/tls/custom-auth/custom-auth-mode/custom-config/custom-pg-coordinator/custom-uid             9
cluster/prometheus.io/backupconfiguration/stash/tls/custom-auth/custom-auth-mode/custom-config/custom-uid                                   9
```

### Elasticsearch

```
combined/backupconfiguration/stash/cert-manager/custom-auth/custom-config/internal-users/base                                         14
combined/backupconfiguration/stash/cert-manager/custom-auth/custom-config/internal-users/kernel-settings                              14
combined/prometheus.io/backupconfiguration/stash/cert-manager/custom-auth/custom-config/internal-users/base                           14
combined/prometheus.io/backupconfiguration/stash/cert-manager/custom-auth/custom-config/internal-users/kernel-settings                14
combined/prometheus.io_builtin/backupconfiguration/stash/cert-manager/custom-auth/custom-config/internal-users/base                   14
combined/prometheus.io_builtin/backupconfiguration/stash/cert-manager/custom-auth/custom-config/internal-users/kernel-settings        14
```

### MySQL

```
group-replication/prometheus.io/backupconfiguration/stash/tls/custom-auth/config-file/base                             9
group-replication/prometheus.io/backupconfiguration/stash/tls/custom-auth/config-file/customize-pod-template           9
innodb-cluster/prometheus.io/backupconfiguration/stash/tls/custom-auth/config-file/base                                9
innodb-cluster/prometheus.io/backupconfiguration/stash/tls/custom-auth/config-file/customize-pod-template              9
standalone/prometheus.io/backupconfiguration/stash/tls/custom-auth/config-file/base                                    9
standalone/prometheus.io/backupconfiguration/stash/tls/custom-auth/config-file/customize-pod-template                  9
```
