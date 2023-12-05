
***Start using***

---
**Packages, nodes, topics and interfaces**

Start docker and then do source instructons

By executing this command we will see available packages

```
ros2 pkg list
```
so we would see acailable packages

we also can see available nodes
```
ros2 node list
```
but we need to run node prior:

```
ros2 run demo_nodes_cpp talker
```

and in another terminal:

```
ros2 run demo_nodes_py listener
```

to see info about node
```
ros2 node info /talker
```
here we create 2 notes, which communicate through  "/chatter" topic


to see that:

```
ros2 topic list
ros2 topic info /chatter
```
it is 1 of available communicate interfaces; to see others run:

```
ros2 interface list
```

All that we talked about above we may see in rqt_graph;

it's gui app, so you need to exeute instructions below:

to start container with GUI
run this lines

---

```bash

xhost +local:
docker run -it -e DISPLAY=$DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix -v /home/maly/ros_ws:/ros_ws ros2image 
xhost -local:

```
---

and after, in new terminal

```bash

rqt_graph
```