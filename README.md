# onap

### k8s deployment:

Install cert-manager:
```bash
helm repo add jetstack https://charts.jetstack.io
helm repo update

helm install cert-manager jetstack/cert-manager \
  --create-namespace \
  --namespace cert-manager \
  --set installCRDs=true
```

clone oom repo for k8s deployment:
```bash
git clone -b istanbul https://gerrit.onap.org/r/oom --depth 1
cd oom/kubernetes
```

