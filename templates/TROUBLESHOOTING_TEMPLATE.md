# Troubleshooting

## Symptoms

| Symptom | First Check | Possible Cause | Action |
| --- | --- | --- | --- |
| CORS error | Browser Network, API Gateway OPTIONS | Missing preflight response | Check OPTIONS route |
| Report stuck | Job table, worker logs | Worker timeout | Check job status and logs |
| Stale UI | CDN cache, object storage | Cache invalidation missing | Invalidate or adjust TTL |

## Log Locations

| Layer | Location |
| --- | --- |
| Browser | DevTools Console / Network |
| CDN | CDN access logs |
| API Gateway | Access logs |
| Worker | Runtime logs |
| Database | Slow query / connection metrics |

## Recovery Notes

