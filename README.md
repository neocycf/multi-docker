# Introduction
Based on Stephen Grider's course. To deploy a react app using docker in AWS Elastic Beanstalk.

## Development mode
![dev_mode](/images/multi-docker_dev.jpg)

- uses docker-compose for local testing
- uses Dockerfile.dev
- uses react server default port 3000 to serve dev web server

## Production in AWS Elastic Beanstalk
![prod_mode](/images/multi-docker_prod.jpg)

Uses Dockerrun.aws.json to deploy multi-container.

Deployment process:
1. Push code to Github
2. Travis pulls repo
3. Travis builds test image, tests code
4. Travis builds prod image
5. Travis pushes image to Docker hub
6. Travis pushes project to AWS Elastic Beanstalk
7. Elastic Beanstalk pulls image from Docker hub and deploys

