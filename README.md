# jx3-namespace-provision
Creates all required resources to run Jenkins X jobs in a namespace

Running
-------

```bash
helm install jx-test1 ./jx3-namespace-provision --create-namespace -n jx-test1 --values ./values.yaml
```

values.yaml
-----------

```yaml
# namespace admin can perform deployments in SAME NAMESPACE
# while if .isNamespaceAdmin is set to false, then only necessary permissions for pipeline completion (without CD part) are granted
isNamespaceAdmin: false

secrets:
    registryDockerConfigJson: |
        {
            "auths":{
                "ghcr.io": {
                    "auth": "tralalalala"
                }
            }
        }
    gitUsername: "user"
    gitPassword: "password"
    gitProviderUrl: https://github.com

# you may take a look at your jx3 installation repository to pick same values
environment:
    installRepo:
        branch: master
        url: https://github.com/keskad/jx3-local-testing-cluster.git
    settings:
        gitServer: https://github.com
        kubeProvider: kubernetes
        pipelineUserEmail: jenkins-x@googlegroups.com
        pipelineUsername: keskad
```
