## Containers

A container is a way to package application with everything the application needs in order to run it including its dependencies, code and configuration.

Containers are portable. They can be moved around between development team or development and operations team.

![Container](./images/image-1.png)
![Container](./images/image-2.png)


![Improve](./images/image-4.png)

## How containers improve application development process

![Installing software](./images/image-5.png)

The chances of something going wrong and error happening is pretty high becuase of the numbers steps require to install each service. This process of setting up new environment, let's say setting up 100 computers, can be pretty tedious depending on how complex your application is.   

## After Containers

Container can be considered as isolated environment.

With containers, you don't directly install softwares on your operating system. Containers have their own operating system with linux based image. One command to install and run container whether you are using linux and windows.

Also, you can have different versions of the same application running on your local environments without having any conflicts. 

![After](./images/image-7.png)

## Improve Application Deployment

![Before](./images/image-8.png)


## Container Vs Images

![Diff](./images/image-10.png)
![Diff](./images/image-17.png)

## Container VS VM
![VM vs Container](./images/image-11.png)
![VM vs Container](./images/image-12.png)
![VM vs Container](./images/image-13.png)

## Docker Architecture and its components

![Docker Engine](./images/image-14.png)

Docker server or Daemon has its own parts.

Docker Runtime = Responsible for pulling images, managing container lifercycle (creating, updating and deleting)

![Docker Server](./images/image-15.png)
![Docker Server](./images/image-16.png)