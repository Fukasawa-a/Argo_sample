# Application Settings 
```yaml
apiVersion: argoproj.io/v1alpha1
kind: Application
metadata:
  name: colorpage
  namespace: argocd
spec:
  destination:
    namespace: default
    server: https://kubernetes.default.svc
  project: default
  source:
    path: guestbook2
    repoURL: https://github.com/tac-ichiro/Argo_sample.git
    targetRevision: HEAD
```


```console
kubectl port-forward svc/guestbook-ui 8081:8080 --address 0.0.0.0
````

access to http://YOUR.HOST.NAME:8081/


# Test Sync 

change image name  in `guestbook-ui-deployment.yaml`
```
- image: argoproj/rollouts-demo:blue 
- image: argoproj/rollouts-demo:green 
- image: argoproj/rollouts-demo:red
- image: argoproj/rollouts-demo:yellow
```
