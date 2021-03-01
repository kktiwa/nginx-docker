# nginx-docker

This project demonstrates using the docker nginx image to run a nginx server and deploy a static HTML page. The idea is
to build a working CI/CD pipeline that builds the Docker image with every change and then pushes the new docker image
and finally deploys by running the newly created image

## Incomplete Items

- Write docker tests to validate NGINX details
- Install Jenkins and run via Jenkinsfile