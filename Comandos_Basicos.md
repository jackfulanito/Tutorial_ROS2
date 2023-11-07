# Comandos básicos

comandos de lista de ROS2

```
ros2 node list
ros2 topic list
ros2 service list
ros2 action list
```

Comando de información de ROS2
```
ros2 node info <node_name>
ros2 topic info <node_name>
ros2 service info <node_name>
ros2 action info <node_name>
```

Iniciar un paquete
```
ros2 run <package_name> <executable_name>
```

Hacer un re-mapeo de los nodos 
```
ros2 run turtlesim turtlesim_node --ros-args --remap __node:=my_turtle
```

---

Verificar topicos y a la vez el tipo de mensaje
ros2 topic list -t

Verificar los datos entregados por los topicos
ros2 topic echo <topic_name>

Verificar el tipo de mensaje que envía 
ros2 interface show <msg_type>

Para enviar un mensaje 
```
ros2 topic pub <loop> <topic_name> <msg_type> '<args>'

Opcional se puede usar <--once> para que solo se repita una vez
Opcional se puede usar <--rate 1> para que se repita cada 1Hz

Ejemplo de '<args>' = "{linear: {x: 2.0, y: 0.0, z: 0.0}, angular: {x: 0.0, y: 0.0, z: 1.8}}"
```

Para identificar la periocidad con la que se publica un tópico

ros2 topic hz <topic_name>
---
Para identificar el tipo de servicio se puede usar
ros2 service type <service_name>
##Si se quiere encontrar un tipo especifico de servicio se puede usar
ros2 service find <type_name>	
##Ejemplo de <type_name> = std_srvs/srv/Empty

Para identificar la estructura de un servicio
ros2 interface show <type_name>

Para llamar a un servicio se usa
ros2 service call <service_name> <service_type> <arguments>

---

Para identificar el tipo de parametros
ros2 param get <node_name> <parameter_name>

Para identificar todos los parametro de un nodo
ros2 param dump <node_name>	

Si se desea cambiar los parametros se puede utilizar
ros2 param set <node_name> <parameter_name> <value>

Para cambiar los parametros en el momento se usa
ros2 param set <node_name> <parameter_name> <value>
##Solo se cambian para el uso actual

Para guardar el estado actual de los parametros
ros2 param dump /turtlesim > turtlesim.yaml

Para colocar los parametros desde un archivo
ros2 param load <node_name> <parameter_file>
##Los parametros de lectura solo pueden ser modificados al iniciar

Para iniciar un nodo con los parametros dados
ros2 run <package_name> <executable_name> --ros-args --params-file <file_name>
-------------------------------------------------------------------------------
Las acciones son similares a los servicios pero pueden cancelarce y mantien un monitoreo constante. Tienen un funcionamiento similar al de los publicadores-subscriptores, pues consisten en un goal, un feedback y un resultado. Es para tareas que demoren un tiempo


Para identificar el tipo de acción 
ros2 action list -t
##necesario el contenido entre [...] cuando se quiera llamar a la acción

Para conocer el formato de escritura se utiliza
ros2 interface show [...]
##Su estructura se compone de la siguiente manera
##tipo de dato y nombre del goal
##tipo de dato y nombre del result
##tipo de dato y nombre del feedback

Para enviar una acción se utiliza
ros2 action send_goal <action_name> <action_type> <values>
##con values en formato yaml
##ejemplo: ros2 action send_goal /turtle1/rotate_absolute turtlesim/action/RotateAbsolute "{theta: 1.57}"
##--feedback al final de la linea para que se vaya actualizando en el tiempo




