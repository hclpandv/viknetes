## Bash cli to build and test small k3d based kubernetes cluster

`viknetes` is a lightweight, pure Bash CLI for quickly creating, testing, and tearing down a small k3d-based Kubernetes cluster.
It is designed for ephemeral labs, quick experiments, and learning—no background services, no APIs, no state.

Typical usecase is to install on google cloud shell  https://console.cloud.google.com/
(Azure Cloud Shell runs in a locked-down container environment hence can not use viknetes)

Tested in Github Codespace and it worked like a charm ✅ 


#### How to setup 

1. Download the Cli and execute

```bash
curl -sSL https://raw.githubusercontent.com/hclpandv/viknetes/main/viknetes -o viknetes
chmod +x viknetes
./viknetes up
```

2. click on web preview in cloud shell  

   <img width="1501" height="228" alt="Image" src="https://github.com/user-attachments/assets/b0face5c-0ace-4fb6-bfe9-3193c028e12b" />  

4. Copy token for login to HeadLamp UI

```bash
kubectl exec -n viknetes-system deploy/headlamp -- cat /var/run/secrets/kubernetes.io/serviceaccount/token
```

4. Deploying applications (recommended model)

Developers deploy applications only via Headlamp UI Each app typically consists of:

* Namespace
* Deployment
* Service (ClusterIP)  

(Ingress is intentionally not used in Cloud Shell due to complexities)

5. Now port forward the services to expose via google cloud shell web preview

```bash
kubectl -n echo port-forward svc/echo 8081:80
kubectl -n app1 port-forward svc/app1 8082:80
# or
kubectl -n viki-web-terminal port-forward  svc/viki-web-terminal 7681:7681
```
