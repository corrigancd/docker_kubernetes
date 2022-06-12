# instructions to docker for setting up a docker image

# the base image which the docker instance will be based on, python used below exists on DockerHub and will be used from there
FROM python

# We need to run npm install command from our app folder so we set the working directory, this also means copy . . below would copy to the app folder
WORKDIR /app

# copy contents of root folder into an app folder in the docker image
COPY . /app

EXPOSE 80

# the command to run when a container is started based on the image, should always be the last command in the dockerfile instruction
CMD ["python", "rng.py"]

# to run build docker image:
# docker build ./python-app-starting-setup/

# get the docker image list with
# docker image ls

# to create docker container that required arguments
# docker run -i -t <image id>

# after running it once, we can get the argument prompts each time it starts by running in attached mode and in interactive mode (the -t flag is remembered from before)
# docker run -a -i <image id>
