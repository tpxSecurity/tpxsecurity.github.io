---
title: "Fundamentos"
author: 
  name: Julio Romo T
  link: https://github.com/TishcaTpx
date: 2021-12-09 23:22:00 +0800
categories: [Seguridad]
tags: [Seguridad]
image:
  src: 
  width: 800
  height: 500
  alt: Fundamentos
---

Antes de introducirnos dentro del mundo de la Ciberseguridad es necesario revisar las especialidades existentes:

* Seguridad en la red e infraestructura
* Seguridad en aplicaciónes Web
* Seguridad en aplicaciones Android
* Análisis Forence
* Detección y Respuesta

Dentro de los temas menciónados anteriormente dentro de esta sección nos enfocaremos especificamente en  **Seguridad en aplicaciónes Web**.
Los conocimientos base para ser un auditor de aplicaciones web pueden llegar a ser bastante aplios, con base a la existencia de multiples lenguajes de programación Backend y Frontend, de igual forma el reconocer las configuraciones posibles o necesarias para el correcto funcionamiento del servico web.

## 2.1.- Funcionamiento de las redes

El primer conocimiento base de un auditor Web o pentester Web se basa en el entendimiento de las redes y como viaja la información atravez de la red. Los conocimientos de ello brinda al pentester un panorama mas amplio de ataque, mejorando la efectividad dentro delas pruebas a realizar.

### 2.1.1.- Funcionamiento de la Red/Modelo OSI

  La meta en el standar modelo OSI fue crear un modelo de referencia que permitiera la comunicación entre diversos dispositivos, tecnologias y brindar compatibilidad.
  Estas capas representan las fases en el establecimiento de cada conexión pensando en como los paquetes seran enviados, el estandar fue creado para rastrear como la conexión fue estructurada y brindarnos visibilidad.

* Capa 1: **Fisica**

    Si alguna vez ha tenido que solucionar problemas electrónicos, la capa 1 es donde respondería la pregunta "¿Está enchufado?" La capa 1 también incluye diseños de pines, voltajes, enlaces de radiofrecuencia y otros requisitos físicos.

* Capa 2: **Enlace de datos**

    La capa de enlace de datos es la responsable de del intercambio de datos entre un host cualquiera, y la red a la que está conectado. Permitiendo una correcta comunicación entre las capas superiores (Red, Transporte y Aplicación) y el medio físico de transporte de datos. Su principal objetivo es la de proveer una comunicación segura entre dos nodos pertenecientes a una misma red o subred, para ello se encarga de la notificación de errores, de la topología de la red y el control del flujo en la transmisión de las tramas.

* Capa 3: **Red**

     La capa 3, alberga direcciones IP y enrutadores que buscan las vías de comunicación más eficientes para los paquetes que contienen información de control y datos de usuario, también conocida como carga útil.

* Capa 4: **Trasporte**

    La capa 4 es una capa de host que generalmente funciona como una oficina postal digital que coordina las transferencias de datos entre sistemas y hosts, incluida la cantidad de datos que se envían, la tasa de transmisión de datos, los destinos de datos y más.

* Capa 5: **Sesión**

    La capa 5 es una capa de host que actúa como un moderador en el sentido de que controla el diálogo entre computadoras, dispositivos o servidores. Establece rutas, límites para el tiempo de espera de respuesta y finaliza sesiones.

* Capa 6: **Presentación**

    Esta capa de host es donde los datos se traducen y formatean para que las aplicaciones, las redes y los dispositivos puedan comprender lo que reciben. Los caracteres se codifican y los datos se comprimen, cifran y descifran en la capa 6.

* Capa 7: **Aplicación**

    Esta capa de host superior es familiar para los usuarios finales porque es el hogar de las interfaces de programación de aplicaciones (API) que permiten compartir recursos, acceder a archivos remotos y más. Es donde encontrará navegadores web y aplicaciones como clientes de correo electrónico y sitios de redes sociales.

### 2.1.2.- ¿Qué es un servicio?

Los servicios son aplicaciónes o funciónes las cuales nos permiten realizar determinadas taread dentro de la red mediante el uso de protocolos. Estos suelen brindar desde el envio de un correo o visualización de una pagina web hasta la administración remota de un equipo. Mostraremos algunos de muchos de los serviciós mas comunes usados en el dia a dia dentro de la red.

