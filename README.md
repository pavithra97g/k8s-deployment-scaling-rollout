# Kubernetes Deployment + Scaling + Rollout

## Task Objective
To deploy a scalable application on Kubernetes, perform rolling updates, rollbacks, and configure health checks using readiness and liveness probes.

## Tools Used
- Minikube
- kubectl
- Nginx (sample application)

## Steps Performed
1. Created a Kubernetes Deployment YAML (`deployment.yml`) with 2 replicas
2. Applied deployment using `kubectl apply -f deployment.yml`
3. Verified deployment, ReplicaSet, and pods using `kubectl get deploy`, `kubectl get rs`, `kubectl get pods -o wide`
4. Inspected pods and verified load distribution across nodes
5. Scaled deployment horizontally to 5 replicas using `kubectl scale deployment nginx-deployment --replicas=5`
6. Updated the Nginx version in the deployment using `kubectl set image deployment/nginx-deployment nginx=nginx:1.26`  
7. Monitored the rollout progress and checked the rollout history using `kubectl rollout status deployment/nginx-deployment` and `kubectl rollout history deployment/nginx-deployment`  
8. Rolled back to previous version using `kubectl rollout undo deployment/nginx-deployment`
9. Added readiness and liveness probes to deployment YAML and verified health checks

## Architecture
       User Browser
            |
        Service IP
            |
   Kubernetes Cluster (Minikube)
            |
       Deployment → ReplicaSet
            |
       Pods (Nginx containers)


## Outcome
- Successfully deployed a scalable Kubernetes workload
- Performed rolling updates and rollback without downtime
- Learned how readiness and liveness probes work
- Understood Deployment → ReplicaSet → Pod hierarchy

## Screenshots
- `K8s-deploy.png` → Deployment created  
- `scaling.png` → Scaling to 5 replicas  
- `rollout-status.png` → Rolling update status  
- `rollback-undo.png` → Rollback execution
- `rollback-history.png` → Rollback history
