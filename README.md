## Task 6.2C – Interacting with Kubernetes

This part of the task focuses on interacting with the Kubernetes cluster we set up earlier in Task 6.1P. The goal was to verify that the app is running, forward ports from Kubernetes to the browser, and access the service on `localhost`.

### StepsFollowed

#### 1. Started Minikube
```
minikube start --driver=docker
```
This restarted my existing Minikube cluster.

#### 2. Checked if the app is running
I used these commands to confirm that everything was still deployed and working:
```
kubectl get pods
kubectl get svc
```
The pod was in "Running" state, and the service showed NodePort was mapped to port `3000`.

#### 3. Port Forwarding
To access the app in the browser, I ran:
```
kubectl port-forward service/node-app-service 3001:3000
```
This forwarded my local port 3001 to the Kubernetes service port 3000.


#### 4. Opened the App in the Browser

I tested the app by visiting:
-  `http://localhost:3001/add?num1=10&num2=5` → `{ "result": 15 }`
-  `http://localhost:3001/divide?num1=10&num2=5` → `{ "result": 2 }`

Both results showed up perfectly in the browser.

### Screenshots I Took
- `kubectl get pods` output
- `kubectl get svc` output
- Terminal showing port-forward command
- Browser result for `/add` and `/divide` endpoints