Correo electrónico (e-mail). Utiliza el protocolo SMTP ("Simple Mail Transfer Protocol"), para la recepción y envío.

Emulación de terminal TELNET. Se utiliza para conectar a equipos remotos mediante la Red emulando un terminal del equipo al que se realiza la conexión.

Transferencias de ficheros: Utiliza el protocolo FTP ("File Transfer Protocol"), se usa para enviar o recibir ficheros (de cualquier tipo) entre dos equipos conectados a la red.

Servicio de nombres de dominio DNS ("Domain Name Service"). En realidad es un servicio que raramente se utiliza solo;  es usado por otros, como TELNET, FTP, WWW, etc. para conseguir las direcciones IP (numéricas) de las máquinas remotas a partir de los nombres de dominio.

Gopher. Un servicio de información basado en servidores y que sirve de interfaz para otros servicios de información.

WAIS ("Wide Area Information Service"). Como su nombre indica, se trata de otro servicio de información basado en bases de datos de ficheros que permiten su rápida localización.
finger.  Un servicio de identificación de usuarios.

La Web, WWW, W3. Un servicio basado en HTTP (Hyper Text Transfer Protocol), el último y más popular que está fagocitando a muchos de los anteriores.

Sistema de ficheros de red NFS ("Network File System"). Un sistema que permite a equipos físicamente distantes, compartir discos y directorios mediante la técnica denominada RPC ("Remote Procedure Call"), que hace que tales recursos aparezcan como si estuvieran en el propio sistema.

Servicios de Información de Red, NIS ("Network Information Services").  También basados en RPC, permite que varios sistemas puedan compartir una misma base de datos situada en remoto; por ejemplo, varios sistemas pueden compartir bases de datos con el mismo fichero de seguridad (password file), lo que facilita su gestión centralizada.

Servicios "R".  Tales como rlogin, rsh y otros.  Utilizan la idea de acuerdos entre sistemas (hosts trusting), que permite ejecutar comandos y otras órdenes en equipos remotos sin requerir un password.

### 2.1.3.- ¿Qué es un protocolo?

Loas protocolos son una serie de estándares y politcas formales, conformados por procedimientos, restricciones y formatos que permiten el intecambo de paquetes dentro de una red.

Protocolos de la capa 1 - Capa física

* USB: Universal Serial Bus
* Ethernet: Ethernet physical layer
* DSL: Digital subscriber line
* Etherloop: Combinación de Ethernet and DSL
* Infrared: Infrared radiation
* Frame Relay
* SDH: Jerarquía digital síncrona
* SONET: Red óptica sincronizada

Protocolos de la capa 2 - Enlace de datos

* DCAP: Protocolo de acceso del cliente de la conmutación de la transmisión de datos
* FDDI: Interfaz de distribución de datos en fibra
* HDLC: Control de enlace de datos de alto nivel
* LAPD: Protocolo de acceso de enlace para los canales
* PPP: Protocolo punto a punto
* STP (Spanning Tree Protocol): protocolo del árbol esparcido
* VTP VLAN: trunking virtual protocol para LAN virtual
* MPLS: Conmutación multiprotocolo de la etiqueta

Protocolos de la capa 3 - Red

* ARP: Protocolo de resolución de direcciones
* BGP: Protocolo de frontera de entrada
* ICMP: Protocolo de mensaje de control de Internet
* IPv4: Protocolo de internet versión 4
* IPv6: Protocolo de internet versión 6
* IPX: Red interna del intercambio del paquete
* OSPF: Abrir la trayectoria más corta primero
* RARP: Protocolo de resolución de direcciones inverso

Protocolos de la capa 4 - Transporte

* IL: Convertido originalmente como capa de transporte para 9P
* SPX: Intercambio ordenado del paquete
* SCTP: Protocolo de la transmisión del control de la corriente
* TCP: Protocolo del control de la transmisión
* UDP: Protocolo de datagramas de usuario
* iSCSI: Interfaz de sistema de computadora pequeña de Internet iSCSI
* DCCP: Protocolo de control de congestión de datagramas

Protocolos de la capa 5 - Sesión

* NFS: Red de sistema de archivos
* SMB: Bloque del mensaje del servidor
* RPC: Llamada a procedimiento remoto
* SDP: Protocolo directo de sockets
* SMB: Bloque de mensajes del servidor
* SMPP: Mensaje corto punto a punto

Protocolos de la capa 6- Presentación

