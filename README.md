# ui-samples

```bash
# generate kustomization.yaml for the handwritten samples
# cd ~/go/src/kmodules.xyz/kustomizer
# go run gen/main.go ~/go/src/github.com/appscode/ui-samples/.kustomizer/mongodb

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


# go run gen/main.go ~/go/src/github.com/appscode/ui-samples/.kustomizer/postgres
# go run gen/main.go ~/go/src/github.com/appscode/ui-samples/.kustomizer/mariadb
# go run gen/main.go ~/go/src/github.com/appscode/ui-samples/.kustomizer/elasticsearch
# go run gen/main.go ~/go/src/github.com/appscode/ui-samples/.kustomizer/mysql
# go run gen/main.go ~/go/src/github.com/appscode/ui-samples/.kustomizer/redis
# go run gen/main.go ~/go/src/github.com/appscode/ui-samples/.kustomizer/redissentinel
# go run gen/main.go ~/go/src/github.com/appscode/ui-samples/.kustomizer/kubevault/vaultserver

# generate kustomize bases from handwritten sample yamls
kustomizer ~/go/src/github.com/appscode/ui-samples/.kustomizer/mongodb ~/go/src/github.com/appscode/ui-samples/.kustomize/mongodb

kustomizer ~/go/src/github.com/appscode/ui-samples/.kustomizer/postgres ~/go/src/github.com/appscode/ui-samples/.kustomize/postgres

kustomizer ~/go/src/github.com/appscode/ui-samples/.kustomizer/mariadb ~/go/src/github.com/appscode/ui-samples/.kustomize/mariadb

kustomizer ~/go/src/github.com/appscode/ui-samples/.kustomizer/elasticsearch ~/go/src/github.com/appscode/ui-samples/.kustomize/elasticsearch

kustomizer ~/go/src/github.com/appscode/ui-samples/.kustomizer/mysql ~/go/src/github.com/appscode/ui-samples/.kustomize/mysql

kustomizer ~/go/src/github.com/appscode/ui-samples/.kustomizer/redis ~/go/src/github.com/appscode/ui-samples/.kustomize/redis

kustomizer ~/go/src/github.com/appscode/ui-samples/.kustomizer/redissentinel ~/go/src/github.com/appscode/ui-samples/.kustomize/redissentinel

kustomizer ~/go/src/github.com/appscode/ui-samples/.kustomizer/kubevault/vaultserver ~/go/src/github.com/appscode/ui-samples/.kustomize/kubevault/vaultserver

# build final sample yamls
cd ~/go/src/kmodules.xyz/kustomizer
go run build/main.go ~/go/src/github.com/appscode/ui-samples/.kustomize/mongodb ~/go/src/github.com/appscode/ui-samples/mongodb

go run build/main.go ~/go/src/github.com/appscode/ui-samples/.kustomize/postgres ~/go/src/github.com/appscode/ui-samples/postgres

go run build/main.go ~/go/src/github.com/appscode/ui-samples/.kustomize/mariadb ~/go/src/github.com/appscode/ui-samples/mariadb

go run build/main.go ~/go/src/github.com/appscode/ui-samples/.kustomize/elasticsearch ~/go/src/github.com/appscode/ui-samples/elasticsearch

go run build/main.go ~/go/src/github.com/appscode/ui-samples/.kustomize/mysql ~/go/src/github.com/appscode/ui-samples/mysql

go run build/main.go ~/go/src/github.com/appscode/ui-samples/.kustomize/redis ~/go/src/github.com/appscode/ui-samples/redis

go run build/main.go ~/go/src/github.com/appscode/ui-samples/.kustomize/redissentinel ~/go/src/github.com/appscode/ui-samples/redissentinel

go run build/main.go ~/go/src/github.com/appscode/ui-samples/.kustomize/kubevault/vaultserver ~/go/src/github.com/appscode/ui-samples/kubevault/vaultserver

# determine the most complex configuration
go run stats/main.go ~/go/src/github.com/appscode/ui-samples/mongodb

go run stats/main.go ~/go/src/github.com/appscode/ui-samples/mariadb

go run stats/main.go ~/go/src/github.com/appscode/ui-samples/postgres

go run stats/main.go ~/go/src/github.com/appscode/ui-samples/elasticsearch

go run stats/main.go ~/go/src/github.com/appscode/ui-samples/mysql

go run stats/main.go ~/go/src/github.com/appscode/ui-samples/redis

go run stats/main.go ~/go/src/github.com/appscode/ui-samples/redissentinel
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
topology/prometheus.io/backupconfiguration/stash/cert-manager/custom-auth/custom-config/internal-users/kernel-settings                7|15
topology/prometheus.io/backupconfiguration/stash/cert-manager/custom-auth/custom-config/internal-users/base                           7|15
combined/prometheus.io/backupconfiguration/stash/cert-manager/custom-auth/custom-config/internal-users/kernel-settings                7|15
combined/prometheus.io/backupconfiguration/stash/cert-manager/custom-auth/custom-config/internal-users/base                           7|15
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

### Redis

```
sentinel/prometheus.io/backupconfiguration/stash/tls/custom-auth/custom-config            8|10
sentinel/prometheus.io/backupconfiguration/stash/tls/custom-config                        8|9
sentinel/prometheus.io/backupconfiguration/stash/tls/custom-auth/base                     8|9
sentinel/prometheus.io/backupblueprint/stash/tls/custom-auth/custom-config                8|9
sentinel/prometheus.io/backupblueprint/stash/tls/custom-config                            8|8
sentinel/prometheus.io/backupblueprint/stash/tls/custom-auth/base                         8|8
standalone/prometheus.io/backupconfiguration/stash/tls/custom-auth/custom-config          7|9
sentinel/prometheus.io_operator/backupconfiguration/stash/tls/custom-auth/custom-config   7|9
sentinel/prometheus.io_builtin/backupconfiguration/stash/tls/custom-auth/custom-config    7|9
sentinel/prometheus.io/backupconfiguration/stash/custom-auth/custom-config                7|9
sentinel/backupconfiguration/stash/tls/custom-auth/custom-config                          7|9
cluster/prometheus.io/backupconfiguration/stash/tls/custom-auth/custom-config             7|9
```

### Redis Sentinel

```
prometheus.io/tls/custom-auth          4|4
tls/custom-auth                        3|3
prometheus.io_operator/tls/custom-auth 3|3
prometheus.io_builtin/tls/custom-auth  3|3
prometheus.io/tls/base                 3|3
prometheus.io/custom-auth              3|3
```
