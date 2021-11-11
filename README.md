# onap

### k8s deployment:

clone oom repo for k8s deployment:
```bash
git clone -b istanbul https://gerrit.onap.org/r/oom --recurse-submodules --depth 1
cd oom/kubernetes
```

install helm plugins for macOS:
```bash
cp -R oom/kubernetes/helm/plugins/ ~/Library/helm/plugins
helm plugin install https://github.com/chartmuseum/helm-push.git --version 0.9.0
```

Install chartmuseum:
```bash
curl -LO https://s3.amazonaws.com/chartmuseum/release/latest/bin/linux/amd64/chartmuseum
chmod +x ./chartmuseum
mv ./chartmuseum /usr/local/bin
```

Install cert-manager:
```bash
helm repo add jetstack https://charts.jetstack.io
helm repo update

helm install cert-manager jetstack/cert-manager \
  --create-namespace \
  --namespace cert-manager \
  --set installCRDs=true
```

Source: https://docs.onap.org/projects/onap-oom/en/latest/oom_quickstart_guide.html

