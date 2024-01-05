## Publish Java and Gradle Artifacts to Nexus hosted Repository

In this practical demo, we are going to learn how to publish artifacts to nexus hosted repository. As you know, Artifacts need to be stored somewhere safe, so, it can be used for other environments (dev, prod, etc) later.

![Upload](./images/image-1.png)

## Pre-Requisites
1- Make sure you have nexus application installed on AWS EC2. You can see my project 2 to setup nexus application.

## Steps:

1- Create a nexus user. click on the gear icon (Settings) and from left sidebar, click on the users tab.

![users](./images/image-2.png)

2- Once you have users screen opened, click on the create local user button.

![create](./images/image-3.png)

3- Fills the user form and give it anonymous role

![form](./images/image-4.png)
![form](./images/image-5.png)

4- The user has been created successfully. From sidebar, click on the roles tab.

![Roles](./images/image-6.png)

5- In the Roles screen, we will see a create role button, click on button.

![Create role](./images/image-7.png)

6- Fills the form and give it maven snapshot view all pivileges

![form](./images/image-8.png)
![form](./images/image-9.png)

7- Click save to create a role.

8- Assign that role to the user created before.

![Assign](./images/image-10.png)

9- Use the following Gradle project as an example

```https://gitlab.com/ibrarmunir/java-app```

10- Add a plugin for publishing jar to maven formatted repository 

![Plugin](./images/image-12.png)

11- Add the publishing block in build gradle file

```publishing {
    publications {
        maven(MavenPublication) {
            artifact("build/libs/my-app-$version"+".jar") {
                extension 'jar'
            }
        }
    }

    repositories {
        maven {
            name 'nexus'
            url 'http://54.210.82.35:8081/repository/maven-snapshots/'
             allowInsecureProtocol = true
            credentials {
                username
                password 
            }
        }
    }
}
```

![Publication](./images/image-13.png)

12- Create a gradle properties file where we will define nexus username and password since these are sensitive information.

![properties](./images/image-14.png)
![properties](./images/image-15.png)

13- Build the project

```./gradlew build```

14- Publush the artifact

```./gradlew publish```

![Publish](./images/image-17.png)
![Publish](./images/image-19.png)


### Publish Maven project to Nexus

1- Use the following project as an example

```https://gitlab.com/ibrarmunir/java-maven-app```

2- Open the pom.xml file and define the puglin just like gradle that enables maven to publish artifact to nexus

```
<build>
        <pluginManagement>
            <plugins>
                <plugin>
                    <groupId>org.apache.maven.plugins</groupId>
                    <artifactId>maven-deploy-plugin</artifactId>
                    <version>2.8.2</version>
                </plugin>
            </plugins>
        </pluginManagement>

        <plugins>
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-deploy-plugin</artifactId>
            </plugin>
        </plugins>
    </build>
```

![Plugin](./images/image-18.png)

3- Next step, define nexus repository configuration in pom.xml

```  <distributionManagement>
        <snapshotRepository>
            <id>nexus-snapshots</id>
            <url>http://54.210.82.35:8081/repository/maven-snapshots/</url>
        </snapshotRepository>
    </distributionManagement>
```

4- The way we configure nexus user credentials for repository in maven is in the .m2 folder in the user home directory. Create settings.xml file inside the .m2 folder inside the home directory.

![cred](./images/image-20.png)
![cred](./images/image-21.png)

5- Build the project using mvn package

```mvn package```

6- Deploy artifact

```mvn deploy```

![Deployed](./images/image-22.png)