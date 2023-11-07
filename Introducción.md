# Introducción

ROS 2 o Robot Operating System 2 es la segunda generación del middleware ROS, siendo este una capa intermedia entre el sistema operativo y la aplicación en la que se está desarrollando la aplicación, en especificó ROS está diseñado para sistemas robóticos y tiene la gran ventaja de ser de código abierto con el apoyo de grandes compañías y organizaciones internacionales.

### ROS 2

El middleware de ROS2 a igual que ROS se basa en el grafo computacional, esto quiere decir que ROS y ROS2 se basan en la interacción entre diversos nodos, con una función específica que se comunican entre ellos para realizar un objetivo, para esto se basa en tres tipos de paradigmas: 

- Publicación / Subscripción: Se basa en una comunicación asincrónica en la que N nodos **publican** información en forma de **mensajes** a un **tópico** que alcanza a M nodos se **subscritos**, dicho mensaje no posee ni destinatario ni remitente, por lo que no se conoce quien envió ni quien recibió el mensaje.

- Servicios: Mendiante los servicios se realiza un petición asincrónica en la que un nodo hace una solicitud a otro nodo y espera una respuesta, es por tal motivo que los servicios deben de ser los más rápidos posibles para que no afecte la ejecución del programa.

- Acciones: En esta comunicación asincrónica al igual que en los servicios un nodo realiza una petición a otro nodo, pero esta petición debe de tener un objetivo especifico, que se realizará en un largo periodo de tiempo y se proporcionará feedback durante y finalizando la acción.

En cuanto a los nodos estos en general tienen dos tipos de funcionamiento:

- Ejecución interactiva:  En la que un nodo se ejecuta en un ciclo definido, es decir que mediante una frecuencia de funcionamiento se acciona el programa.

- Ejecución orientada en eventos: Mediante esta un nodo se ejecuta o recibe información en el momento en el que un evento ocurra, dicho evento puede poseer o no un tiempo definido.

Los nodos en ROS realizan el enlace mediante un nodo maestro, el cual organiza cuales son los nodos a comunicar esto es mejorado en ROS2 mediante un control descentralizado basado en una capa de comunicación de Data Distribution Service (DDS) y como centro de ROS 2 se encuentra Ros Client Library (rcl) cuyo código es manejado mediante las librerías rclc y rclpy de de C++ y Python respectivamente, es mediante esta que se generan los códigos de creación de nodos.

En el caso de esta guía básica se utilizará la versión de ROS2 Humble en Ubuntu 22.04.