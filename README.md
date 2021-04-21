# helm-kustomize

**Register a new plugin in `argocd-cm` ConfigMap.**

```yaml
data:
  configManagementPlugins: |
    - name: helm+kustomize
        init:
          command: ["/bin/sh", "-c"]
          args: ["helm template ../../base -f ./values.yaml > app.yaml"]
        generate:                      
          command: ["/bin/sh", "-c"]
          args: ["kustomize build"]
```