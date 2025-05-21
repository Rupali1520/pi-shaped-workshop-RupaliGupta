# Docker Day 2 Exercise 

## Overview
This is a simple Flask-based "Hello, World!" REST API that was containerized using Docker (from Day 1) and now deployed on Kubernetes using pod scheduling with **node affinity** , **Limited resources** and **tolerations**.

## How to Run

```bash
git clone https://github.com/yourusername/pi-shaped-workshop-RupaliGupta.git
cd pi-shaped-workshop-RupaliGupta/docker-k8s-workshop/day2
kubectl label nodes <node-name> disktype=ssd
kubectl taint nodes <node-name>  env=dev:NoSchedule
kubectl apply -f Deployment.yaml
kubectl get pods -o wide
kubectl port-forward pod/flask-hello-pod-affinity 8080:8080  #Access the Flask App
```


## Core Concept Questions

### 1. Why do we set requests and limits for CPU/memory in a production-grade product?

In a real production system, many applications run together on the same cluster. Setting resource requests and limits helps:

1. Ensure fairness – So one app doesn't consume all the CPU/memory and crash others.

2. Prevent overuse – Limits stop a container from using more than allowed.

3. Plan capacity – Requests tell Kubernetes how much resource a pod needs to work well, which helps with proper scheduling.

4. Improve stability – It keeps the system stable and avoids node crashes due to memory or CPU exhaustion.

So, resource limits and requests help keep your product reliable, fast, and stable — even under load.

---

### 2. When would a product team apply node affinity in Kubernetes?

A product team uses node affinity when they want to make sure a pod runs only on certain nodes based on labels.

Examples:

1. To run a database pod only on nodes with fast SSDs (disktype=ssd)

2. To schedule sensitive workloads only on secure nodes

3. To run heavy apps only on high-memory or GPU nodes

In short, node affinity helps place the right workload on the right machine for better performance, security, and efficiency.


