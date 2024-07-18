# Docker Commands


1. Start a Container
    ``` bash
    docker run nginx
    ```
2. List running Containers
    ``` bash
    docker ps
    ```

3. List all Containers
    ``` bash
    docker ps -a
    ```
4. Stop a Container
    ``` bash
    docker stop <name>
    ```

5. Remove a container
    ``` bash
    docker rm <name>
    ```

6. List of Images locally
    ``` bash
    docker images
    ```

7. Remove images  
 **NOTE** (*You need to stop all containers using that image*)
    ``` bash
    docker rmi <image> 
        i.e. docker rmi nginx
    ```
8. 