# Install Docker on Linux machine or VM

## Install using the convenience script
1. Go to ```docs.docker.com```, then click on ```Get Docker```
2. From the left hand menu select ```Docker Engine```, then ```Install```, then select your system type, ```Linux```, then OS flavor ```Ubuntu```  
    ```NOTE:``` (*To install Docker Engine - Community, you need a 64-bit version OS*)
3. Uninstall any old version if any exist  
    ``` bash
    sudo apt-get remove docker docker-engine docker.io containerd runc
    ```
4. From the webpage, scroll down until you find ```Install using the convenience script```, and run the following commands
    ``` bash
    curl -fsSL https://get.docker.com -o get-docker.sh

    ls

    sudo sh get-docker.sh
    ```
5. Check the version of docker installed
    ``` bash
    sudo docker version
    ```
6. Go to ```hub.docker.com``` to test running containers on your system  
    ```NOTE:``` (*This site has a list of docker images to use*)
7. Use the search bar to find ```whalesay```
8. Run the following docker container
    ``` bash
    sudo docker run docker/whalesay cowsay Hello-World!
    ```

## Install using the ```apt``` repository
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