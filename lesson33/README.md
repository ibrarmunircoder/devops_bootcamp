## Jenkins Webhhoks

![Ways to trigger build](./images/image-1.png)
![Ways to trigger build](./images/image-2.png)

## Configure automatic triggering of build for pipeline

Install the gitlab plugin

![Plugin](./images/image-3.png)

Once the plugin is installed, navigate to system configuration tab

![Gitlab](./images/image-4.png)

Generate a token on gitlab which is required while setting a API Toke Credentials in jenkins

Go to user preferences

![preferences](./images/image-5.png)

In the left sidebar, click on the access tokens

![access tokens](./images/image-6.png)

![form](./images/image-7.png)


Setup jenkins API Token type credentials by clicking on add button

![add](./images/image-8.png)

![Form](./images/image-9.png)

Now, we need to configure webhook on gitlab repository to automatically sent notification to jenkins whenever the change is made on that repository.

Click on repo settings and under settings click on integrations

![Settings](./images/image-10.png)

Scroll down and look for Jenkins

![Jenkins](./images/image-11.png)
![Jenkins](./images/image-13.png)
![Jenkins](./images/image-12.png)

Now, configure pipeline job to accept connection from jenkins. click on configure from left sidebar inside the pipeline job

![configure](./images/image-14.png)
![configure](./images/image-15.png)

![MultiBranch](./images/image-16.png)

1- Install Plugin for that

![Plugin](./images/image-17.png)

2- Navigate to multi branch pipeline configure tab

![configure](./images/image-18.png)
![configure](./images/image-19.png)

We will use this string "gitlabtoken" inside the gitlab webook configuration for a specific repository. This token could be any name.

3- Click on webhooks under settings of a repository.

![Webhook](./images/image-20.png)

```http://54.211.234.168:8080/multibranch-webhook-trigger/invoke?token=gitlabtoken```

![Add](./images/image-21.png)



