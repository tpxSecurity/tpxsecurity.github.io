---
title: "Explotación"
author: "Julio Alberto Romo T"
date: 2022-2-03 23:22:00 +0800
categories: [Seguridad]
tags: [Seguridad]

image:
  src: /assets/img/posts/recon.svg
  width: 800
  height: 500
  alt: Fase de Reconocimiento
---

## EXPLOTACIÓN

### SQL

Una inyección SQL es un recurso en el que se puede encontrar información técnica detallada sobre las diferentes variantes de la vulnerabilidad. 
En esta vulnerabilidad, el atacante inyectará la declaración sql maliciosa para comprometer la base de datos o el servidor.

|     |            |
| --- | ---------- |
| M   | MYSQL      |
| S   | SQL Server |
| P   | PostgreSQL |
| O   | Oracle     |

### Autenticacion

Es la vulnerabilidad más crítica por acceso a datos confidenciales, el proceso para identificar la elegibilidad del usuario antes de acceder a datos confidenciales.

- Proceso que verifica que un usuario es quien dice ser.
- El proceso de verificar que el usuario puede hacer algo.

Esta vulnerabilidad se crea porque no protege contra ataques de fuerza bruta. Los flujos lógicos o encriptados no válidos, que un atacante pasa por alto se conocen como "validación rota".

- Vulnerabilidad en el inicio de sesión basado en contraseña
- Vulnerabilidad en la autenticación multifactor
- Vulnerabilidad en otro mecanismo de autenticación

***Autenticación multifactor***
**Omisión 2FA**
si algún brinda la contraseña, que se le solicitó el código de verificación a través de una página diferente. El usuario está efectivamente en estado de "inicio de sesión" antes de haber ingresado el código de verificación, se podría omitir las páginas de "solo inicio de sesión" y el sistema no verifica si completamos el segundo paso o no.

**Lógica de verificación fluida 2F**
El flujo es después de completar el paso de inicio de sesión inicial, el usuario no verifica que el mismo  haya completado la segunda etapa.
Se inicia  sesión con las credenciales y al solicitar el código de verificación,  se cambia el usuario con otra identificación de usuario, y eso es manipulable.
En algún casos se utiliza n fuerza bruta para el código de verificación, pero no es necesaria ninguna contraseña para el usuario víctima.

**Lógica rota 2FA**
inicie sesión con credenciales válidas,si la solicitud contiene un campo para verificar el nombre de usuario en la cookie. reenvie esa solicitud con el nombre de usuario de la víctima para que generemos un código de verificación para la víctima en el servidor.
Depues inicie sesión con las credenciales y cuando ingrese a OTP, cambie la cookie de verificación a OTP de víctima y fuerza bruta y obtendra su cuenta sin su contraseña.

## Divulgación de información

Es la fuga de datos privados o los datos sobre la aplicación o la empresa que no deberían estar disponibles para los usuarios públicos o normales. La información llega a filtrarse cuando no se elimina el contenido interno, mala configuración del sitio web o tecnología utilizada o también el mal diseño y funcionamiento de las aplicaciones.

Ejemplos:

- Mostrar los nombres, la estructura y el contenido de los directorios ocultos a través de archivos robots.txt o listas de directorios.
- Brindar el acceso a archivos de código fuente a través de copias de seguridad temporales.
- Revelar explícitamente el nombre de la columna o la tabla de la base de datos en el mensaje de error.
- Divulgación de información altamente sensible. es decir, número de tarjeta de crédito.
- Codificación de claves API, credenciales de bases de datos, etc. en el código fuente.

¿Cómo probar la divulgación de información?

- Fuzzing
- Burp Scanner

## Broken Access Control

Existe una vulnerabilidad de control de acceso roto, si los usuarios realizan o acceden a ciertos recursos que no se encuentra permitido acceder. Cuando un usuario obtiene acceso a alguna funcionalidad a la que no debería poder acceder u obtiene acceso a la funcionalidad de administración, se trata de una escalada vertical de privilegios.

## IDOR

Se produce cuando una aplicación utiliza la entrada proporcionada por el usuario para acceder a los objetos directamente.  Se asocia comúnmente con la escalada de privilegios horizontal, pero también puede ocurrir en asociación con la escalada de privilegios vertical.

## Directory Traversal

Esta vulnerabilidad también se conoce como path-traversal que incluye datos de aplicaciones, código, credenciales, archivos sensibles del sistema operativo. Si algunos de estos archivos tienen permiso de escritura, permite al atacante modificar el contenido del archivo y tomar el control total del servidor.

## Server-side request Forgery(ssrf)

