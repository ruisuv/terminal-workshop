# Ordinary World (prerequisites)

## Install Docker Desktop
Fun thing to use GUI in a Terminal Workshop, but it will be harder if I try to get every single possibility with commands.

Click [this link](https://www.docker.com/products/docker-desktop/) and choose the versions for your machine.

Please be patience. 
I would recommend to listen to your favorite playlist, but I don't want your bandwidth to be reduced by streaming services.

For Windows users:
1. Why?
2. Troubleshooting can be found [here](https://docs.docker.com/desktop/windows/troubleshoot/#virtualization)


## Ubuntu distro on Docker

- Download Ubuntu image 

  `docker pull ubuntu`
- Get the container id 

    `docker ps -f ancestor=ubuntu`
  - Output should be something like
  ```
  CONTAINER ID   IMAGE           COMMAND   CREATED       STATUS       PORTS     NAMES
  d01d18af48ad   ubuntu:latest   "bash"    4 hours ago   Up 3 hours             elated_brahmagupta
  ```
- Access to the new container using the CONTAINER ID from the previous step 

  `docker exec -it $CONTAINER_ID bash`
- Verify if everything is ok by doing your first `ls`. Output should be similar to:
    ```
    root@d01d18af48ad:/# ls
    bin  boot  dev  etc  home  lib  media  mnt  opt  proc  root  run  sbin  sd.txt  srv  sys  tmp  usr  var
    ```
