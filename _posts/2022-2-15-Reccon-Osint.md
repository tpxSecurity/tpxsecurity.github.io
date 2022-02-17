---
title: "Reccon Osint"
author: "Eduardo Rosales Meoño"
date: 2022-2-15 23:22:00 +0800
categories: [Seguridad,Técnicas]
tags: [Seguridad]

image:
  src: 
  width: 800
  height: 500
  alt: Reccon Osint
---
## Domain info(whois [ [Whoxy](https://www.whoxy.com), [Whoisxmlapi](https://www.whoisxmlapi.com), [Dnslytics](https://dnslytics.com/) ],resistant)

antes de realizar un ataque un pentester debe conocer el entorno destino como las caracteristicas del sistema.
Cuanta más información específica encuentre el pentester, mayores serán las posibilidades de identificar la forma más fácil y rápida de tener éxito, los servicios de exploración pueden incluir huellas de Internet para investigar objetivos, monitorear recursos, monitorear personal, procesos, escanear información de red y servicios públicos de ingeniería social como mesas de ayuda.

## Metadata

Los **metadatos** son información relacionada a un recurso , esta información puede contener datos como la procedencia del archivo, fecha de creación, fecha de modificación, autor, dimensiones, modelo de cámara , coordenadas GPS entre otros, estos brindan información valiosa sobre un objetivo ya que  permiten identificar patrones de comportamiento, hábitos, software o tecnología utilizada para la generación de documentos o archivos hasta detalles personales.

## Data leaks

Una violación de datos es la transferencia no intencional de datos a partir de en una organización a un destinatario externo. Si bien esta puede provocar pérdidas financieras inmediatas a una organización.

pwndb es una herramienta empleada para ola busqeda de credenciales o datos filtrados en el servicio onion.

## Google dorks

es una tecnica que utiliza la busqueda avanzada de google para la obtencion de agujeros de seguridad en la configuracion
o en el codigo  interno de los sitios web.

```console

- intitle: el título que se busca;
- inurl: la URL del sitio web al que se dirige.
- ” : buscar frase exacta.
- and y not: operadores lógicos y o no.
- + y –: incluir y excluir.
- * :  cualquier palabra, pero una sola palabra.
- . :  cualquier palabra, una o muchas.
- site: solo busca resultados dentro de la web que va detrás de site.
- filetype: solo busca archivos de un tipo (doc, xls, txt…).
- link: solo busca en páginas que tienen un link a una determinada web.
- inanchor: solo busca en páginas que tienen en el texto de enlace la expresión buscada.
- cache: muestra el resultado en la caché de Google de una página web.
- related: busca webs relacionadas con una determinada.

```

## Gihub dorks

es una tecnica muy eficaz debido a que con ella se pueden encontrar informacion confidencial de los repositorios de github.

**busqueda de archivos**

 ```console
filename:manifest.xml
filename:travis.yml
filename:vim_settings.xml
filename:database
filename:prod.exs NOT prod.secret.exs
filename:prod.secret.exs
filename:.npmrc _auth
filename:.dockercfg auth
filename:WebServers.xml
filename:.bash_history <Domain name>
filename:sftp-config.json
filename:sftp.json path:.vscode
filename:secrets.yml password
filename:.esmtprc password
filename:passwd path:etc
filename:dbeaver-data-sources.xml
path:sites databases password
filename:config.php dbpasswd
filename:prod.secret.exs
filename:configuration.php JConfig password
filename:.sh_history
shodan_api_key language:python
filename:shadow path:etc
JEKYLL_GITHUB_TOKEN
filename:proftpdpasswd
filename:.pgpass
filename:idea14.key
filename:hub oauth_token
HEROKU_API_KEY language:json
HEROKU_API_KEY language:shell
SF_USERNAME salesforce
filename:.bash_profile aws
extension:json api.forecast.io
filename:.env MAIL_HOST=smtp.gmail.com
filename:wp-config.php
extension:sql mysql dump
filename:credentials aws_access_key_id
filename:id_rsa or filename:id_dsa
 ```

**busqueda de lenguajes**

  ```console
  language:python username
language:php username
language:sql username
language:html password
language:perl password
language:shell username
language:java api
HOMEBREW_GITHUB_API_TOKEN language:shell
   ```

**busqueda de API Keys, Tokens and Passwords**

  ```console
  api_key
“api keys”
authorization_bearer:
oauth
auth
authentication
client_secret
api_token:
“api token”
client_id
password
user_password
user_pass
passcode
client_secret
secret
password hash
OTP
user auth
  ```

**busqueda de username**

  ```console
user:name (user:admin)
org:name (org:google type:users)
in:login (<username> in:login)
in:name (<username> in:name)
fullname:firstname lastname (fullname:<name> <surname>)
in:email (data in:email)
  ```  

**busqueda de informacion por fecha**

   ```console
created:<2012–04–05
created:>=2011–06–12
created:2016–02–07 location:iceland
created:2011–04–06..2013–01–14 <user> in:username
  ```

**busqueda de informacion por extensiones**

   ```console
extension:pem private
extension:ppk private
extension:sql mysql dump
extension:sql mysql dump password
extension:json api.forecast.io
extension:json mongolab.com
extension:yaml mongolab.com
[WFClient] Password= extension:ica
extension:avastlic “support.avast.com”
extension:json googleusercontent client_secret
  ```
  