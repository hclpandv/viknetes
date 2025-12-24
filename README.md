## Bash cli to build and test small k3d based kubernetes cluster

`viknetes` is a lightweight, pure Bash CLI for quickly creating, testing, and tearing down a small k3d-based Kubernetes cluster.
It is designed for ephemeral labs, quick experiments, and learning—no background services, no APIs, no state.

Typical usecase to install on google/azure cloud shell  https://console.cloud.google.com/
   

#### How to setup 

1. Download the Cli and execute

```bash
curl -sSL https://raw.githubusercontent.com/hclpandv/viknetes/main/viknetes -o viknetes
chmod +x viknetes
./viknetes up
```

Copy token: 

```bash
kubectl exec -n viknetes-system deploy/headlamp -- cat /var/run/secrets/kubernetes.io/serviceaccount/token
```