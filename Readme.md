kubectl patch svc argocd-server -n argocd -p '{"spec":{"type": "NodePort"} }'

kubectl port-forward svc/argocd-server -n argocd 8080:443

kubectl get secret -n argocd argocd-initial-admin-secret -o jsonpath="{.data.password }" | base64 -d && echo