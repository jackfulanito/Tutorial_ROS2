# Como construir un paquete mediante Colcon
---
Para trabajar con ROS2 se debe de primero iniciar un entorno de trabajo, para esto se utiliza la herramienta de Colcon con el fin de ordenar el espacio, pero primero es necesaria la instalación de dicha herramienta mediante.

sudo apt install python3-colcon-common-extensions

Luego mediante comandos se realiza la creación de carpetas que trabajen en dicho entorno hasta crear algo similar a lo siguiete:
.
├── build
├── install
├── log
└── src
    └── examples
        ├── CONTRIBUTING.md
        ├── LICENSE
        ├── rclcpp
        ├── rclpy
        └── README.md

Los comandos necesarios serían

```
mkdir -p ~/ros2_ws/src
cd ~/ros2_ws
```

Un ejemplo de carpeta puede ser:

```
git clone https://github.com/ros2/examples src/examples -b humble
```
>No es necesaria una creación de src si se usará el ejemplo

Luego estando en una terminal de la carpeta ros2_ws se realizar: 

```
colcon build --symlink-install
```

Finalmente, al realizar todo se de hacer el source de la carpeta mediante
```
source install/setup.bash
```

y se puede probar una demo mediante los comandos
```
ros2 run examples_rclcpp_minimal_subscriber subscriber_member_function

ros2 run examples_rclcpp_minimal_publisher publisher_member_function
```

con los cuales se puede iniciar un subscriptor y un publicador.

Realizados todos estos pasos se puede proceder a realizar un nuevo paquete mediante el comando.

```
ros2 pkg create <nombre_paquete>
```

para realizar un seguimiento del paquete realizado existen los comandos
```
echo "source /usr/share/colcon_cd/function/colcon_cd.sh" >> ~/.bashrc
echo "export _colcon_cd_root=/opt/ros/humble/" >> ~/.bashrc
```

Para activar el autocompletado
```
echo "source /usr/share/colcon_argcomplete/hook/colcon-argcomplete.bash" >> ~/.bashrc
```

si no ser requiere de hacer un build a un paquete se puede colocar un archivo COLCON_IGNORE en el directorio y no se indexará

si no se requiere de configurar y hacer tests en paquetes CMake se puede usar 
> --cmake-args -DBUILD_TESTING=0.