## Jenkins Credentials

![Credentials Scope](./images/image-1.png)

## Third Credentials Scope is multibranch pipeline

![Third Scope](./images/image-2.png)

We can separate credentials between projects using multi-branhc pipeline credientials.

## What is Jenkins Shared Library? Why we need it?

![Why](./images/image-3.png)
![What](./images/image-4.png)

![Use-case](./images/image-5.png)

## Steps to create shared library

![Steps](./images/image-8.png)

## Jenkins Shared Library structure

![Structure](./images/image-6.png)
![Structure](./images/image-7.png)

When you reference function from jenkins shared library into a job, you will reference it by function name.

![buildJar](./images/image-9.png)


## Use Jenkins Library in Jenkins

1- Go inside manage jenkins and click on systems

![System](./images/image-10.png)

2- Find the Global pipeline libraries Section

![Pipeline](./images/image-11.png)

3- Add a name and in the default version, you could either add branch name or specific commit hash.

![fomr](./images/image-12.png)

4- Add Repository Details and credentials

![form](./images/image-13.png)

5- Usage in jenkinsfile

```groovy
@Library('jenkins-shared-library')_
def gv

pipeline {

    agent any

    tools {
        maven 'maven-3.9'
    }

    stages {

        stage("init") {
            steps {
                script {
                    gv = load "script.groovy"
                }
            }
        }

        stage("build jar") {
            steps {
                script {
                    buildJar()
                }
            }
        }

        stage("build image") { 
            steps {
                script {
                    buildImage()
                }
            }
        }

        stage("Deploy") {
            steps {
                script {
                    gv.deployApp()
                }
            }
        }
    }
}

```

6- Let's parameterize our build image function

![Pass Parmas](./images/image-14.png)
![Pass Parmas](./images/image-16.png)

7- We can also global Env variables in groovy shared script

![ENV](./images/image-15.png)

## Instead adding global pipeline libraries, we can also define and reference the shared library within Jenkinsfile which is only available for this pipeline job.

![Local Library reference](./images/image-17.png)

