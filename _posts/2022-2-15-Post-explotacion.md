---
title: "Post explotación"
author: "Eduardo Rosales Meoño"
date: 2022-2-15 23:22:00 +0800
categories: [Seguridad,Tecnicas]
tags: [Seguridad]

image:
  src: 
  width: 800
  height: 500
  alt: Post explotación
---

## Information gathering

Se trata de recopilar la mayor cantidad de información posible sobre el sistema de destino para que podamos definir una estrategia y un plan de acción que se utilizará en los próximos pasos. Algunas cosas interesantes sobre el sistema de destino pueden ser las siguientes:

• Sistema Operativo del Objetivo y el nivel de parche aplicado

• Características de Hardware del objetivo y determinar si se encuentra ejecutándose sobre una máquina virtual o no.

• Listado de Usuarios registrados en el sistema y cuales se encuentran logueados actualmente.

• Listado de Procesos en Ejecución

• Programas instalados en la maquina objetivo y frecuencia de uso

• Tiempo de Actividad/Inactividad del Sistema objetivo.

• Dependiendo del sistema operativo instalado en el objetivo, verificación de ficheros de configuración en busca de posibles vulnerabilidades para seguir explotando.

• Listado de variables de entorno en el sistema objetivo.

• Obtención de los hashes correspondientes a los passwords de los usuarios del sistema objetivo.c  

• Determinar si se tiene acceso a otras máquinas en el segmento de red y si existen directorios compartidos.

## Privilege Escalation

El informe de privilegios se usa para obtener una cuenta de usuario que tiene todos los privilegios habilitados en el sistema, por lo que tendremos más opciones cuando cambiemos la máquina infectada para que sea controlada por otra máquina, controlar la capa de red y finalmente cortar la red.

## Persistencia

Son técnicas utilizadas por los atacantes para mantener el acceso cuando ingresan al sistema, ya sea reiniciando el sistema sin importar que este infectado , modificando sus credenciales o realizando acciones maliciosas, otras acciones pueden interrumpir la conexión entre el atacante y la víctima.

