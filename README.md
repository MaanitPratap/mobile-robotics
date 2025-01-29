# Duckiebot Repository (CSC22905)

This repository contains code and instructions for operating the Duckiebot DB21M robot named `csc22905`.

## Course Website

https://sites.google.com/ualberta.ca/maanitpratap/home

## Robot Specifications

- **Model**: Duckiebot DB21M
- **Robot Name**: csc22905
- **Dashboard**: csc22905.local

## Basic Operations

### Discovery and Connection
```bash
# Discover active Duckiebots on Duckienet wifi
dts fleet discover

# Ping robot to check connection
ping csc22905.local
```

### Robot Control
```bash
# Control robot using keyboard
dts duckiebot keyboard_control csc22905

# Shutdown robot
dts duckiebot shutdown csc22905.local
```

### Calibration
```bash
# Camera intrinsics calibration
dts duckiebot calibrate_intrinsics csc22905

# Camera extrinsics calibration
dts duckiebot calibrate_extrinsics csc22905
```

### Development Tools
```bash
# Start GUI tools
dts start_gui_tools csc22905

# Build locally
dts devel build -f

# Build on robot (ARM architecture)
dts devel build -f --arch arm32v7 -H csc22905.local
```

## Running Demos

### Lane Following Demo
```bash
dts duckiebot demo --demo_name lane_following --duckiebot_name csc22905 --package_name duckietown_demos
```

**Controls:**
- Press 'a' to start demo
- Press 's' to stop demo

## Docker Operations

To run the mobile robotics container:
```bash
docker -H csc22905.local run -it --rm --net=host duckietown/mobile-robotics:v3-arm32v7
```

## Robot Configuration

### Setting Trim Parameter
```bash
rosparam set /csc22905/kinematics_node/trim 0.0916
```

## Exercise 1 Python Code (Hello from My_Robot) location

The Hello from My_Robot code can be found at:
```
packages/my_package/my_script.py
```

## Getting Started

1. Ensure you're connected to the Duckienet wifi network
2. Verify robot connectivity using `ping csc22905.local`
3. Start with basic keyboard control to test robot operation
4. Perform camera calibrations if needed
5. Run demos or custom code as required

## Support

For issues related to:
- Robot hardware: Check the Duckiebot DB21M manual: https://docs.duckietown.com/daffy/opmanual-duckiebot/intro.html
- Software: Refer to the Duckietown documentation: https://docs.duckietown.com/daffy/
