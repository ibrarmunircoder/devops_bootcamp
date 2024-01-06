## Demo: Docker in Software Development

![Diagram](./images/image-1.png)

1- Let's pull mongo and mongo-express images

```docker pull mongo```
```docker pull mongo-express```
![Mongo](./images/image-4.png)
![Mongo-express](./images/image-5.png)

## Docker Network

Docker containers run inside docker network. They can talk to each using just the container name without localhost, port becuase they are in the same network.

![Network](./images/image-2.png)
![Network](./images/image-3.png)

Docker by default provides some network.

```docker network ls```

Create a new network 

```docker network create mongo-network```

![network](./images/image-6.png)

Start the mongo container inside the new network 

```docker run -p 27017:27017 -d -e MONGO_INITDB_ROOT_USERNAME=admin -e MONGO_INITDB_ROOT_PASSWORD=admin123 --name mongodb --net mongo-network mongo```

![Mongo Run](./images/image-7.png)

Start the mongo express container inside the new network 

```docker run -d -p 8081:8081 -e ME_CONFIG_MONGODB_ADMINUSERNAME=admin -e ME_CONFIG_MONGODB_ADMINPASSWORD=admin123 -e ME_CONFIG_MONGODB_SERVER=mongodb --net mongo-network --name mongo-express mongo-express```

![Express](./images/image-8.png)

![Express](./images/image-9.png)

Now, Let's connect Nodejs backend with mongodb database. Clone the nodejs backend application by using the following link.

```https://gitlab.com/ibrarmunir/developing-with-docker.git```

Run the npm install command to download dependencies.

```npm i```

After you have cloned the nodejs backend application, open the server js file and update the mongo local url with the correct credentials and database name.

![Update](./images/image-11.png)

Run the Nodejs application with:
```npm run start```

![start](./images/image-12.png)

Open the browser and visit the localhost on port 3000 to load web app. Update the profile info and see if you see document in the mongodb collection.

![End](./images/image-13.png)
![End](./images/image-14.png)

Congratulations. You have completed the demo project. This is how local development looks like with docker.