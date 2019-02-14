2nd task - Ingress setup

After Installtion the minikube check the status of minikube (please check the minikube installation page)

```Gauravs-MacBook-Pro:all gauravagnihotri$ minikube status
host: Running
kubelet: Running
apiserver: Running
kubectl: Correctly Configured: pointing to minikube-vm at 192.168.99.111```


RUN Mandatory Command is required for all kind of deployments 


1st command :
```kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/master/deploy/mandatory.yaml```

or 

```kubectl apply -f mandatory.yaml```   (this file is avialable in kubernetes folder)

2nd command:-

```minikube addons enable ingress```

3rd command to check the ingress controller status:-

```kubectl get pods -n kube-system | grep nginx-ingress-controller```

4th command to set the env for kubernetes to pull a image from local image pool.

``` eval $(minikube docker-env)```

5th command to deploy your service:-

```kubectl apply -f deployment-config.yml```

Note in the file called deployment-config.yml , I change the run and name tag with test-ingress-node-1, test-ingress-node-2 
respectively and run the below command to check service is created or not.

Gauravs-MacBook-Pro:kuburnetes gauravagnihotri$ kubectl get service
]NAME                  TYPE        CLUSTER-IP     EXTERNAL-IP   PORT(S)    AGE
kubernetes            ClusterIP   10.96.0.1      <none>        443/TCP    20h
test-ingress-node-1   ClusterIP   10.103.241.6   <none>        8080/TCP   11h
test-ingress-node-2   ClusterIP   10.110.88.29   <none>        5000/TCP   11h

Your both the service is cretaed test-ingress-node-1, test-ingress-node-2 with different port.

6th command :-
Now create Ingress service.
kubectl apply -f ingress-service.yaml

(wait for couple of minutes ,as ingress will be live)

Now run minikube command to know the IP.

Gauravs-MacBook-Pro:kuburnetes gauravagnihotri$ ```minikube ip```
192.168.99.111

Hit the URL :-

https://192.168.99.111/#/ 

Please check the below path to see the screenshot.

Pub_Challenge/kuburnetes/Screenshot 2019-02-14 at 10.09.20 AM.png











 