Es una vulnerabilidad de seguridad web que permite a un atacante inducir a la aplicación del lado del servidor a realizar una solicitud HTTP a un dominio arbitrario elegido por el atacante. Provoca que el servidor se conecte al servicio solo interno dentro de la infraestructura de la organización. Podría obligar al servidor a conectarse a un sistema externo arbitrario, para filtrar datos confidenciales, como credenciales de autorización.

- El impacto común es el acceso no autorizado a los datos dentro de la organización. En alguna situación, podría permitir que el atacante realice RCE.

## XXE Injection

También conocido como XXE es una vulnerabilidad de seguridad web que permite a un atacante interferir con el procesamiento de datos XML de una aplicación.  
Permite al atacante ver archivos en el servidor de aplicaciones e interactuar con cualquier sistema de backend al que tenga acceso la propia aplicación.  Algunas veces el atacante aprovecha los ataques XXE a SSRF.

**Tipos de ataque XXE:**

- Explotación XXE para la obtención de archivos: donde una entidad externa determina el contenido del archivo y lo devuelve en la respuesta de la aplicación.
- Explotación XXE para realizar un ataque SSRF: cuando se identifica una entidad externa en función de la URL del sistema back-end.
- Explotación ciega fuera de banda XXE Minería de datos: cuando se transfieren datos confidenciales desde un servidor de aplicaciones a un sistema controlado por un atacante.
- Explotación Blind XXE para recuperar datos a través de mensajes de error: donde un atacante puede desencadenar un mensaje de error de análisis que contiene datos confidenciales.
- Algunas aplicaciones tienen una función para cargar imágenes en svg xml, por lo que también pueden ser vulnerables a ataques XXE, SSRF y XSS.

## RCE

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

## BUSINESS LOGIC

Las vulnerabilidades de lógica empresarial son flujos que surgen durante el diseño y la implementación de aplicaciones que permiten que un atacante provoque un comportamiento inesperado. Esto podría permitir potencialmente a los atacantes manipular la funcionalidad legítima para lograr objetivos maliciosos. Los errores de lógica a menudo son invisibles para aquellos que no los buscan explícitamente, porque generalmente no están expuestos a través del uso normal de la aplicación.

- Riesgos
Las vulnerabilidades de la lógica de negocio a menudo surgen porque los equipos de diseño y desarrollo hacen suposiciones incorrectas sobre cómo los usuarios interactuarán con la aplicación.. (RESUMIR)
Es posible que los desarrolladores que trabajan en grandes bases de código no tengan un conocimiento profundo de cómo funcionan todas las áreas de una aplicación.

- Impacto
El impacto de las vulnerabilidades de la lógica de negocio depende de la aplicación y de qué lógica o área de la aplicación se rompe.

## CSRF Cross Site Request For forgery

Es una vulnerabilidad de seguridad web que permite a un atacante inducir a los usuarios a realizar acciones que no tienen intención de realizar. Permite a un atacante eludir parcialmente la política de origen.  
  
- Impacto  
En un ataque CSRF exitoso, el atacante hace que el usuario víctima realice una acción de forma no intencionada.  Si el usuario víctima es administrador, el atacante puede tomar el control total de todos los datos y funcionalidades de la aplicación.

## WebSockets

Los sockets web se utilizan para todo tipo de propósitos, incluida la realización user action, Transmitting sensitive. Son ampliamente utilizados en aplicaciones web modernas, se iniciaron a través de HTTP y proporcionan conexiones de larga duración con comunicación asíncrona en ambas direcciones.
Prácticamente cualquier vulnerabilidad de seguridad web que surja con HTTP regular también puede surgir en relación con WebSockets communication.

## Cross Site Scripting

Es una vulnerabilidad de seguridad web que permite a un atacante comprometer las interacciones de los usuarios con una aplicación vulnerable.

**Tipos de XSS**

- Reflected XSS: Surge cuando una aplicación recibe datos en una solicitud HTTP e incluye datos dentro de la respuesta inmediata de forma insegura.
- Stored XSS: Surgen cuando una aplicación recibe datos de una fuente que no es de confianza e incluye edatos en su respuesta HTTP de una manera no segura.
- DOM-Based XSS: Surge cuando una aplicación contiene JavaScript del lado del cliente que procesa datos de una fuente que no es de confianza de una manera no segura, generalmente escribiendo los datos nuevamente en el DOM.

## DOM (Document Object Model)

El modelo de objeto de documento es una representación jerárquica de elementos de página de un navegador web. Las páginas web pueden usar JavaScript para manipular nodos y objetos DOM y sus propiedades. La manipulación del DOM en sí misma no es un problema. De hecho, es una parte integral de cómo funcionan los sitios web modernos. Sin embargo, JavaScript maneja datos inseguros que pueden desencadenar una variedad de ataques. Las vulnerabilidades basadas en DOM surgen cuando una página web que contiene JavaScript toma un valor controlable por el atacante, llamado fuente, y lo pasa a una función maliciosa, llamada sink.

