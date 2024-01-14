## Kubernetes Volumes

![Volume Types](./images/image-1.png)

## Storage Requirements

1- Storage doesn't depend on the Pod lifecycle. If the MySQL gets restarted, the storage component must be available and have all the data.

2- We don't know where the pod is going to be scheduled. Basically, We don't know on which Node the pod will be scheduled. Storage must be available on all nodes.

3- The Storage needs to survive even if the cluster crashed as a whole.

![Requirements](./images/image-2.png)
![Requirements](./images/image-3.png)

## Persistent Volume

![PV](./images/image-5.png)
![PV](./images/image-6.png)
![PV](./images/image-7.png)
![PV](./images/image-8.png)

![Namespace Scope](./images/image-9.png)

## Local vs Remote  Storage

![Local](./images/image-10.png)

### Persistent Volume should be there in cluster before

![PV](./images/image-11.png)

### Kubernetes Roles

![Roles](./images/image-12.png)

Based on the storage requirements from developers team of what type of storage they need, K8s admin will provision that storage backend by using PV component.

### PVC

![PVC](./images/image-13.png)
![PVC](./images/image-14.png)
![PVC](./images/image-15.png)

### Levels of Volumes Abstraction

![Abstraction](./images/image-16.png)

### Note that Claim must be in the same namespace as Pod using that claim

![Mount](./images/image-17.png)

![Configmap or Secrete as Volums](./images/image-18.png)

### Different Volume types in POD

![](./images/image-19.png)

### Storage Class

![SG](./images/image-20.png)
![SG](./images/image-21.png)
![SG](./images/image-22.png)