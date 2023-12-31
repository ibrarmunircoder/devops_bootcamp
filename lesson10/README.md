## Linux User and Permissions Part 2

User Permissions are related to reading, writing and executing files.

### Ownership
![Ownership](./images/image-1.png)
![Ownership](./images/image-2.png)

### Change Ownership
![change ownership](./images/image-3.png)

change only group
```sudo chgrp devops test.txt```

### File Permissions
![file type](./images/image-4.png)
![Permissions Block](./images/image-5.png)

### Modifying Permissions
![chmod](./images/image-6.png)

```sudo chmod g=rwx test.txt```
```sudo chmod g=r-- test.txt```

### Numeric Permission
![Numeric](./images/image-7.png)

```sudo chmod 740 script.sh```

![Wrap](./images/image-8.png)