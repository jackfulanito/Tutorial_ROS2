# Crear un paquete

---

Un paquete en ros2 puede contener tanto una configuración para c++ o para python y utiliza a ament como como constructor del sistema y a colcon como herramienta de construcción.
Una carpeta comun que contenga programas en python y c++ se vería de la siguiente forma.

workspace_folder/
  |_src/
     |_cpp_package_1/
     |   |_CMakeLists.txt
     |   |_include/cpp_package_1/
     |   |_package.xml
     |   |_src/
     |
     |_py_package_1/
     |   |_package.xml
     |   |_resource/py_package_1
     |   |_setup.cfg
     |   |_setup.py
     |   |_py_package_1/
     | ...
     |_cpp_package_n/
        |_CMakeLists.txt
        |_include/cpp_package_n/
        |_package.xml
        |_src/
        
Para esto se realiza los siguiente comandos:

Para C++:

```
ros2 pkg create --build-type ament_cmake <package_name>
```

Para python

```
ros2 pkg create --build-type ament_python <package_name>
```

mediante el comando --node-name se puede crear un simple hello world

luego se debe de hacer una actualización mediante
```
colcon build --packages-select my_package
```

con este comando se puede actualizar solo el creado y no todo el espacio de trabajo

finalmente se debe de hacer un source general y luego un source del overlay para correr el código de ejemplo lo que se puede ver en el ejemplo2.

```
source /opt/ros/humble/setup.bash

source install/local_setup.bash
```

![[EJEMPLO2.png]]

