
***Crete workspace***

First create in your home directory, where all your projects will be placed:

Then let's moint this workspace to docker container

```
docker run -it --rm -v /home/username/ros_ws:/ros_ws rosimage /bin/bash
```

In future all files and changes, in you native -ws will als be available in container ws

---
this will let us edit code natively and run it on container

---