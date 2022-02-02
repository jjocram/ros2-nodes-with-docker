# PoC Pub/Sub over a docker network
This repository contains a Proof of Concept of nodes communication through Docker.

The two nodes are a publisher and a subscriber, I followed [this guide](https://docs.ros.org/en/galactic/Tutorials/Writing-A-Simple-Py-Publisher-And-Subscriber.html) to create them but, unlike the guide I create the listener and the talker in two different workspaces.

## Repository structure
- listener_ws
    - src
        - py_sub --> created with `ros2 pkg create --build-type ament_python py_sub` 
    - Dockerfile
    - launch.sh
- publisher_ws
    - src
        - py_pub --> created with `ros2 pkg create --build-type ament_python py_pub` 
    - Dockerfile
    - launch.sh
- docker-compose.yml

Each node has the Python package that takes care of the nodes logic, a Dockerfile that calls `colcon build` to build the node and executes `launch.sh` that get the environmental variables and execute the node.

The `docker-compose.yml` file takes care of building the two containers and connect them through a network. 

