---
layout: page
title: ROS 2
permalink: /ros2-cheatsheet/
description: Cheatsheet of useful commands to use in ROS 2.
---

**Table of Contents**

* TOC
{:toc}

## Build & Workspace
- Install package dependencies (run from workspace root):
```bash
rosdep install --from-paths src -y --ignore-src
```
- Build the workspace (run from workspace root):
```bash
colcon build (--packages-select <package_names>: build only these packages) (--symlink-install: no rebuild needed after editing Python/launch files)
```
- Source the workspace (in every new terminal):
```bash
source install/setup.bash
```
- Run tests and view results:
```bash
colcon test (--packages-select <package_names>: test only these packages)
colcon test-result (--verbose: show failing tests)
```

## Execution
- Run executables:
```bash
ros2 run <package_name> <executable_name>
```
- Launching multiple nodes:
```bash
ros2 launch <package_name> <launch_file_name> (<arg_name>:=<value>: set launch argument) (--show-args: list available arguments)
```
- Remap topics, node name or namespace:
```bash
ros2 run <package_name> <executable_name> --ros-args -r <old_topic>:=<new_topic> (-r __node:=<node_name>: rename node) (-r __ns:=/<namespace>: set namespace)
```
- Set a parameter on startup:
```bash
ros2 run <package_name> <executable_name> --ros-args -p <parameter_name>:=<value>
```
- Set logging level:
```bash
ros2 run <package_name> <executable_name> --ros-args --log-level <debug | info | warn | error | fatal>
```

## Interfaces
- List available message/service/action types:
```bash
ros2 interface list (-m: messages only) (-s: services only) (-a: actions only)
```

## Nodes
- List all nodes:
```bash
ros2 node list
```
- Access more info:
```bash
ros2 node info <node_name>
```

## Topics
- List active topics:
```bash
ros2 topic list (-t: show topic types)
```
- View data being published by a topic:
```bash
ros2 topic echo <topic_name>
```
- View publisher/subscriber count:
```bash
ros2 topic info <topic_name> (-v: verbose details)
```
- View message definition:
```bash
ros2 interface show <msg_type>
```
- Publish data to a topic:
```bash
ros2 topic pub <topic_name> <msg_type> '<args>'     # use auto-complete!
```
- View data rate of publishing:
```bash
ros2 topic hz <topic_name>
```
- View bandwidth utilization of a topic:
```bash
ros2 topic bw <topic_name>
```
- List available topics of a specific type:
```bash
ros2 topic find <topic_type>
```

## Services
- List active services:
```bash
ros2 service list (-t: show type)
```
- View service type:
```bash
ros2 service type <service_name>
```
- View information about a particular service:
```bash
ros2 service info (-v: more details) <service_name>
```
- Find services of a specific type:
```bash
ros2 service find <type_name>
```
- View arguments of call/response of a service type:
```bash
ros2 interface show <type_name>
```
- Call service from command line:
```bash
ros2 service call <service_name> <service_type> <arguments> # use auto-complete!
```
- Monitor communication between service client and service server:
```bash
ros2 service echo <service name | service_type> <arguments>
```

## Parameters
- View list of parameters:
```bash
ros2 param list
```
- Identify type and value of parameter:
```bash
ros2 param get (<node_name>: omit when querying all nodes) <parameter_name>
```
- Change paramete value at runtime:
```bash
ros2 param set <node_name> <parameter_name> <value>
```
- Save parameters of node to file:
```bash
ros2 param dump <node_name> >file.yaml
```
- Load node parameters from file:
```bash
ros2 param load <node_name> <parameter_file>
```
- Load parameter file on node startup:
```bash
ros2 run <package_name> <executable_name> --ros-args --params-file <file_name>
```

## Actions
- List all actions of a node:
```bash
ros2 node info <node_name>
```
- Identify all actions in the ROS graph:
```bash
ros2 action list (-t: include type)
```
- List the type of an action:
```bash
ros2 action type <action_name>
```
- View details of an action:
```bash
ros2 action info <action_name>
```
- View the structure of the action type:
```bash
ros2 interface show <action_type>
```
- Send an action goal from the command line:
```bash
ros2 action send_goal <action_name> <action_type> <values>
```
- View communication between action client and action server:
```bash
ros2 action echo <action_name> <optional arguments | action_type>
```

## Bags
- Record topics to a bag:
```bash
ros2 bag record <topic_names> (-a: record all topics) (-o <bag_name>: set output name)
```
- View information about a bag:
```bash
ros2 bag info <bag_name>
```
- Replay a bag:
```bash
ros2 bag play <bag_name> (-l: loop) (-r <rate>: playback speed factor)
```

## Debugging
- Check ROS 2 setup for issues:
```bash
ros2 doctor (--report: full report of system, network and distro info)
```