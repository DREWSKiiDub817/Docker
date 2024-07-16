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

1. update Server
    ```shell
    sudo apt update -y
    ```
2. install prerequisite packages for Docker to run
    ```shell
    sudo apt install apt-transport-https ca-certificates curl gnupg-agent software-properties-common
    ```
3. pull down docker gpg key
    ```shell
    curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
    ```
4. verify its configuration
    ```shell
    sudo apt-key fingerprint 0EBFCD88
    ```
5. add the Docker Repository
    ```shell
    sudo add-apt-repository  "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
    ```
6. update server again
    ```shell
    sudo apt update
    ```
7. install necessary packages
    ```shell
    sudo apt install docker-ce docker-ce-cli containerd.io
    ```
8. add user to the Docker Group
    ```shell
    sudo usermod ubuntu -aG docker
    ```