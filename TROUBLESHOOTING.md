# Troubleshooting Log

## Deployment manifest path error

**Symptom:** `kubectl apply` reported that `manifests/deployment.yaml` did
not exist. The rollout check still reported success for the existing
Deployment, whose Pods still showed the BestEffort QoS class.

**Cause:** I ran the command from the `manifests/` directory using a path
relative to the project root. The evidence file path failed for the same reason.

**Fix:** I returned to `~/kubernetes-fundamentals`, reapplied the manifest,
and waited for the new rollout to finish.

**Verification:** Both replacement Pods were ready and showed the expected
CPU and memory requests and limits. Their QoS class was Burstable. The
output is saved in `evidence/resource-settings.txt`.
