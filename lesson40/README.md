## Kubernetes Services

![](./images/image-1.png)

![What is service](./images/image-2.png)

### 1- Cluster IP Service

![Internal Service](./images/image-3.png)
![Internal Service](./images/image-4.png)
![Internal Service](./images/image-5.png)

Note that when you create a service, kubernetes creates an endpoint object that has a same name as service and kubernetes keep track of which pods are members of the service.

![Endpoint](./images/image-6.png)

![Service Port](./images/image-7.png)

### Multi-Port Services

![Multi Port](./images/image-8.png)
![Multi Port](./images/image-9.png)

When you have multiple ports defined in a service, you have to name those ports.

![Multi Port](./images/image-10.png)

### 2- Headless Service

![Headless Service](./images/image-11.png)
![Headless Service](./images/image-12.png)

![Types](./images/image-14.png)

NodePort Service:

![NodePort Service](./images/image-15.png)
![NodePort Service](./images/image-16.png)
![NodePort Service](./images/image-17.png)

LoadBalancer Service:

![Load Balancer](./images/image-18.png)

When you create a Load balancer Service, NodePort and ClusterIP services automatically created by kubernetes. NodePort Port is only accessible via Cloud Provider Load balancer.


--------------------------------------------------

## Ingress

![File](./images/image-19.png)

![Ingress Controller](./images/image-20.png)
![Ingress Controller](./images/image-21.png)
![Ingress Controller](./images/image-22.png)

## Some Use-cases for Ingress

![1](./images/image-23.png)
![2](./images/image-24.png)

![TLS](./images/image-25.png)
![TLS](./images/image-26.png)