# Runbook — High HTTP 500 Error Count

## Trigger
More than 2 HTTP 500 errors detected within 5 minutes.

## Initial checks
1. Check the Grafana alert status.
2. Check the HTTP 500 error panel.
3. Check FastAPI/Uvicorn logs.
4. Identify which endpoint is failing.
5. Check recent code or configuration changes.

## Investigation
- Use logs to identify the error message.
- Use Prometheus metrics to confirm the error volume.
- Use Grafana Tempo traces to identify where the request failed or slowed down.

## Recovery
- Restart the affected service if appropriate.
- Roll back recent changes if they caused the issue.
- Escalate to a more experienced engineer if the cause is unclear.

## Verification
- Confirm HTTP 500 errors have stopped.
- Confirm the alert returned to Normal.
- Confirm `/health` responds with HTTP 200.
