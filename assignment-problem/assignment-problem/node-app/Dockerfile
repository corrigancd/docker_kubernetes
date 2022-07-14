# instructions to docker for setting up a docker image

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
EXPOSE 3000

# the command to run when a container is started based on the image, should always be the last command in the dockerfile instruction
CMD ["node", "server.js"]
