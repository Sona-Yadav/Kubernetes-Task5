# Task 5 - Minikube Kubernetes Deployment

## Objective
Deploy and manage an application locally using Kubernetes with Minikube.

## Tools Used
1. Minikube (Local Kubernetes cluster)
2. kubectl (Kubernetes CLI tool)
3. Docker Desktop (Container runtime)
4. Windows 11

## Steps Followed
1. Install Required Tools
--- Installed Docker Desktop and enabled Kubernetes support.
--- Install Minikube Manually (No Chocolatey)
                Go to: https://github.com/kubernetes/minikube/releases
                Download the latest minikube-windows-amd64.exe.
                Rename it to minikube.exe.
                Move it to a folder like: C:\Program Files\Kubernetes\
               Add that folder to your System PATH:
               Search "Edit system environment variables" → Environment Variables → Under "System variables", find Path → Edit → Add the folder path.
               minikube version
   <img width="1257" height="673" alt="image" src="https://github.com/user-attachments/assets/bc60386e-44b5-4c12-978f-dbabe817387e" />


2. Create Deployment.yml
      ---kubectl apply -f deployment.yaml
      ---kubectl get pods
   <img width="759" height="137" alt="image" src="https://github.com/user-attachments/assets/5b60ddca-0e90-4f4b-849c-877b9a5f9b48" />


4. Expose Deployment with a Service (service.yaml)
   --- kubectl apply -f service.yaml
   --- kubectl get services
   <img width="822" height="164" alt="image" src="https://github.com/user-attachments/assets/2c75d46d-cbd6-4e47-a5a4-2dd7924178e1" />

   Get URL: minikube service hello-service
<img width="918" height="359" alt="image" src="https://github.com/user-attachments/assets/f223e13e-1d16-4663-8594-d9046f0460f8" />

<img width="1918" height="696" alt="image" src="https://github.com/user-attachments/assets/b3f373c2-f426-4a87-88f9-2bcedb67615c" />

5. Scale Deployment
   --- kubectl scale deployment hello-deployment --replicas=4
  --- kubectl get pods
   <img width="951" height="220" alt="image" src="https://github.com/user-attachments/assets/55a39612-b99a-4ab7-9783-889fec2899cc" />

6. View Logs & Describe
  --- kubectl describe deployment hello-deployment
  --- kubectl logs <pod-name>
