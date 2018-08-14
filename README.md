# Docker - Getting Started
### Found [here](https://nodejs.org/en/docs/guides/nodejs-docker-webapp/)

##  Creating a Basic Node App

`touch package.json`
- include a package.json with all dependencies your app will need, then run
`npm install`

`touch server.js`
- create a server.js which will be the jumping off point for your Node app

`npm start`
- make sure it's running correctly, then visit http://0.0.0.0:8080 in the browser to see a super fun message!!

## On to the Docker Stuff

`touch Dockerfile`
- this is the file that will tell Docker what to do and how to build your app in a container

`touch .dockerignore`
- add node_modules and npm stuff in there

### From your project root
`docker build -t pre:test .`
- after it builds, run
`docker images` 
- this will show a list of the images you have pulled

`docker run -p 49160:8080 -d pre:test`
- to run the image you previously built
- -d runs the container in detached mode, leaving the container running in the background
- -p redirects a public port to a private port inside the container
- you should get a unique ID printed out

`docker ps`
- gives you the health status and Container ID of your container
`docker logs <container id>`

`curl -i localhost:49160`
- can call the app with a curl