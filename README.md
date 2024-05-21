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
From the alpine container we did curl to the localhost and we saw the home page for nginx.
![image](https://github.com/kamalmohan217/Kubernetes-Networking/assets/128888356/8027c8f4-8e6a-4659-a132-471387f51822)
#### Pod to Pod Communication
**In kubernetes each pod has a unique IP address. When communication happens between the pods then it will happen over the IP address assign to the pod. The traffic flows from eth0 of Pod1 to eth0 of Pod2 through the virtual bridge network.**
![image](https://github.com/kamalmohan217/Kubernetes-Networking/assets/128888356/9746442c-72f2-4bde-8d7e-7d1f47c1905a)
![image](https://github.com/kamalmohan217/Kubernetes-Networking/assets/128888356/c63f0c95-2c50-4228-9717-29ee7a757741)
![image](https://github.com/kamalmohan217/Kubernetes-Networking/assets/128888356/b20ef348-1226-4519-98a2-c649a0dbde6b)
**Pod to Pod communication happens over the IP address assigned to the pod.**
<br><br/>
#### Pod to Service Communication
![image](https://github.com/kamalmohan217/Kubernetes-Networking/assets/128888356/92f46427-8468-4142-8fa7-1ca2ca35e09f)
