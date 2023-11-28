# Docker by A Cloud Guru

## Installation
```shell
# update Server
sudo apt update -y

# install prerequisite packages for Docker to run
sudo apt install apt-transport-https ca-certificates curl gnupg-agent software-properties-common

# pull down docker gpg key
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

# verify its configuration
sudo apt-key fingerprint 0EBFCD88

# add the Docker Repository
sudo add-apt-repository  "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"

# update server again
sudo apt update

# install necessary packages
sudo apt install docker-ce docker-ce-cli containerd.io

# add user to the Docker Group
sudo usermod ubuntu -aG docker
```

## Launching a Container
```shell
# hello-world container
docker run hello-world

# see containers running
docker container ls

# see all containers whether running or stopped
docker container ls -a

# run a container
docker run <image>

# launch a container and drop to shell
docker run -it  <image>

# allow container to run in background/persist
docker run -d <image>

# Container restart settings
docker run -dt --restart always --name CGnR-container alpine

# Remove container when exited
docker run --rm <image>

# Provide container nickname
docker run --name <name> <image>


# -i, --interactive - Keep STDIN open
# -t, --tty - Locate a psuedo-tty; without this, there's no command prompt
# -d, --detach - Run the container in the background
# restart <value> - Set restarting parameters
# no - Never restart
# always - Always restart when stopped
# unless-stopped - Restart unless manually stopped
# on-failure<:retries> - Restart when the container fails; we can supply the maximum amount of retries
# --rm - Remove the container upon exit
# --name <name> - Provide a nickname for the container

```