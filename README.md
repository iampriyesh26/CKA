# Kubernetes (CKA) Practice

This repository contains exercises and notes for Kubernetes practice aimed at Certified Kubernetes Administrator (CKA) preparation.

## Purpose
- Focused, hands-on practice for CKA exam (workloads, services, configuration, storage, cluster maintenance).
- Small, repeatable exercises you can run locally.

## Prerequisites
- OS: Windows (PowerShell preferred)
- Tools installed: `kubectl`, `docker` (or another container runtime), and either `kind` or `minikube`.
- Recommended: a text editor (VS Code) and familiarity with YAML.

## Quick setup (examples for PowerShell)
- Using kind (lightweight, ephemeral clusters):
  - Install kind: https://kind.sigs.k8s.io/
  - Create cluster:
    kind create cluster --name day2
  - Verify:
    kubectl cluster-info --context kind-day2

- Using Minikube (alternative):
  - Install minikube: https://minikube.sigs.k8s.io/
  - Start cluster with Docker driver:
    minikube start --driver=docker










































If you want, I can add ready-to-run YAML manifests for each Day 2 exercise or a PowerShell script to bootstrap the cluster and examples.---- minikube: https://minikube.sigs.k8s.io/- kind: https://kind.sigs.k8s.io/- CKA curriculum: https://training.linuxfoundation.org/certification/certified-kubernetes-administrator-cka/- Kubernetes documentation: https://kubernetes.io/docs## Resources- Keep answers idempotent (use apply, not create when possible).- Timebox tasks and read requirements carefully in the exam environment.- Memorize common flags and kubectl verbs (apply, get, describe, logs, exec, port-forward).- Practice YAML by hand; the exam requires editing and creating manifests.## Tips for CKA- kubectl cordon <node> && kubectl drain <node> --ignore-daemonsets --delete-local-data- kubectl rollout undo deployment/<name>- kubectl rollout status deployment/<name>- kubectl exec -it <pod> -- /bin/sh- kubectl logs <pod>- kubectl describe pod <name>- kubectl get pods,deploy,svc -A- kubectl apply -f <file.yaml>## Useful kubectl commands (cheat sheet)   - Simulate node failure and cordon/drain a node.   - Use `kubectl describe`, `kubectl logs`, `kubectl top` (metrics-server) and `kubectl exec`.7. Debugging & Maintenance   - Create a namespace and limit access with Role/RoleBinding.6. Namespaces and RBAC   - Use nodeSelector and tolerations / taints.   - Add liveness and readiness probes to a pod.5. Probes and Scheduling   - Practice deleting pods and verifying PVC/PV behavior.   - Create a PersistentVolumeClaim and mount it into a pod.4. Storage   - Inject ConfigMap and Secret into a pod as env vars and files.3. ConfigMaps & Secrets   - Test service connectivity from inside the cluster (busybox / curl).   - Expose a Deployment with ClusterIP and NodePort service types.2. Services and Networking   - Create a Deployment and perform a rolling update and rollback.- [CKA Exam Curriculum](https://training.linuxfoundation.org/certification/certified-kubernetes-administrator-cka/)

---

Feel free to contribute or suggest improvements!