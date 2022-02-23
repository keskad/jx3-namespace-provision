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
