# instructions to docker for setting up a docker image

# the base image which the docker instance will be based on, node used below exists on DockerHub and will be used from there
FROM node

# We need to run npm install command from our app folder so we set the working directory, this also means copy . . below would copy to the app folder
WORKDIR /app

# an optimisation step, now npm install will only run if a change has been detected in the package.json file
COPY package.json /app

# this will be executed after the copy phase
RUN npm install

# copys all the files in the base path of the node application into an app folder in the docker instance
COPY . /app

# specify the port that is visible for outside of the container, 
# THIS IS NOT NECESSARY IF WE EXPOSE THE PORT LIKE BELOW. EXPOSING AS BELOW IS REQUIRED
# IF WE WANT TO ACCESS THE CONTAINER FROM OUTSIDE (PRETTY MUCH ALWAYS REQUIRED!!)
EXPOSE 80

# the command to run when a container is started based on the image, should always be the last command in the dockerfile instruction
CMD ["node", "server.js"]


# to create an instance type:
# sudo docker build .
# to create a container based on this image:
# docker run -p <local-host-port>:<internal-docker-container-exposed-port> <image-name>

# to create a docker image in detached mode (the advantage here is that the same terminal can be used for other purposes)
#docker run -p 3003:80 -d a38d7e898ffe

## sample output:
#e96bd8b0f0e6190b7fee325ebf86e1bbc7f21fff7344a7b66f1295c1a6d08627

# then usng the id in the output above, we can use docker attach to access the running container
# Note - the name can be got by typing `docker ps`
# docker attach <container name> 
