## environment
---
```
   PLATFORM INFORMATION
system           : Linux
platform info    : Linux-6.8.0-58-generic-x86_64-with-glibc2.35
release          : 6.8.0-58-generic
processor        : x86_64

   RMW MIDDLEWARE
middleware name    : rmw_fastrtps_cpp

   ROS 2 INFORMATION
distribution name      : humble
distribution type      : ros2
distribution status    : active
release platforms      : {'rhel': ['8'], 'ubuntu': ['jammy']}

```

## install
---
make sure ros2 installed properly
```
ros2 run turtlesim turtlesim_node
ros2 run demo_nodes_cpp talker
```

make sure gazebo classic (not gazebo ignition) installed properly
```
gazebo --version
gazebo --verbose /usr/share/gazebo-11/worlds/empty.world
```
if not install
```
sudo apt install gazebo libgazebo-dev
```

## misc
```
error: W: An error occurred during the signature verification. The repository is not updated and the previous index files will be used. GPG error: http://packages.ros.org/ros2/ubuntu jammy InRelease: The following signatures were invalid: EXPKEYSIG F42ED6FBAB17C654 Open Robotics <info@osrfoundation.org> W: Failed to fetch http://packages.ros.org/ros2/ubuntu/dists/jammy/InRelease The following signatures were invalid: EXPKEYSIG F42ED6FBAB17C654 Open Robotics <info@osrfoundation.org> W: Some index files failed to download. They have been ignored, or old ones used instead.

update ros2 key:
sudo mkdir -p /etc/apt/keyrings

curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.key \
  | sudo tee /etc/apt/keyrings/ros-archive-keyring.gpg > /dev/null

echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/ros-archive-keyring.gpg] \
http://packages.ros.org/ros2/ubuntu $(. /etc/os-release && echo "$UBUNTU_CODENAME") main" | \
sudo tee /etc/apt/sources.list.d/ros2.list > /dev/null

sudo rm -f /etc/apt/sources.list.d/ros2-latest.list
sudo apt-key del F42ED6FBAB17C654 || true

sudo apt update
```

## reference
```
https://www.youtube.com/watch?v=KEObIB7RbH0
https://drive.google.com/drive/folders/1JJHC59IyypIF9JXdzzF1K_zQiq_fo0Dv
```