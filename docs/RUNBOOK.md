# Runbook

## Service

- Name: `claims-api`
- Team: `Payments`
- Owner: `mooref068@gmail.com`
- Cost center: `payments`

## First Checks

```bash
kubectl get rollout claims-api -n claims-api-dev
kubectl get pods -l app.kubernetes.io/name=claims-api -n claims-api-dev
kubectl logs -l app.kubernetes.io/name=claims-api -n claims-api-dev
```

## Health

```bash
curl https://claims-api.dev.platform.ohanyere.internal/healthz
curl https://claims-api.dev.platform.ohanyere.internal/readyz
curl https://claims-api.dev.platform.ohanyere.internal/livez
```

## Rollback

```bash
kubectl argo rollouts undo claims-api -n claims-api-dev
```

Escalate to `Payments` through `mooref068@gmail.com` if rollback does not restore service.
