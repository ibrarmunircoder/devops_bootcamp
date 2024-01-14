## Configmap and Secret as Kubernetes Volumes

![How to create configuration files as configmap and secret](./images/image-1.png)

## ConfigMap and Secret use-cases

1- With these components, you can create individual key value pairs such as username and password.

2- But, By using these components, you can also create files that will be mounted into Pod and then mounted into the container. Some Application needs configuration files on start.

![](./images/image-2.png)

## Examples
![1](./images/image-3.png)
![2](./images/image-4.png)
![3](./images/image-5.png)


## StatefulSet

What is stateful Application?

Any Application that stores data to keep track of its state. In other words, the stateful application tracks state by saving information in some storage.

![Stateless vs stateful](./images/image-6.png)

Pod identity

![Identity](./images/image-7.png)

![why](./images/image-8.png)
![why](./images/image-9.png)

only one pod will be master pod responsible for writing into the database and other pods are reader.

Each Pods has its own physical storage. They don't use the same physical storage.
![Same](./images/image-10.png)

In addition to Pod identity, Each pod has it DNS endpoint from a service.
![DNS endpoint](./images/image-12.png)
![DNS endpoint](./images/image-13.png)

## 2 Charactertics (Fixed Pod name and Fixed DNS Endpoint) 

![2 Characteristics](./images/image-14.png)


![Complex](./images/image-15.png)