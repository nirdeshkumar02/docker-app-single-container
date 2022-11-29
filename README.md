# frontend -
## Overview - This Project comes handy to make you understand how you can make refernce of your local project to docker container using volumes. you don't need to copy the project files inside container so that whatever changes you make inside local they can reflect to container. also helpful in understanding production greade workflow. 

## Testing - we include some testing inside it. There are some ways to check live test - 

1. Run `docker-compose up` command and live the application. Now from another terminal take the container id using `docker ps` and run `docker exec -it container-id npm run test`, so that you can run the test on app.
2. Inside docker-compose file add another service for test as did in docker-compose file. check it for your refrence but it run only one time, if you need to run test again through terminal as you can do in option 1 not possible.

## Production - Multi Step Dockerfile is used for production ready container because we need only care for build folder for react app, its only served for production, for ref check the Dockerfile.prod.
1. Using Multi Step we 1st build the application using `npm run build`.
2. Then using 1st steps result to run application in nginx webserver.

## Deployment - Deploying Application to other world on AWS using Travis CI Workflow -
`Code -> GitHub (Feature Branch) -> Pull Request -> GitHub (Master Branch) -> Travis CI -> Aws Hosting`
