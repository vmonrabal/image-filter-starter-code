# Udagram Image Filtering Microservice

Udagram is a simple cloud application developed alongside the Udacity Cloud Engineering Nanodegree. It allows users to register and log into a web client, post photos to the feed, and process photos using an image filtering microservice.

The project is split into three parts:
1. [The Simple Frontend](https://github.com/vmonrabal/udagram-frontend/tree/master)
A basic Ionic client web application which consumes the RestAPI Backend. [Covered in the course]
2. [The RestAPI Backend](https://github.com/vmonrabal/udacity-c2-restapi/tree/master), a Node-Express server which can be deployed to a cloud service. [Covered in the course]
3. [The Image Filtering Microservice](https://github.com/vmonrabal/image-filter-starter-code/tree/master), the final project for the course. It is a Node-Express application which runs a simple script to process images. [Your assignment]

## Project Rubric tasks
### Engineering Process and Quality

Changes in the below files:
[server.ts](https://github.com/vmonrabal/image-filter-starter-code/blob/master/src/server.ts)
[util.ts](https://github.com/vmonrabal/image-filter-starter-code/blob/master/src/util/util.ts)

### Development Server
#### The project demonstrates the ability to develop using the NodeJS framework
![npm run dev](https://raw.githubusercontent.com/vmonrabal/image-filter-starter-code/master/deployment_screenshots/npm_run_dev.png)

#### The project demonstrates an understanding of RESTFUL design
![200](https://raw.githubusercontent.com/vmonrabal/image-filter-starter-code/master/deployment_screenshots/localhost_200-OK.png)

#### The project demonstrates an understanding of HTTP status codes
![400](https://raw.githubusercontent.com/vmonrabal/image-filter-starter-code/master/deployment_screenshots/localhost_400-BAD-REQUEST.png)

![422](https://raw.githubusercontent.com/vmonrabal/image-filter-starter-code/master/deployment_screenshots/localhost_422-UNPROCESSABLE.png)

### Elastic Beanstalk Deployment
[EB URL endpoint](http://image-filter-app-dev.eu-central-1.elasticbeanstalk.com/filteredimage?image_url=https://upload.wikimedia.org/wikipedia/commons/b/bd/Golden_tabby_and_white_kitten_n01.jpg)

#### The project demonstrates the ability to create functional cloud deployments
![200](https://raw.githubusercontent.com/vmonrabal/image-filter-starter-code/master/deployment_screenshots/EB_200-OK.png)

![200](https://raw.githubusercontent.com/vmonrabal/image-filter-starter-code/master/deployment_screenshots/EB-Rubric_image_200-OK.png)

![400](https://raw.githubusercontent.com/vmonrabal/image-filter-starter-code/master/deployment_screenshots/EB_400-BAD-REQUEST.png)

![422](https://raw.githubusercontent.com/vmonrabal/image-filter-starter-code/master/deployment_screenshots/EB_422-UNPROCESSABLE.png)


#### The project demonstrates an understanding of AWS Elastic Beanstalk’s CLI and Console Dashboard

![EB Deployment](https://raw.githubusercontent.com/vmonrabal/image-filter-starter-code/master/deployment_screenshots/EB_deployment.png)

![EB Dashboard](https://raw.githubusercontent.com/vmonrabal/image-filter-starter-code/master/deployment_screenshots/EB_environment.png)

## Tasks

### Setup Node Environment

You'll need to create a new node server. Open a new terminal within the project directory and run:

1. Initialize a new project: `npm i`
2. run the development server with `npm run dev`

### Create a new endpoint in the server.ts file

The starter code has a task for you to complete an endpoint in `./src/server.ts` which uses query parameter to download an image from a public URL, filter the image, and return the result.

We've included a few helper functions to handle some of these concepts and we're importing it for you at the top of the `./src/server.ts`  file.

```typescript
import {filterImageFromURL, deleteLocalFiles} from './util/util';
```

### Deploying your system

Follow the process described in the course to `eb init` a new application and `eb create` a new environment to deploy your image-filter service! Don't forget you can use `eb deploy` to push changes.

## Stand Out (Optional)

### Refactor the course RESTapi

If you're feeling up to it, refactor the course RESTapi to make a request to your newly provisioned image server.

### Authentication

Prevent requests without valid authentication headers.
> !!NOTE if you choose to submit this, make sure to add the token to the postman collection and export the postman collection file to your submission so we can review!

### Custom Domain Name

Add your own domain name and have it point to the running services (try adding a subdomain name to point to the processing server)
> !NOTE: Domain names are not included in AWS’ free tier and will incur a cost.
