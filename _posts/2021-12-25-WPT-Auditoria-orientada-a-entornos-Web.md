---
title: "7.- Auditoría orientada a entornos web"
author: 
  name: Julio Romo T
  link: https://github.com/TishcaTpx
date: 2021-12-25 23:22:00 +0800
categories: [Seguridad,Web]
tags: [Seguridad,Web]
image:
  src: 
  width: 800
  height: 500
  alt: Auditoría orientada a entornos web
---

## 7.1.- Estándares de desarrollo y sus características

Los estándares de desarrollo web son las pautas que se utilizan para crear sitios web. Estos estándares han sido desarrollados con el tiempo por muchas personas y organizaciones.

Los desarrolladores web pueden usar estos estándares para garantizar que sus sitios web cumplan con las expectativas de los usuarios y visitantes. También se aseguran de que su sitio web sea accesible para todos los usuarios, independientemente de su dispositivo o navegador.

Existe una herramienta de pentesting, llamada Web Developer, que ayuda a medir qué tan bien se desarrolla un sitio web con respecto a los estándares de desarrollo web. Puede ser utilizado tanto por desarrolladores como por diseñadores para verificar si han seguido todas las pautas al desarrollar un sitio web.

### 7.1.1.- API REST

Una API de REST, o API de RESTful, es una interfaz de programación de aplicaciones (API o API web) que se ajustan a los límites de la arquitectura REST y permite la interacción con los servicios web de RESTful. El informático Roy Fielding es el creador de la transferencia de estado representacional (REST).

### 7.1.2.- SOAP

SOAP es un formato de mensaje XML utilizado en interacciones de servicios web. Los mensajes SOAP habitualmente se envían sobre HTTP o JMS, pero se pueden utilizar otros protocolos. El uso de SOAP en un servicio web específico se describe mediante la definición WSDL.

## 7.2.- Explorando los diferentes tipos de servidores y tecnologías

Como se aprendio en el apartado de fundamentos de sistemas operativos existe una variedad muy amplia de tecnologías, las cuales debemos saber identificar y las características que estas tienen al momento de realizar la explotación.
Con el fin de tener un mayor impacto y efectividad antes de comenzar la auditoría es necesario verificar  la información obtenida en el reconocimiento sobre las tecnologías para con ello tener bases solidas sobre las vulnerabilidades más comunes y tener mayor efectividad.

## 7.3.- Alcance y proceso de una auditoría Web

El alcance de una auditoría es subjetivo depende de la forma de negocio o contrato establecido, dado que nosotros como auditores no tenemos el conocimiento de que puede llegar a implicar un daño a la continuidad del negocio. Dado esto por entendio esto el alcance es una negociación entre lo descubierto dentro de la etapa del reconocimiento y la negociación con el cliente.

## 7.4.- Metodologías de seguridad orientadas hacia aplicaciones Web