* TLS: Seguridad de la capa de transporte
* SSL: Capa de conexión segura
* XDR: Extenal data representation
* MIME: Multipurpose Internet Mail Extensions

Protocolos de la capa 7 - Aplicación

* DHCP: Protocolo de configuración dinámica de host
* DNS: Domain Name System
* HTTP: Protocolo de transferencia de hipertexto
* HTTPS: Protocolo de transferencia de hipertexto seguro
* POP3: Protocolo de oficina de correo
* SMTP: protocolo de transferencia simple de correo
* Telnet: Protocolo de telecomunicaciones de red

### 2.1.4.- ¿Cómo viaja tu información por Internet?

Internet es un lugar vasto y en constante cambio, con contenido nuevo que se carga cada minuto. La información que se sube a Internet se puede compartir con millones de personas en cuestión de segundos. Internet se ha convertido en una poderosa herramienta para la comunicación y el intercambio de información, pero ¿cómo funciona?

Internet funciona mediante el uso de servidores para almacenar datos y luego conectarlos a través de redes. Estos servidores están conectados entre sí a través de redes para formar lo que se conoce como la World Wide Web. Para acceder a esta información, necesita un proveedor de servicios de Internet (ISP). Cuando ingresa la URL de un sitio web en su navegador, se conectará a un ISP que transmitirá su solicitud y eventualmente lo conectará al servidor que almacena los datos del sitio web.

## 2.2.- Sistemas operativos y distribuciones

Servicios comunes para las aplicaciones.
Hay muchos sistemas operativos diferentes en uso hoy en día. Los más populares son Microsoft Windows, Apple Mac OS y Linux.

Sitemas operativos mas comunes en el mundo de internet:

* Microsoft Windows Server
  * Core
  * 2008 - 2021
* Servidores Linux/Unix
  * Ubuntu
  * Debian
  * Centos
  * Redhat
  * Solaris Os
* macOS Server

### 2.2.1.- Sistemas Operativos orientados a pruebas de seguridad

Uno de los mas grandes mitos dentro del mundo de la ciberseguridad es "para hackerar se necesita usar Kali Linux" esto se da gracias a la enorme comunidad y la dibulgación en redes sociales. Si bien es cierto que la mayoria de los hackers eticos y pentesters hacen uso de el, a si como de otras distribuciónes. Realmente el uso es por la integración previa de herramientas, sinembargo el sistema raiz a utilizar es linux esto dadas las caracteristicas que este tiene, las cuales permiten tener un gran control del hardware.

Sistemas Operativos dirigidos a pentesting recomendados:

* Kali Linux
* Parrot Os
* Black Arch
* BlackBox
* Caine
* Ninjutsu OS (Windows)

### 2.2.2.- Comandos Básicos de Linux / Shell Scripting

El bash scripting es la habilidad más utilizada por los pentesters, ya que dentro de las auditorías el uso de la automatización suele ser crucial para disminuir en tiempo de análisis.

