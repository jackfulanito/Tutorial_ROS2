# Introducción

ROS 2 o Robot Operating System 2 es la segunda generación del middleware ROS, siendo este una capa intermedia entre el sistema operativo y la aplicación en la que se está desarrollando la aplicación, en especificó ROS está diseñado para sistemas robóticos y tiene la gran ventaja de ser de código abierto con el apoyo de grandes compañías y organizaciones internacionales.

### ROS 2

El middleware de ROS2 a igual que ROS se basa en el grafo computacional, esto quiere decir que ROS y ROS2 se basan en la interacción entre diversos nodos, con una función específica que se comunican entre ellos para realizar un objetivo, para esto se basa en tres tipos de paradigmas:

 - Publicación / Subscripción: Se basa en una comunicación asincrónica en la que N nodos **publican** información en forma de **mensajes** a un **tópico** que alcanza a M nodos se **subscritos**, dicho mensaje no posee ni destinatario ni 