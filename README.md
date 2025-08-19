# ROS 2 Humble with Python 3.11 (for Isaac Sim 5.0)

## 1. Introduction
This project provides a prebuilt **ROS 2 Humble workspace with Python 3.11 support**.  
It is based on [NVIDIA IsaacSim ROS Workspaces](https://github.com/isaac-sim/IsaacSim-ros_workspaces).  

The original NVIDIA ROS Workspaces has some issues and cannot build successfully in one go. This project fixes those problems and provides a successfully built version, tested locally on:
- **Architecture:** x86_64  
- **OS:** Ubuntu 22.04  
- **ROS Distribution:** Humble  

This repository **hosts the build output only** (no rebuild needed).  
You can directly import it into your Ubuntu 22.04 environment alongside your existing ROS 2 Humble (Python 3.10) installation.



## 2. Usage

We provide a compressed workspace: `ros_py311.tar.gz`.

1.  Unpack it:
    ```bash
    tar -xzvf ros_py311.tar.gz
    sudo mv humble_ws /opt/ros/
    ```
    This keeps it separate from your default ROS 2 Humble setup.

2.  When running IsaacSim 5.0 (which requires Python 3.11):
    Source the workspace in your shell: `source /opt/ros/humble_ws/install/local_setup.bash`
    
    ⚠️ If you use zsh or another shell, pick up accordingly, like `local_setup.zsh`.

3.	In the same shell session, start Isaac Sim. It will now recognize the correct `rclpy` bindings for Python 3.11.

    ⚠️ Don’t forget to also create and use a Python 3.11 virtual environment for your Isaac Sim development.

4. Verification
    To confirm that the workspace works with Python 3.11:
    ```bash
    python3.11
    >>> import rclpy
    ```


## Notes
* Default Ubuntu 22.04 ROS 2 Humble comes with Python 3.10 support.
* This package allows parallel usage of Python 3.10 and 3.11 depending on your project needs.
* Useful especially when working with Isaac Sim 5.0, which strictly requires Python 3.11.