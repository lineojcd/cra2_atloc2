# cra2_atloc2
Duckietown CRA2 AprilTag localization

Instructions to reproduce results

### 1. Clone this repository and go to its directory
```bash
git clone https://github.com/lineojcd/cra2_atloc2.git
cd cra2_atloc2
```
### 2. Build docker image in Duckiebot
```bash
dts devel build -f --arch arm32v7 -H [ROBOT_NAME].local 
```

### 3. Run docker image in Duckiebot with the following options
```bash
docker -H [ROBOT_NAME].local run -it -v /data/config/calibrations/:/code/catkin_ws/src/cra2_atloc2/calibrations/ --rm --net=host --privileged duckietown/cra2_atloc2:latest-arm32v7
```

### 4. Run the keyboard container to control the duckiebot.
```bash
dts duckiebot keyboard_control [ROBOT_NAME]
```

### 5. Check the TF inside of RVIZ
```bash
dts start_gui_tools jcdgo
rviz
```
Add TF and compressedImage inside of RVIZ, then set at_baselink as the fixed frame. 
