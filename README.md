## Bash cli to build and test small k3d based kubernetes cluster

`viknetes` is a lightweight, pure Bash CLI for quickly creating, testing, and tearing down a small k3d-based Kubernetes cluster.
It is designed for ephemeral labs, quick experiments, and learning—no background services, no APIs, no state.

#### How to setup 

1. Download the Cli and execute

```bash
curl https://raw.githubusercontent.com/hclpandv/viknetes/refs/heads/main/viknetes -o viknetes
chmod u+x
./viknetes up 
```
