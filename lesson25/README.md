## Docker Compose

Run multiple containers with declarative way

![Diff](./images/image-1.png)
![Diff](./images/image-2.png)
![Diff](./images/image-3.png)

![Docker compose network](./images/image-4.png)
![Docker compose network](./images/image-5.png)

## Dockerfile

![file](./images/image-6.png)

```yml
FROM node:13-alpine

ENV MONGO_DB_USERNAME=admin \
    MONGO_DB_PWD=admin123

RUN mkdir -p /home/app

COPY ./app /home/app

# set default dir so that next commands executes in /home/app dir
WORKDIR /home/app

# will execute npm install in /home/app because of WORKDIR
RUN npm install

# no need for /home/app/server.js because of WORKDIR
CMD ["node", "server.js"]
```