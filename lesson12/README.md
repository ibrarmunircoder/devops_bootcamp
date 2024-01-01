## Introduction Shell Scripting

![diff shell vs sh vs bash](./images/image-1.png)
![diff shell vs sh vs bash](./images/image-2.png)

### Why Shebang
![Shebang](./images/image-3.png)

![Variable](./images/image-4.png)

![Variable](./images/image-5.png)

### Conditions
![Condition](./images/image-6.png)

```bash
#!/bin/bash

echo "Setup and configure Server"
file_name=config.yml

if [ -d "config" ]
then
    echo "reading from config folder"
    config_contents=$(ls config)
else
   echo "Config dir not exist. Creating one"
   mkdir config
fi

echo "Using file $file_name to configure something"
echo "Here are all the configuration files: $config_contents"
```

### Basic Operators
![Operators](./images/image-7.png)
![Relational](./images/image-8.png)
![String Operators](./images/image-9.png)

### Positional Parameters
![Positional Parameter](./images/image-10.png)
![Positional Parameter](./images/image-11.png)
![Positional Parameter](./images/image-12.png)
![Positional Parameter](./images/image-13.png)

```bash
#!/bin/bash

echo "Setup and configure Server"
file_name=config.yml

if [ -d "config" ]
then
    echo "reading from config folder"
    config_contents=$(ls config)
else
   echo "Config dir not exist. Creating one"
   mkdir config
fi
user_group=$1

if [ "$user_group" == "ibrar" ]
then
   echo "Configure the server"
elif [ "$user_group" == "admin" ]
then
   echo "Administrator the server"
else
   echo "No permissions to configure server. No user group"
fi

echo "Using file $file_name to configure something"
echo "Here are all the configuration files: $config_contents"
```

### Loops
![Loop](./images/image-14.png)
![For Loop](./images/image-15.png)
![While Loop](./images/image-16.png)

![Parenthesis](./images/image-17.png)

When use double square brackets, you don't need to enclose varaibale in quotes
![double brackets](./images/image-18.png)

```bash
#!/bin/bash

echo "All the parameters $*"
echo "Number of Paramters $#"

for param in $*
 do
   if [ -d "$param" ]
   then
      echo "Executing script in the config folder"
      ls -l "$param"
   fi
   echo $param
 done

sum=0
while true
 do
   read -p "Enter a score" score
   if [ "$score" == "q" ]
   then
     break
   fi
   sum=$((sum+score))
   echo "Overall Score: $sum"
 done
```

### Functions
A function is way of grouping a set of logic, a set of commands into a reuseable components.
![Function](./images/image-19.png)

### Accepting arguments in Function
![Arguments](./images/image-20.png)
![Arguments](./images/image-21.png)

![Last command result](./images/image-22.png)

### Use-cases of Bash Scripting
![Usecases](./images/image-23.png)