## Click jacking

El Clickjacking, también conocido como "ataque de reparación de la interfaz de usuario", ocurre cuando un atacante usa múltiples capas de transparencias o no transparentes para engañar al usuario para que haga clic en un botón o enlace en otra página cuando tiene la intención de hacer clic en la página de nivel superior. De este modo, el atacante "secuestra" los clics destinados a su sitio y los dirige a otra página, probablemente propiedad de otra aplicación, otro dominio o ambos. Usando una técnica similar, los ataques también pueden ser desviados. Con una cuidadosa combinación de hojas de estilo, iframes y cuadros de texto, se puede engañar a los usuarios haciéndoles creer que están ingresando su dirección de correo electrónico o la contraseña de su cuenta bancaria, pero en cambio, golpean un marco invisible controlado por el atacante.

## CORS

La compartición de recursos de origen cruzado es un mecanismo del navegador, que permite el acceso controlado a recursos situados fuera de un determinado dominio.
Amplía y añade flexibilidad a la política del mismo origen (SOP). También proporciona un potencial para los ataques basados en dominios cruzados. Si la política de cors de los sitios web está mal configurada o implementada, no protege contra los ataques de origen cruzado como CSRF.

## O-Auth

La serialización es el proceso de convertir una estructura de datos compleja, como los objetos y su campo, aun formato más plano que pueda ser enviado y recibido como un flujo secuencial de bytes. Enviar datos complejos, por ejemplo, a través de una red, entre diferentes componentes de una aplicación, o en una llamada a la API. Cuando se serializa un objeto también se persiste su estado, en otras palabras, los atributos del objeto se conservan junto con sus valores asignados.

## Insecure Deserealization SE REPITE MUCHO LA PALABRA BUSCA SINONIMOS Y RESUMIR

Muchos ataques de deserialización se completan antes de que la deserialización haya terminado. Esto significa que el propio proceso de deserialización puede iniciar el ataque, incluso si la propia funcionalidad de la aplicación no interactúa directamente con el objeto malicioso.
El impacto de una deserealizacion insegura puede ser grave, ya que proporciona un punto de entrada a una superficie de ataque enormemente aumentada. Permite a los atacantes reutilizar el código de la aplicación existente de manera perjudicial, lo que genera muchas otras vulnerabilidades, a menudo RCE (Ejecución remota de código).

## HTTP Request Smuggling

El contrabando de solicitudes HTTP es una técnica para interferir con la forma en que un sitio web procesa la secuencia de solicitudes HTTP que se reciben de uno o más usuarios.
Esta vulnerabilidad es de naturaleza crítica, lo que permite a un atacante eludir los controles de seguridad, obtener acceso no autorizado a datos confidenciales y comprometer directamente otra aplicación.

## Web Cache Poisoning

El envenenamiento de la caché web es una técnica avanzada en la que un atacante explota el comportamiento del servidor web y para enviar una respuesta HTTP maliciosa a otros usuarios.  
En primer lugar, un atacante debe descubrir cómo obtener una respuesta de backend, sin darse cuenta, contiene algún tipo de carga útil maliciosa.  
Una vez que el primer paso es exitoso, deben asegurarse de que su respuesta se almacene en caché y luego se entregue a la víctima prevista.  
El caché web infectado puede ser una forma devastadora de lanzar una variedad de ataques que explotan vulnerabilidades como XSS, inyección de JavaScript, redireccionamientos abiertos y más.

## Server Side Template Injection

SSTI ocurre cuando un atacante puede usar la sintaxis nativa del modelo para inyectar una carga útil maliciosa en un modelo, que se ejecuta en el lado del servidor.
Ocurre cuando la entrada del usuario se concatena directamente en una plantilla, en lugar de pasarla como datos, lo que permite que un atacante introduzca directivas de plantilla arbitrarias para manipular el motor de plantilla, lo que a menudo les permite tener un control total sobre el servidor. El impacto de SSTI expone a los sitios web a varios ataques dependiendo del motor de plantilla, en algunos casos esta vulnerabilidad no representa un riesgo de seguridad real, pero la mayor parte del impacto de SSTI es muy catastrófico en la fase crítica de la escala un atacante puede llegar al RCE, tomar el control total del servidor. En el caso de que la ejecución remota de código no sea posible, el atacante puede usar un servidor modelo en paralelo como base para muchos otros ataques, obteniendo potencialmente acceso de lectura a datos confidenciales y archivos arbitrarios en el servidor.

## Attacking GraphQL

GraphQL es un lenguaje de consulta para API y un tiempo de ejecución para cumplir con esas consultas con datos existentes. Un servicio GraphQL se crea definiendo tipos y campos en esos tipos y luego proporcionando funciones para cada campo en cada tipo.
