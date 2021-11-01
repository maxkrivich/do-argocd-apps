apiVersion: argoproj.io/v1alpha1
kind: Application
metadata:
  name: my-apps
spec:
  destination:
    name: ''
    namespace: default
    server: 'https://kubernetes.default.svc'
  source:
    path: apps/
    repoURL: 'https://github.com/maxkrivich/do-argocd-apps.git'
    targetRevision: HEAD
  project: default
  syncPolicy:
    automated:
      prune: true
      selfHeal: true
