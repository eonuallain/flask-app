# flask-app

## Kind - install (linux)

https://kind.sigs.k8s.io/docs/user/quick-start/
```
[ $(uname -m) = x86_64 ] && curl -Lo ./kind https://kind.sigs.k8s.io/dl/v0.27.0/kind-linux-amd64
```

## Kind - install (mac)

```
brew install kind
```

## Kind - create cluster

```
cat <<EOF | kind create cluster --config=-
kind: Cluster
apiVersion: kind.x-k8s.io/v1alpha4
nodes:
- role: control-plane
  extraPortMappings:
  - containerPort: 80
    hostPort: 80
    protocol: TCP
  - containerPort: 443
    hostPort: 443
    protocol: TCP
EOF
```

## Ingress install with for kind

```
https://kind.sigs.k8s.io/docs/user/ingress/

kubectl apply -f https://kind.sigs.k8s.io/examples/ingress/deploy-ingress-nginx.yaml
```
