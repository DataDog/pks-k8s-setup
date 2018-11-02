# pks-k8s-setup

## Steps

(optional): Modify `docker-compose.yaml` then `kompose convert -f docker-compose.yaml --out k8s-kompose.yaml`

1. Replace `<API_KEY>` in `datadog-agent.yaml` with a real key
1. `kubectl create -f k8s-kompose.yaml`
1. `kubectl create -f datadog-serviceaccount.yaml`
1. `kubectl create -f datadog-agent.yaml`
1. `kubectl get deployment,svc,pods,pvc,daemonsets`

## Notes

You may not need this in `datadog-agent.yaml`:

```
- name: DD_KUBELET_TLS_VERIFY
  value: "false"
```