```console

#!/usr/bin/env bash
#La primera linea hace referencia al shebang de linux que dice que sistema ejecutará
# Ejemplos de shelbang: http://en.wikipedia.org/wiki/Shebang_(Unix)
#Una vez configurado esto todo lo que empice con “#” es un comentario<

# Ejemplo simple de un Hola Mundo!:
echo Hello world! # => Hello world!

# Los comandos se ejecutan uno después de otro al existir un ;
echo 'Primer linea'; echo 'Segunda Linea'
# => Primera Línea
# => Segunda Línea

#Como Declarar variables:
Variable="una cadena"

# La sintaxis importa:
Variable = "Some string" # => regresa un error "Variable: command not found"
# Bash al detectar un espacio entre el nombre y el “=” lo detecta como comando
# este al no existir regresa error
# Igual de la siguiente manera:
Variable= 'Cadena’ # => returns error: "Some string: command not found"
# Bash puede decidir que ‘Cadena’ es un comando interno y genera el error
# por no reconocerlo. (en este caso 'Variable=' está bien ejecutado  pero el uso de 
# comilla simple rompe el comando).

#Uso de variables:
echo $Variable # => Some string
echo "$Variable" # => Some string
echo '$Variable' # => $Variable
# Si se quiere hacer uso de las variables se tiene que hacer uso del símbolo $
# de lo contrario no lo reconoce y el uso de ' hace que las variables no sean reconocidas

# Expansión de parámetros ${ }:
echo ${Variable} # => Some string

#Este es un simple uso de la expansión de parámetros
#El parámetro de expansión obtiene el valor de una variable.
# Esto “expande” o imprime el valor de la variable
#Durante la expansión del tiempo del valor puede ser modificado
# Bajo de estos modificadores se pueden añadir más parámetros de expansión

# Sustitución de cadenas en variables
echo ${Variable/Some/A} # => A string
# Esto intercambia el valor "Some" al valor  "A"


# Substraer una cadena de una variable
Length=7
echo ${Variable:0:Length} # => Some st
# Regresa solo los primeros 7 caracteres del valor
echo ${Variable: -5} # => tring
# regresa los 5  últimos caracteres

#Medir cadena
echo ${#Variable} # => 11

# Expansión indirecta
OtherVariable="Variable"
echo ${!OtherVariable} # => Some String
# Eso puede expandir el valor de otra variable

# Valor por defecto de la variable
echo ${Foo:-"DefaultValueIfFooIsMissingOrEmpty"}
# => DefaultValueIfFooIsMissingOrEmpty
# Esto funciona para nool (Foo=) y para una cadena vacía(Foo=""); caso de 0 (Foo=0) regresa 0.
# Nota: Esto solo cambia el valor por defecto de una variable, pero no cambia el valor de esta


# Declaración de array con n elementos
array0=(one two three four five six)
# Imprimir primer elemento
echo $array0 # => "one"
#Segunda forma
echo ${array0[0]} # => "one"
# Imprimir todos los elementos
echo ${array0[@]} # => "one two three four five six"
# Imprime el número de elementos
echo ${#array0[@]} # => "6"
# Imprime el número de caracteres en el tercer elemento
echo ${#array0[2]} # => "5"
#Imprime dos elementos desde la 4ta posición
echo ${array0[@]:3:2} # => "four five"
#Imprime todos los elementos realizando un salto de línea en cada uno
for i in "${array0[@]}"; do
    echo "$i"
done

# Brace Expansion { }
# Utilizado para genera cadenas arbitrarias
echo {1..10} # => 1 2 3 4 5 6 7 8 9 10
echo {a..z} # => a b c d e f g h i j k l m n o p q r s t u v w x y z
# Esto imprime desde el rango inicial hasta el rango final


#Variables  Built-in:
# Estas son algunas variables de entorno utilizadas frecuentemente
echo "Last program's return value: $?"
echo "Script's PID: $$"
echo "Number of arguments passed to script: $#"
echo "All arguments passed to script: $@"
echo "Script's arguments separated into different variables: $1 $2..."

#Ahora que sabes el uso básico de variables e imprecion ,
#vamos a aprender algunos comandos básicos en bash!

# El comando para saber el directorio en el cual estamos :`pwd`.
# `pwd`  imprime el directorio en el cual estamos trabajando.
#Podemos invocarlo con la siguiente variable built-in `$PWD`.
#Un ejemplo de los comandos:
echo "I'm in $(pwd)" # Ejecuta `pwd` y lo concatena a la salida
echo "I'm in $PWD" # Concatena directamente el valor de PWD

#Si tu terminal está llena de basura
# el comando `clear` limpia la pantalla
# Ctrl-L también funciona para limpiar pantalla

#Leyendo valores de entrada:
echo "What's your name?"
read Name # Note: No es necesario declarar la variable!
echo Hello, $Name!


# Nosotros tenemos la siguiente estructura de if basica:
# Usa el comando “man <test comand>” para ver información de sintaxis
if [ $Name != $USER ]
then
    echo "Your name isn't your username"
else
    echo "Your name is your username"
fi
# Es verdadero si en nombre del usuario no es el mismo al de el usuario logeado

# Nota: Si $Name está vacío pensaríamos  validar de esta forma  :
if [ != $USER ]
#Esto es una sintaxis errónea
#La manera correcta para validar variables vacías dentro de bash:
if [ "$Name" != $USER ] ...
# Otra manera de aplicarlo:
if [ "" != $USER ] ...

# Ejecuciones condicionales
echo "Always executed" || echo "Only executed if first command fails"
# => Always executed
echo "Always executed" && echo "Only executed if first command does NOT fail"
# => Always executed
# => Only executed if first command does NOT fail

# Para usar && y || dentro de estamentos condicionales tenemos que separa con square brackets:
if [ "$Name" == "Steve" ] && [ "$Age" -eq 15 ]
then
    echo "This will run if $Name is Steve AND $Age is 15."
fi

if [ "$Name" == "Daniya" ] || [ "$Name" == "Zach" ]
then
    echo "This will run if $Name is Daniya OR Zach."
fi

#También se puede usar el operador `=~` para testear una cadena con el parámetro Regex:
Email=me@example.com
if [[ "$Email" =~ [a-z]+@[a-z]{2,}\.(com|net|org) ]]
then
    echo "Valid email!"
fi
# Nota: El operador  =~ Solo funciona dentro de [[ ]] square brackets,
#Cada una tiene sutilmente diferencias [ ].
# Ingresa a http://www.gnu.org/software/bash/manual/bashref.html#Conditional-Constructs para saber mas del tema.

#Redefinir comandos con alias `ping` solo envia 5 paquetes.
alias ping='ping -c 5'
# Se puede escapar del comando alias usando el símbolo\
\ping 192.168.1.1
# Imprime todos los alias
alias -p

#Dentro de bash puedes enumerar  los directorios dentro de tu espacio de trabajo.
ls # Lista todos los directorios que contiene  el directorio actual

# Este comando tiene parámetros de control:
ls -l # Imprime todos los archivos en forma de lista
ls -t # Ordena los archivos por última vez de modificación
ls -R # Muestra de manera recursiva todos los directorios

#Los resultados previos de estos comandos pueden ser pasados al siguiente comando
# grep es un comando que nos permite leer un texto e identificar patrones de texto
# Esto nos muestra una lista de todos los archivos con extensión txt
ls -l | grep "\.txt"

# Usa `cat`para imprimir el contenido de los archivos:
cat file.txt
Contents=$(cat file.txt)
# "\n" imprime un  nuevo salto de línea
# Usa `cp` para copiar  documentos o directorios de un lugar a otro
# `cp` cp crea copias a partir de la original,
# la copia no afecta al original
# Nota:si se nombra igual puede sobre escribir al original
cp srcFile.txt clone.txt
cp -r srcDirectory/ dst/ # recursively copy

# Usa el comando `mv` para mover archivos de un lugar a otro
# `mv` es similar `cp`, pero elimina el archivo orien
# `mv` es muy util para renombrar archivos
mv s0urc3.txt dst.txt # sorry, l33t hackers...
#Para navegar un poco sobre nuestra carpeta:
cd ~    # Mover al directorio home
cd      # también nos lleva a home
cd ..   # subir un directorio
# (^^say, from /home/username/Downloads to /home/username)
cd /home/username/Documents   # cambiar a una dirección específica 
cd -    #Regresar al último directorio
# => /home/username/Documents

# Uso de subshells para trabajar entre directorios 
(echo "First, I'm here: $PWD") && (cd someDir; echo "Then, I'm here: $PWD")
pwd # still in first directory

# Usa `mkdir` para crear nuevos directorios
mkdir myNewDir

# Escritura en archivos
echo “Hello world” > output.out #Abre el archivo y sobre escribe
echo “Hello world” >> output.out #Abre el archivo y concatena


# Los ciclos for tienen muchas interpretaciones
# se pueden generar  automáticamente.
for Variable in {1..3}
do
    echo "$Variable"
done
# => 1
# => 2
# => 3
# O de la forma tradicional
for ((a=1; a <= 3; a++))
do
    echo $a
done
# => 1
# => 2
# => 3

# Esto tambien sirve con archivos, los lee y guarda en $Variable
for Variable in file1 file2
do
    cat "$Variable"
done

#Creando algunas funciones
function foo ()
{
    echo "Arguments work just like script arguments: $@"
    echo "And: $1 $2..."
    echo "This is a function"
    return 0
}
# llamando la función `foo` con dos argumentos arg1,arg2:
foo arg1 arg2
# => Arguments work just like script arguments: arg1 arg2
# => And: arg1 arg2...
# => This is a function

# Imprimir n cantidad de líneas de abajo para arriba
tail -n 10 file.txt

#Imprimir n cantidad de líneas de arriba para abajo
head -n 10 file.txt

# `sudo`  el comando para tener permisos de super usuario
NAME1=$(whoami)
NAME2=$(sudo whoami)
echo "Was $NAME1, then became more powerful $NAME2
```

