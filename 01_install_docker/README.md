
***Small guide how to install and use ubuntu docker-image***

First install docker uduntu image

```
sudo docker run -ti ubuntu:20.04 /bin/bash

```
this command will pull ubuntu 20.04 and run it in container

then inside container run this commands

```
apt update
apt upgrade
apt install iputils-ping

```
then check your connection

```
ping 8.8.8.8
```
if everything is correct you will see soemthing like this:

```
64 bytes from 8.8.8.8: icmp_seq=1 ttl=57 time=125 ms
64 bytes from 8.8.8.8: icmp_seq=2 ttl=57 time=43.8 ms
```

then we want to save our container's state:
run:

```
docker ps
```

you will see info about your containers, that looks like:
```
CONTAINER ID   IMAGE       COMMAND       CREATED         STATUS         PORTS     NAMES
ee613373c08c   testimage   "/bin/bash"   7 minutes ago   Up 7 minutes             admiring_bose

```

then type in terminal:

```
docker commit ee613373c08c testimage
```

upper commands will save your containers state and if you in future install some packages and commit changes:

```
sudo docker run -ti testimage /bin/bash
```

all packages will be availabele inside container

---
---
next feature let you run multiple terminals from only container

in 1st terminal run:

```
sudo docker run -ti testimage /bin/bash
```

in 2nd termianal run
```
sudo docker exec -it <constainer_id> bash 
```