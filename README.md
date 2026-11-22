# Kubernetes Fundamentals Lab

I used Minikube v1.39.0 with VirtualBox on Ubuntu to run a single-node
Kubernetes v1.37.0 cluster. The node used containerd 2.3.4.

## What I built and verified

- Created a standalone Nginx Pod and inspected its status, events, and logs.
- Created a two-replica Deployment. After I deleted one Pod, Kubernetes
  created a replacement and returned to two ready replicas.
- Created a ClusterIP Service. Nginx returned HTTP 200 from inside the cluster
  and from Ubuntu through port forwarding on port 8040.
- Set CPU and memory requests to 50m and 32Mi and limits to 200m and 64Mi
  per Deployment container. Both new Pods showed the Burstable QoS class.

## Project files

- `manifests/pod.yaml` — standalone Nginx Pod
- `manifests/deployment.yaml` — two-replica Nginx Deployment
- `manifests/service.yaml` — ClusterIP Service
- `evidence/` — terminal output from the verification steps
- `TROUBLESHOOTING.md` — issue, diagnosis, fix, and verification