El proyecto [Web Security Testing Guide (WSTG)](https://owasp.org/www-project-web-security-testing-guide/) produce el principal recurso de pruebas de ciberseguridad para desarrolladores de aplicaciones web y profesionales de la seguridad.

El WSTG es una guía completa para probar la seguridad de las aplicaciones web y los servicios web. Creado por los esfuerzos de colaboración de profesionales de la seguridad cibernética y voluntarios dedicados, el WSTG proporciona un marco de mejores prácticas utilizado por evaluadores de penetración y organizaciones de todo el mundo.

## 7.5.- Fases de una auditoría Web

Los siguientes temas a ver a continuación, son parte de las fases de una auditoría web, así como algunas técnicas y herramientas que pueden ser utilizadas.

### 7.5.1.- Reconocimiento Aplicaciones Web

Durante la fase de recolección de información o mejor conocido como reconocimiento, se basa en la recopilación de información sobre el sistema o infraestructura a auditar. El objetivo es identificar datos desconocidos o no proporcionados por ejemplo:

* Direcciones de IP
* Topología de la red
* Tecnologías utilizadas
* Versiones de librerías
* Dispositivos red y más.

Ahora se mostraran las diferentes técnicas para realizar la recopilación de información:

#### 7.5.1.1- Análisis de subdominios

La enumeración de subdominios es el proceso para encontrar subdominios de un objetivo.
Para realizar este proceso se puede hacer uso de herramientas de internet como [dnsdumpster](https://dnsdumpster.com/), [RapidDNS](https://rapiddns.io/) entre otras.

#### 7.5.1.1.1.- Pasivo

La información se obtiene sin interacción directa con el objetivo mediante el uso de técnicas como búsquedas en Internet, rastreo de redes. Algunas de estas técnicas involucran el uso de buscadores o indexadores de contenido.

[Tecnicas/Herramientas de enumeración de subdominios pasivas](/posts/WPT-Herramientas-de-analisis-de-subdominios/#análisis-pasivo)

#### 7.5.1.1.2.- Certificados SSL

Un SSL (Secure Socket Layer) es un certificado digital que autentica un sitio web y habilita una conexión cifrada.

#### 7.5.1.1.3.- Dns resolution

Es un servicio que apunta el nombre de dominio a la IP del sitio web para que las personas puedan acceder fácilmente al sitio web a través del nombre de dominio registrado. Una dirección IP es una dirección numérica que identifica un sitio en la red. La resolución de dominio es el proceso de convertir nombres de dominio en direcciones IP.

#### 7.5.1.1.4.- Bruteforce

Esta es una técnica en la que uno toma una larga lista de subdominios populares y les agrega su objetivo y, en función de la respuesta, determina si son válidos o no. Esto es similar al ataque de un diccionario.

#### 7.5.1.1.5.- Permutación

Generar listas de subdominios mediante permutaciones (subdominios, bitsquat, guiones, repetición, omisión, reemplazo, transposición, adición, intercambio de vocales), para   comprobar a través de dns resolution si son subdominios válidos.

#### 7.5.1.1.6.- Recursión

Es la realización de diferentes variantes obtenidas de la permutación en la recursión se permite verificar si es correcta la información obtenida.

#### 7.5.1.1.7.- Registros dns

Los registros DNS son varias cadenas de caracteres que se utilizan para indicar acciones a un servidor DNS. Estas letras también se conocen como sintaxis DNS.

#### 7.5.1.1.8.- Análisis de código fuente & Js scraping

Es la depuración de código con el objetivo de encontrar errores y fallas en el código del sistema.
Se utilizan herramientas para examinar los archivos js(javascript) con el fin de obtener información de estos.

#### 7.5.1.1.9.- Técnicas de obtención de ip

Favicon es la imagen de la aplicación la cual si se convierte a md5 obtendremos un código el cual luego se realiza una búsqueda de ip con el md5 obtenido.

### 7.5.1.2.- Técnicas Web

Dentro de la fase de reconocimiento se intenta obtener la mayor parte información orientada a la plataforma a auditar, de lo cual destacan, librerías, software de terceros, frameworks, rutas o endpoints. Con el resultado de ello se procede a identificar vulnerabilidades, con las versiones de software detectadas así como el realizar una serie de pruebas controladas o detección de patrones en variables y rutas.

#### 7.5.1.2.1.- Waf detection

La detección de waf es una de las etapas más importantes antes de inicializar con la detección u explotación dentro de nuestra auditoría. Esto se debe a que la protección del WAF nos podríamos meter en un problema al mandar nuestros payload ya que estos serían bloqueados.

#### 7.5.1.2.2.- Web vuln scan

Al realizar análisis de vulnerabilidades dentro de una plataforma web se basa en la detección de vunerabilidades conocidas o reportadas (CVE), ya sea por vulnerabilidades dentro del framework/librerías utilizadas dentro del desarrollo o las configuraciónes realizadas por los programadores.

Existen también algunas herramientas que nos falicitan estas tareas e incluso logran detectar vulnerabilidades que comunmente los especialistas detectan de manera manual mediante el uso de la técnica [Fuzzing](#75123--fuzzing).

#### 7.5.1.2.3.- Fuzzing

Esta técnica se basa en enviar datos erroneos a formularios, dentro de una aplicación de una forma automatizada o semiautomatizada mediante el uso de diccionarios.
Dentro de estos dicciónarios nos encontramos payloads los cuales incluyen, números, letras, caracteres especiales hasta código para generar una falla o comportamiento inesperado dentro del sistema.

#### 7.5.1.2.4.- CMS scan

CMS son las siglas de Content Management System (Content Management System). un CMS permite crear, organizar, publicar y eliminar contenido de su sitio web.
Se utilizan herramientas para escanear la seguridad de sistemas de gestión de contenido (CMS) de una forma automática y detectar vulnerabilidades, malas configuraciónes e incluso la enumeración de usuario.

#### 7.5.1.2.5.- Directory enumeración

El análisis de directorios/Endpoits es fundamental dentro de la realización de un penstes bajo el entendimiento de que no todo lo que esta dentro de un sistema es completamente visible o se tiene conocimiento de ello, de esta forma descubriendo nuevos caminos a realizar pruebas y fortalecer.

#### 7.5.1.2.6.- Crawler

Los crawlers son programas que exploran páginas web.
Su objetivo principal es rastrear cada enlace de cada sitio web. Luego guarda una copia de todo lo que ve en los archivos. De esta manera, se crea un enlace único para reunir millones de páginas web que se encuentran en Internet y todo el contenido de cada página web.

#### 7.5.1.2.7.- Js análisis

El análisis de JS se basa en una técnica de depuración de código para detectar: fallas lógicas, peticiones e incluso vulnerabilidades. Dentro de estos archivos también podemos detectar Api keys las cuales nos permitan obtener mayor información como Firebase.

#### 7.5.1.2.8.- Cors check

CORS o Cross origin resource sharing es una característica fundamental dentro del desarrollo web, esta característica brinda la capacidad de realizar comunicación entre sistemas. Habilitando el acceso o parcial a la aplicacón, eso se ve reflejado dentro del mundo de las Apis y los permisos de acceso. El detalle de esto es el que pude ser una ventaja así como un gran riesgo.

Un gran ejemplo de ello solia ser un ataque muy famoso en 2008 - 2010 dentro de Facebook el cual era tan simple como mandar una url maliciosa en la cual dentro del codigo js existiera una petición bien formulada, el alcance que esa falla lograba alcanzar, realizaba un account takeover sin que el usuario realizara nada mas que un solo click.

#### 7.5.1.2.9.- Check robots wayback

Wayback machine es un sitio el cual nos permite regresar años e incluso decadas al pasado, permitiendonos visualizar nuestro objetivo, conocerlo y estudiar la estructura, diseño, programación e incluso viejos archivos. Entre ellos visiatar los Robots los cuales nos brinda información de rutas existentes las cuales no deben ser indexadas por un motor de búsqueda.

### 7.5.1.3.- Osint

Antes de realizar un ataque un pentester debe conocer el entorno destino como las características del sistema.
Cuanta más información específica encuentre el pentester, mayores serán las posibilidades de identificar la forma más fácil y rápida de tener éxito, los servicios de exploración pueden incluir huellas de Internet para investigar objetivos, monitorear recursos, monitorear personal, procesos, escanear información de red y servicios públicos de ingeniería social como mesas de ayuda.

#### 7.5.1.3.1.- Domain info(whois,resistant)

Whois se usa a menudo para identificar y encontrar un nombre de dominio específico, también admite la obtención de direcciones IP y sistemas de intranet propietarios. Para obtener un dominio registrado, Whois proporciona información administrativa, como el registro y la información de contacto de la persona u organización que controla el dominio.

#### 7.5.1.3.2.- Metadata

Los **metadatos** son información relacionada a un recurso , esta información puede contener datos como la procedencia del archivo, fecha de creación, fecha de modificación, autor, dimensiones, modelo de cámara , coordenadas GPS entre otros, estos brindan información valiosa sobre un objetivo ya que  permiten identificar patrones de comportamiento, hábitos, software o tecnología utilizada para la generación de documentos o archivos hasta detalles personales.

#### 7.5.1.3.3.- Emails, users, data leaks

Una violación de datos es la transferencia no intencional de datos a partir de en una organización a un destinatario externo. Si bien esta puede provocar pérdidas financieras inmediatas a una organización.

pwndb es una herramienta empleada para la busqeda de credenciales o datos filtrados en el servicio onion.

#### 7.5.1.3.4.- Google dorks

Es una técnica que utiliza la búsqueda avanzada de google para la obtención de agujeros de seguridad en la configuración
o en el codigo  interno de los sitios web.

#### 7.5.1.3.5.- Gihub dorks

Es una técnica muy eficaz debido a que con ella se puede encontrar información confidencial de los repositorios de github.

### 7.5.2.- Explotación Aplicaciones Web

#### 7.5.2.1- SQL Injection

Una inyección SQL es un recurso en el que se puede encontrar información técnica detallada sobre las diferentes variantes de la vulnerabilidad.  
En esta vulnerabilidad, el atacante inyectará la declaración sql maliciosa para comprometer la base de datos o el servidor.

|  |  |
|--|--|
| M | MYSQL |
| S | SQL Server |
| P | PostgreSQL |
| O | Oracle |

#### 7.5.2.2- Autenticación

Es la vulnerabilidad más crítica por acceso a datos confidenciales, el proceso para identificar la elegibilidad del usuario antes de acceder a datos confidenciales.

* Proceso que verifica que un usuario es quien dice ser.
* El proceso de verificar que el usuario puede hacer algo.

Esta vulnerabilidad se crea porque no protege contra ataques de fuerza bruta. Los flujos lógicos o encriptados no válidos, que un atacante pasa por alto se conocen como "validación rota".

* Vulnerabilidad en el inicio de sesión basado en contraseña
* Vulnerabilidad en la autenticación multifactor
* Vulnerabilidad en otro mecanismo de autenticación

#### 7.5.2.3- Divulgación de información

Es la fuga de datos privados o los datos sobre la aplicación o la empresa que no deberían estar disponibles para los usuarios públicos o normales. La información llega a filtrarse cuando no se elimina el contenido interno, mala configuración del sitio web o tecnología utilizada o también el mal diseño y funcionamiento de las aplicaciones.

#### 7.5.2.4- Broken Access Control

Existe una vulnerabilidad de control de acceso roto, si los usuarios realizan o acceden a ciertos recursos que no se encuentra permitido acceder. Cuando un usuario obtiene acceso a alguna funcionalidad a la que no debería poder acceder u obtiene acceso a la funcionalidad de administración, se trata de una escalada vertical de privilegios.

#### 7.5.2.5- IDOR

Se produce cuando una aplicación utiliza la entrada proporcionada por el usuario para acceder a los objetos directamente.  Se asocia comúnmente con la escalada de privilegios horizontal, pero también puede ocurrir en asociación con la escalada de privilegios vertical.

#### 7.5.2.6- Directory Traversal

Esta vulnerabilidad también se conoce como path-traversal que incluye datos de aplicaciones, código, credenciales, archivos sensibles del sistema operativo. Si algunos de estos archivos tienen permiso de escritura, permite al atacante modificar el contenido del archivo y tomar el control total del servidor.

#### 7.5.2.7- Server-side request Forgery (SSRF)

Es una vulnerabilidad de seguridad web que permite a un atacante inducir a la aplicación del lado del servidor a realizar una solicitud HTTP a un dominio arbitrario elegido por el atacante. Provoca que el servidor se conecte al servicio solo interno dentro de la infraestructura de la organización. Podría obligar al servidor a conectarse a un sistema externo arbitrario, para filtrar datos confidenciales, como credenciales de autorización.

El impacto común es el acceso no autorizado a los datos dentro de la organización. En alguna situación, podría permitir que el atacante realice RCE.

#### 7.5.2.8- XXE Injection

También conocido como XXE es una vulnerabilidad de seguridad web que permite a un atacante interferir con el procesamiento de datos XML de una aplicación.  
Permite al atacante ver archivos en el servidor de aplicaciones e interactuar con cualquier sistema de backend al que tenga acceso la propia aplicación.  Algunas veces el atacante aprovecha los ataques XXE a SSRF.

**Tipos de ataque XXE:**

* Explotación XXE para la obtención de archivos: donde una entidad externa determina el contenido del archivo y lo devuelve en la respuesta de la aplicación.
* Explotación XXE para realizar un ataque SSRF: cuando se identifica una entidad externa en función de la URL del sistema back-end.
* Explotación ciega fuera de banda XXE Minería de datos: cuando se transfieren datos confidenciales desde un servidor de aplicaciones a un sistema controlado por un atacante.
* Explotación Blind XXE para recuperar datos a través de mensajes de error: donde un atacante puede desencadenar un mensaje de error de análisis que contiene datos confidenciales.
* Algunas aplicaciones tienen una función para cargar imágenes en svg xml, por lo que también pueden ser vulnerables a ataques XXE, SSRF y XSS.

#### 7.5.2.9- Remote Code Execution

La inyección de comandos del sistema operativo también se conoce como inyección de shell o RCE. Esta es una vulnerabilidad que permite a un atacante ejecutar cualquier comando en el sistema y tomar el control total del servidor.
Un atacante podría explotar una vulnerabilidad de inyección de comandos del sistema operativo para comprometer otras partes de la infraestructura de alojamiento, explotando las relaciones de confianza para apuntar a otros sistemas de la organización.
Esta vulnerabilidad puede presentarse en cualquier parámetro que se pueda proporcionar directamente al shell interno, pero necesitamos un proxy para verificar que puede interactuar con un parámetro oculto o en una solicitud de API.

| purpose               | linux               | windows        |
| --------------------- | ------------------- | -------------- |
| name of current user  | 'whoami'            | 'whoami'       |
| OS                    | 'uname -a'          | 'ver'          |
| Network configuration | 'ifconfig'or'ipaddr | 'ipconfig/all' |
| Network Connection    | 'nestat -an'        | 'netstat -an'  |
| Running Process       | 'ps -ef'            | 'tasklist'     |

#### 7.5.2.10- BUSINESS LOGIC

Las vulnerabilidades de lógica empresarial son flujos que surgen durante el diseño y la implementación de aplicaciones que permiten que un atacante provoque un comportamiento inesperado. Esto podría permitir potencialmente a los atacantes manipular la funcionalidad legítima para lograr objetivos maliciosos. Los errores de lógica a menudo son invisibles para aquellos que no los buscan explícitamente, porque generalmente no están expuestos a través del uso normal de la aplicación.

* Riesgos
Las vulnerabilidades de la lógica de negocio a menudo surgen porque los equipos de diseño y desarrollo hacen suposiciones incorrectas sobre cómo los usuarios interactuarán con la aplicación.. (RESUMIR)
Es posible que los desarrolladores que trabajan en grandes bases de código no tengan un conocimiento profundo de cómo funcionan todas las áreas de una aplicación.

* Impacto
El impacto de las vulnerabilidades de la lógica de negocio depende de la aplicación y de qué lógica o área de la aplicación se rompe.

#### 7.5.2.11 CSRF Cross Site Request For forgery

Es una vulnerabilidad de seguridad web que permite a un atacante inducir a la aplicación del lado del servidor a realizar una solicitud HTTP a un dominio arbitrario elegido por el atacante. Provoca que el servidor se conecte al servicio solo interno dentro de la infraestructura de la organización. Podría obligar al servidor a conectarse a un sistema externo arbitrario, para filtrar datos confidenciales, como credenciales de autorización.

* El impacto común es el acceso no autorizado a los datos dentro de la organización. En alguna situación, podría permitir que el atacante realice RCE.

#### 7.5.2.12 WebSockets

Los sockets web se utilizan para todo tipo de propósitos, incluida la realización user action, Transmitting sensitive. Son ampliamente utilizados en aplicaciones web modernas, se iniciaron a través de HTTP y proporcionan conexiones de larga duración con comunicación asíncrona en ambas direcciones.
Prácticamente cualquier vulnerabilidad de seguridad web que surja con HTTP regular también puede surgir en relación con WebSockets communication.

#### 7.5.2.13- Cross Site Scripting

Es una vulnerabilidad de seguridad web que permite a un atacante comprometer las interacciones de los usuarios con una aplicación vulnerable.

##### Tipos de XSS

* Reflected XSS: Surge cuando una aplicación recibe datos en una solicitud HTTP e incluye datos dentro de la respuesta inmediata de forma insegura.
* Stored XSS: Surgen cuando una aplicación recibe datos de una fuente que no es de confianza e incluye edatos en su respuesta HTTP de una manera no segura.
* DOM-Based XSS: Surge cuando una aplicación contiene JavaScript del lado del cliente que procesa datos de una fuente que no es de confianza de una manera no segura, generalmente escribiendo los datos nuevamente en el DOM.

#### 7.5.2.14- DOM (Document Object Model)

El modelo de objeto de documento es una representación jerárquica de elementos de página de un navegador web. Las páginas web pueden usar JavaScript para manipular nodos y objetos DOM y sus propiedades. La manipulación del DOM en sí misma no es un problema. De hecho, es una parte integral de cómo funcionan los sitios web modernos. Sin embargo, JavaScript maneja datos inseguros que pueden desencadenar una variedad de ataques. Las vulnerabilidades basadas en DOM surgen cuando una página web que contiene JavaScript toma un valor controlable por el atacante, llamado fuente, y lo pasa a una función maliciosa, llamada sink.

#### 7.5.2.15- Click jacking

El Clickjacking, también conocido como "ataque de reparación de la interfaz de usuario", ocurre cuando un atacante usa múltiples capas de transparencias o no transparentes para engañar al usuario para que haga clic en un botón o enlace en otra página cuando tiene la intención de hacer clic en la página de nivel superior. De este modo, el atacante "secuestra" los clics destinados a su sitio y los dirige a otra página, probablemente propiedad de otra aplicación, otro dominio o ambos. Usando una técnica similar, los ataques también pueden ser desviados. Con una cuidadosa combinación de hojas de estilo, iframes y cuadros de texto, se puede engañar a los usuarios haciéndoles creer que están ingresando su dirección de correo electrónico o la contraseña de su cuenta bancaria, pero en cambio, golpean un marco invisible controlado por el atacante.

#### 7.5.2.16- CORS

La compartición de recursos de origen cruzado es un mecanismo del navegador, que permite el acceso controlado a recursos situados fuera de un determinado dominio.
Amplía y añade flexibilidad a la política del mismo origen (SOP). También proporciona un potencial para los ataques basados en dominios cruzados. Si la política de cors de los sitios web está mal configurada o implementada, no protege contra los ataques de origen cruzado como CSRF.

#### 7.5.2.17- O-Auth

La serialización es el proceso de convertir una estructura de datos compleja, como los objetos y su campo, aun formato más plano que pueda ser enviado y recibido como un flujo secuencial de bytes. Enviar datos complejos, por ejemplo, a través de una red, entre diferentes componentes de una aplicación, o en una llamada a la API. Cuando se serializa un objeto también se persiste su estado, en otras palabras, los atributos del objeto se conservan junto con sus valores asignados.

#### 7.5.2.18- Insecure Deserealization

Muchos ataques de deserialización se completan antes de que la deserialización haya terminado. Esto significa que el propio proceso de deserialización puede iniciar el ataque, incluso si la propia funcionalidad de la aplicación no interactúa directamente con el objeto malicioso.
El impacto de una deserealizacion insegura puede ser grave, ya que proporciona un punto de entrada a una superficie de ataque enormemente aumentada. Permite a los atacantes reutilizar el código de la aplicación existente de manera perjudicial, lo que genera muchas otras vulnerabilidades, a menudo RCE (Ejecución remota de código).

#### 7.5.2.19- HTTP Request Smuggling

El contrabando de solicitudes HTTP es una técnica para interferir con la forma en que un sitio web procesa la secuencia de solicitudes HTTP que se reciben de uno o más usuarios.
Esta vulnerabilidad es de naturaleza crítica, lo que permite a un atacante eludir los controles de seguridad, obtener acceso no autorizado a datos confidenciales y comprometer directamente otra aplicación.

#### 7.5.2.20- Web Cache Poisoning

El envenenamiento de la caché web es una técnica avanzada en la que un atacante explota el comportamiento del servidor web y para enviar una respuesta HTTP maliciosa a otros usuarios.  
En primer lugar, un atacante debe descubrir cómo obtener una respuesta de backend, sin darse cuenta, contiene algún tipo de carga útil maliciosa.  
Una vez que el primer paso es exitoso, deben asegurarse de que su respuesta se almacene en caché y luego se entregue a la víctima prevista.  
El caché web infectado puede ser una forma devastadora de lanzar una variedad de ataques que explotan vulnerabilidades como XSS, inyección de JavaScript, redireccionamientos abiertos y más.

#### 7.5.2.21- Server Side Template Injection

SSTI ocurre cuando un atacante puede usar la sintaxis nativa del modelo para inyectar una carga útil maliciosa en un modelo, que se ejecuta en el lado del servidor.
Ocurre cuando la entrada del usuario se concatena directamente en una plantilla, en lugar de pasarla como datos, lo que permite que un atacante introduzca directivas de plantilla arbitrarias para manipular el motor de plantilla, lo que a menudo les permite tener un control total sobre el servidor. El impacto de SSTI expone a los sitios web a varios ataques dependiendo del motor de plantilla, en algunos casos esta vulnerabilidad no representa un riesgo de seguridad real, pero la mayor parte del impacto de SSTI es muy catastrófico en la fase crítica de la escala un atacante puede llegar al RCE, tomar el control total del servidor. En el caso de que la ejecución remota de código no sea posible, el atacante puede usar un servidor modelo en paralelo como base para muchos otros ataques, obteniendo potencialmente acceso de lectura a datos confidenciales y archivos arbitrarios en el servidor.

#### 7.5.2.22- Web Cache Poisoning

El envenenamiento de la caché web es una técnica avanzada en la que un atacante explota el comportamiento del servidor web y para enviar una respuesta HTTP maliciosa a otros usuarios.  
En primer lugar, un atacante debe descubrir cómo obtener una respuesta de backend, sin darse cuenta, contiene algún tipo de carga útil maliciosa.  
Una vez que el primer paso es exitoso, deben asegurarse de que su respuesta se almacene en caché y luego se entregue a la víctima prevista.  
El caché web infectado puede ser una forma devastadora de lanzar una variedad de ataques que explotan vulnerabilidades como XSS, inyección de JavaScript, redireccionamientos abiertos y más.

#### 7.5.2.23- Attacking GraphQL

SSTI ocurre cuando un atacante puede usar la sintaxis nativa del modelo para inyectar una carga útil maliciosa en un modelo, que se ejecuta en el lado del servidor.
Ocurre cuando la entrada del usuario se concatena directamente en una plantilla, en lugar de pasarla como datos, lo que permite que un atacante introduzca directivas de plantilla arbitrarias para manipular el motor de plantilla, lo que a menudo les permite tener un control total sobre el servidor. El impacto de SSTI expone a los sitios web a varios ataques dependiendo del motor de plantilla, en algunos casos esta vulnerabilidad no representa un riesgo de seguridad real, pero la mayor parte del impacto de SSTI es muy catastrófico en la fase crítica de la escala un atacante puede llegar al RCE, tomar el control total del servidor. En el caso de que la ejecución remota de código no sea posible, el atacante puede usar un servidor modelo en paralelo como base para muchos otros ataques, obteniendo potencialmente acceso de lectura a datos confidenciales y archivos arbitrarios en el servidor.

### 7.5.3- Post Explotación Aplicaciones Web

#### Information gathering

Se trata de recopilar la mayor cantidad de información posible sobre el sistema de destino para que podamos definir una estrategia y un plan de acción que se utilizará en los próximos pasos. Algunas cosas interesantes sobre el sistema de destino pueden ser las siguientes:

• Sistema Operativo del Objetivo y el nivel de parche aplicado

• Características de Hardware del objetivo y determinar si se encuentra ejecutándose sobre una máquina virtual o no.

• Listado de Usuarios registrados en el sistema y cuales se encuentran logueados actualmente.

• Listado de Procesos en Ejecución

• Programas instalados en la maquina objetivo y frecuencia de uso

• Tiempo de Actividad/Inactividad del Sistema objetivo.

• Dependiendo del sistema operativo instalado en el objetivo, verificación de ficheros de configuración en busca de posibles vulnerabilidades para seguir explotando.

• Listado de variables de entorno en el sistema.

• Obtención de los hashes correspondientes a los passwords de los usuarios del sistema.  

• Determinar si se tiene acceso a otras máquinas en el segmento de red y si existen directorios compartidos.

##### Privilege Escalation

El informe de privilegios se usa para obtener una cuenta de usuario que tiene todos los privilegios habilitados en el sistema, por lo que tendremos más opciones cuando cambiemos la máquina infectada para que sea controlada por otra máquina, controlar la capa de red y finalmente cortar la red.

#### Persistencia

Son técnicas utilizadas por los atacantes para mantener el acceso cuando ingresan al sistema, ya sea reiniciando el sistema sin importar que este infectado , modificando sus credenciales o realizando acciones maliciosas, otras acciones pueden interrumpir la conexión entre el atacante y la víctima.
