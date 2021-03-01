# nginx-docker

This project demonstrates using the docker nginx image to run a nginx server and deploy a static HTML page. The idea is
to build a working CI/CD pipeline that builds the Docker image with every change and then pushes the new docker image
and finally deploys by running the newly created image

### Install nginx manually
Although the base image directly uses `nginx` image, it could be manually installed via the below command in Dockerfile:
```
RUN apt-get install -y nginx
```

## Incomplete Items

- Write docker tests to validate NGINX details
- Install Jenkins and test CI/CD pipeline via Jenkinsfile