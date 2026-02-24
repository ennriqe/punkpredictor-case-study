# Operations and Release Workflow (Sanitized)

## Scheduled Runtime Loop

### 1) Inference / nowcast cycle (every 30 minutes)
- refresh market and sales inputs
- rebuild snapshot tables
- generate current predictions
- publish via current-pointer swap
- persist compatibility/performance outputs for serving
- archive snapshots/artifacts to S3

### 2) Retrain policy check (daily)
- evaluate drift/performance conditions
- enqueue a training request when policy thresholds are met

### 3) Training worker (hourly)
- claim queued request
- run training job (ephemeral compute may be used)
- register contender artifacts/metadata
- run contender evaluation gates
- submit promotion decision event

### 4) Post-promotion monitor (hourly)
- compare promoted model behavior against thresholds
- execute pointer rollback if degradation exceeds policy limits

## Deployment Automation

The private monorepo uses GitHub Actions to deploy:
- VPS inference/runtime assets (model + infra paths)
- backend API updates (server paths)

Operational patterns emphasized:
- deterministic deploys
- dirty-checkout detection and archival before reset on VPS
- explicit service/timer verification after deploy
- secrets managed through CI provider secrets, not code

## Why This Matters

This setup makes the system resilient to the most common ML production failures:
- stale predictions due to broken schedulers
- silent regressions from retrains
- irreproducible model artifacts
- partial deployments leaving services in inconsistent states
