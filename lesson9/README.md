## Linux User and Permissions Part 1

### User Accounts

### 1- Superuser Account
Whenever you need to perform administrative tasks or access restricted files on system, you need to login as root user.

![Root](./images/image-1.png)

### 2- User Account
![User](./images/image-2.png)

### 3- Service Account
No service (Apache, Mysql) should be run as a root user because it will get root user privileges. It may disrupt the whole system
![Service](./images/image-3.png)

![Multiple Users](./images/image-4.png)

### Permissions Level
![Levels](./images/image-5.png)
![Levels](./images/image-6.png)

![User info locations](./images/image-7.png)

![/etc/passwd](./images/image-8.png)
![user entry](./images/image-9.png)
![Primary Group0](./images/image-10.png)

#### Create User
![create](./images/image-11.png)

#### Change Password
![change](./images/image-12.png)

#### Switch User
![Switch User](./images/image-13.png)

#### Create Group
![Group](./images/image-14.png)

#### Commands difference
![diff](./images/image-15.png)
![diff](./images/image-16.png)
![diff](./images/image-17.png)

#### Change User Primary Group
![change](./images/image-18.png)


delgroup = delete the group


#### Add Secondary Group
![Secondary](./images/image-19.png)


#### Adduser command
![add](./images/image-20.png)

#### Remove user from group

```sudo gpasswd -d tom devops```