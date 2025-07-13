Guía de Instalación ROS Noetic, adjunta en la wiki [^1] .

```
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'

sudo apt install curl

curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -

sudo apt update

sudo apt install ros-noetic-desktop-full
```

Para sourcear por defecto el setup.bash general

```
echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc
	source ~/.bashrc
```

| Meta Package              | Description                                                                              |
| ------------------------- | ---------------------------------------------------------------------------------------- |
| `ros-jazzy-desktop`       | RViz2, herramientas básicas, librerías cliente (equivalente a `ros-desktop` en ROS 1).   |
| `ros-jazzy-simulation`    | Gazebo Fortress, `gazebo_ros_pkgs`, plugins para simulación.                             |
| `ros-jazzy-perception`    | OpenCV, PCL (nube de puntos), filtros, procesamiento de imágenes.                        |
| `ros-jazzy-visualization` | RViz2, `tf2_tools`, `rqt`, visualización de datos.                                       |
| `ros-jazzy-navigation`    | Nav2, SLAM, mapeo, planificación.                                                        |
| `ros-jazzy-ros-core`      | Solo lo esencial: `rclcpp`, `ament_cmake`, mensajes básicos (sin herramientas gráficas). |

[^1]: https://wiki.ros.org/noetic/Installation/Ubuntu

https://hub.docker.com/r/osrf/ros/tags?name=jazzy-desktop

https://hub.docker.com/_/ros/tags?name=jazzy (ros base)

https://docs.ros.org/en/jazzy/Installation/Alternatives/Ubuntu-Development-Setup.html (ubuntu)

ros 2 jazzy jalisco soporte lts hasta 2029
https://docs.ros.org/en/jazzy/Releases.html