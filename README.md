# Kubernetes-Networking
![image](https://github.com/kamalmohan217/Kubernetes-Networking/assets/128888356/7887a56e-bec9-42cb-804f-638380e85b5c)
#### Container to Container Communication
All the containers inside the pod have the same IP address as assigned to the Pod. The **container to container communication happens over the localhost.** 
<br><br/>
In the diagram shown above Pod1 is a multi-container pod (with containers C1 and C2) and Pod2, Pod3 and Pod4 are single container pods. The Container to container communication is shown in the diagram above with green line.
<br><br/>
Below screenshot shows a yaml file using which created a pod (replicas: 1) through the deployment. This pod has two containers one main container (nginx-container) and another container is sidecar container (alpine-container). From main container sending the log files to sidecar container. 
![image](https://github.com/kamalmohan217/Kubernetes-Networking/assets/128888356/1f3c7ace-f6c6-4f75-b9db-ffeedae21a07)
Now check the IP address assigned to Pod and each of the containers(main container and sidecar container). They have the same IP address.
![image](https://github.com/kamalmohan217/Kubernetes-Networking/assets/128888356/07072ff4-bd3f-4a81-95b4-f168d033373f)
![image](https://github.com/kamalmohan217/Kubernetes-Networking/assets/128888356/548a1d92-a42e-4104-8a50-eb8a40567141)
![image](https://github.com/kamalmohan217/Kubernetes-Networking/assets/128888356/f4eb26f4-7bae-46e7-8e41-b889dd39d8e6)
![image](https://github.com/kamalmohan217/Kubernetes-Networking/assets/128888356/00311ec8-e3fa-488a-9692-cb782d2c82fa)
![image](https://github.com/kamalmohan217/Kubernetes-Networking/assets/128888356/136bd1af-8ec8-4350-b3f0-8ec0aa1fa985)
From the alpine container we did curl to the localhost we saw the home page for nginx.
![image](https://github.com/kamalmohan217/Kubernetes-Networking/assets/128888356/8027c8f4-8e6a-4659-a132-471387f51822)
