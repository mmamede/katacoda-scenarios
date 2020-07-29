## Task

`minikube start`{{execute}} 

Abrir novo arquivo - `newFile.yaml`{{open}}

<pre class="file" data-filename="pod-1.0.yaml" data-target="replace">apiVersion: v1
kind: Pod
metadata:
  name: webapp
  labels:
    app: webapp

</pre>
<pre class="file" data-filename="pod-1.0.yaml" data-target="append">
spec:
  containers:
  - name: webapp
    image: mamede/k8s-intro-v2
</pre>

<pre class="file" data-filename="service-1.0.yaml" data-target="replace">apiVersion: v1
kind: Service
metadata:
  name: service-webapp
  
spec:
  type: NodePort
  selector: 
    app: webapp
    
  ports:
    - name: http
      port: 80
      nodePort: 30080
</pre>

`kubectl apply -f myk8s/.`{{execute}} 


https://[[HOST_SUBDOMAIN]]-[[KATACODA_HOST]].environments.katacoda.com/


https://[[HOST_SUBDOMAIN]]-30080-[[KATACODA_HOST]].environments.katacoda.com/
