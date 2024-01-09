## Jenkins Pipeline

![Groovy](./images/image-1.png)

Groovy sandbox allows you to execute whitelisted functions withount any admin approval.

![Sandbox](./images/image-2.png)

## Pipeline Syntax

![Syntax](./images/image-3.png)
![Syntax](./images/image-4.png)
![Syntax](./images/image-5.png)

## Post Attribute

![Post](./images/image-6.png)

## Define Conditions

![Conditions](./images/image-7.png)
```groovy
stages {

        stage("test") {
            when {
                expression {
                    BRANCH_NAME == 'dev' || BRANCH_NAME == 'master'
                    // env.BRANCH_NAME == 'dev' || env.BRANCH_NAME == 'master'
                }
            }
            steps {
                echo "Testing the application"
            }
        }
}
```

## Environment Variables

![ENV](./images/image-8.png)

```http://18.204.205.100:8080/env-vars.html/```

## Define ENV variables for all stages

![ENV](./images/image-9.png)

## Using Jenkins Credientials as ENV variables

![Cred](./images/image-10.png)
![Cred](./images/image-11.png)
![Cred](./images/image-12.png)

## Define credentials in a specific stage using withcredentials

```groovy
     stage("build") { 
            
            steps {
                echo "building the application"
                echo "building version ${NEW_VERSION}"
                withCredentials([
                    usernamePassword(credentialsId: 'docker-hub-repo', usernameVariable: 'USER', passwordVariable: 'PWD')
                ]){
                    sh "echo some script ${USER} ${PWD}"
                }
            }
        }
```

Make sure you have these plugins installed to use credentials

![Plugins](./images/image-14.png)

## Access build tools in your jobs

![BuildTools](./images/image-13.png)

![Maven](./images/image-15.png)
![Maven](./images/image-16.png)

## Parameters in build

![Parameters](./images/image-17.png)
![Parameters Usage](./images/image-18.png)

## External Groovy Script

![Groovy](./images/image-19.png)
![Groovy](./images/image-20.png)
![Groovy](./images/image-21.png)
![Groovy](./images/image-22.png)
![Groovy](./images/image-23.png)
![Groovy](./images/image-24.png)

## Input Parameters from user in a stage

![Input](./images/image-25.png)

Expose only one input parameter to whole stages using environment variables inside script block

![Script](./images/image-26.png)


```groovy
pipeline {

    agent any

    tools {
        maven 'maven-3.9'
    }

    environment {
        NEW_VERSION = '1.1.0'
  
    }

    stages {

        stage("test") {
            when {
                expression {
               
                     env.BRANCH_NAME == 'dev' || env.BRANCH_NAME == 'master'
                }
            }
            steps {
                echo "Testing the application"
            }
        }

        stage("build") { 
            
            steps {
                echo "building the application"
                echo "building version ${NEW_VERSION}"
                withCredentials([
                    usernamePassword(credentialsId: 'docker-hub-repo', usernameVariable: 'USER', passwordVariable: 'PWD')
                ]){
                    sh "echo some script ${USER} ${PWD}"
                }
            }
        }

        stage("deploy") {
            input {
                message "Select the environment to deploy"
                ok "Done"
                parameters {
                    choice(name: 'ENV', choices: ['dev', 'prod', 'test'], description:'')
                }
            }
            
            steps {
                echo "Deploying the application"
            }
        }
    }

    // post {
    //     always {

    //     }
    //     success {

    //     }
    //     failure {

    //     }
    // }
}
```

