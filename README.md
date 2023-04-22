## How do I know if I need NodePort or ClusterIP services to expose my Pods?


```
Choosing between the two types of services is extremely simple, basically because they are 
not meant for the same thing.
If you need your app to be accessible from outside the cluster, then you'll need a 
NodePort service, but if you need your app to be accessible from inside the cluster, then 
you'll need a ClusterIP service. It's as simple as that! ClusterIP services are also 
good for stateless applications that can be scaled, destroyed, recreated, and so on. 
The reason is that the ClusterIP service will maintain a static entry point to a whole 
pool of Pods without being constrained by a port on the worker node, unlike the 
NodePort service. 
Contrary to NodePort services, ClusterIP services will not take one port of the 
worker node, and thus it is impossible to reach it from outside the Kubernetes cluster.
Keep in mind that nothing prevents you from using both types of services for the same 
pool of Pods. Indeed, if you have an app, that should be publicly accessible, but also 
privately exposed to other Pods, then you can simply create two services, one NodePort
service and one ClusterIP service.
In this specific use case, you'll simply have to name the two services differently so that 
they won't conflict when creating them against kube-apiserver. Nothing else prevents 
you from doing so!
```