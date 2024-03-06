
# View Docker Log: Dozzle

## Introduction
Dozzle is a small lightweight application with a web based interface to monitor Docker logs.
It is for live monitoring of your container logs only.



## Installation
The easiest way to setup Dozzle is to use the CLI and mount docker.sock file.

```
docker run --detach --volume=/var/run/docker.sock:/var/run/docker.sock -p 8080:8080 amir20/dozzle
```

This will run the dozzle in the port 8080 by default and you can change it to your desired port.
 
Another way to setup dozzle is using docker compose. You can make following changes to the docker compose file.


```
version: "3"
services:
  dozzle:
    container_name: dozzle
    image: amir20/dozzle:latest
    volumes:
      - /var/run/docker.sock:/var/run/docker.sock
    ports:
      - 9999:8080
```

Now you can use port 8080 and search the desired container of docker that you want to see your logs.




## REFERENCE LINK
https://dozzle.dev/guide/getting-started



## Knowledge Based

### Problem 1: Port already in use for 8080
In this case you can either use different port when configuring dozzle or you can stop the container running in port 8080
by using these commands. This is for terminating certain process of the system. 

Also, it is very risky so know what you are doing before killing a process.

```
sudo lsof -i:<port_number> //This will view port running in that port number 

sudo kill -9 <PID>  //This will terminate the process running of that PID

Example:
sudo lsof -i:3000
sudo kill -9 2133
```

