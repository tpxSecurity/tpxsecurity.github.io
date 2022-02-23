---
title: "Análisis de vulnerabilidades Web"
author: "Julio Alberto Romo T"
date: 2022-2-15 23:22:00 +0800
categories: [Seguridad,Herramientas]
tags: [Seguridad,Herramientas]

image:
  src: 
  width: 800
  height: 500
  alt: Análisis de vulnerabilidades Web
---

Dentro de la fase de reconocimiento se intenta obtener la mayor parte información orientada a la plataforma a auditar, de lo cual destacan, librerias, software de terceros, frameworks, rutas o endpoints. Con el resultado de ello se procede a identificar vulnerabilidades, con las veriones de software detectadas a si como el realizar una serie de pruebas controladas o detección de patrones en variables y rutas.

## Detección de directorios/EndPointscon 

El analisis de directorios/Endpoits es fundamental dentro la realización de un penstes bajo el entendimiento de que no todo lo que esta dentro de un sistema es completamente visible o se tiene conocimiento de ello, de esta forma descubriendo nuevos caminos a realizar pruebas y fortalecer.

### Gobuster

Esta herramienta nos brinda la capacidad de enumerar mediante fuerza bruta, dentro de las capacidades de este nos permite enumerar subdominios y directorios de una manera bastante rapida dado su opción de uso de hilos.

 ```console
  root@tpx.mx:$ gobuster dir -u https://tpx.mx -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt 
  ===============================================================
  Gobuster v3.1.0
  by OJ Reeves (@TheColonial) & Christian Mehlmauer (@firefart)
  ===============================================================
  [+] Url:                     https://tpx.mx
  [+] Method:                  GET
  [+] Threads:                 10
  [+] Wordlist:                /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt
  [+] Negative Status codes:   404
  [+] User Agent:              gobuster/3.1.0
  [+] Timeout:                 10s
  ===============================================================
  2022/02/15 17:18:19 Starting gobuster in directory enumeration mode
  ===============================================================
  /contact              (Status: 301) [Size: 0] [--> https://tpx.mx/contacto]
  /privacy              (Status: 301) [Size: 0] [--> https://tpx.mx/privacy-policy]
  /logo                 (Status: 301) [Size: 0] [--> https://tpx.mx/0xFiles/files/2017/07/logo.jpg]
  /blog                 (Status: 403) [Size: 144605]                                               
  /rss                  (Status: 301) [Size: 0] [--> https://tpx.mx/feed]                          
  [!] Keyboard interrupt detected, terminating.
                                                                                                  
  ===============================================================
  2022/02/15 17:18:22 Finished
  ===============================================================
 ```

### Dirbuster

Esta herramienta con interfaz grafica permite realizar una busqueda recursiva dentro de los directorios obtenidos, detectando nuevas rutas a si como archivos en ellas.

### Dirb

Se podria decir que esta herramienta es la versión no grafica o de consola de Dirbuster

```console
  root@tpx.mx:$ dirb tpx.mx
  dirb https://tpx.mx

  -----------------
  DIRB v2.22    
  By The Dark Raver
  -----------------

  START_TIME: Tue Feb 15 17:05:40 2022
  URL_BASE: https://tpx.mx/
  WORDLIST_FILES: /usr/share/dirb/wordlists/common.txt

  -----------------

  GENERATED WORDS: 4612                                                          

  ---- Scanning URL: https://tpx.mx/ ----
  Testing: https://tpx.mx/.htpasswd   
```

### FFUF / WFUZZ

FFUF y Wfuzz fueron creados para facilitar la tarea en las evaluaciones contra aplicaciones web, y está basado en un concepto simple; reemplaza cualquier referencia a la palabra clave FFUF/FUZZ, por el valor del payload (carga útil) definido.

```console
  root@tpx.mx:$ wfuzz -c --hc=404 -z file,/usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt https://tpx.mx/FUZZ

  ********************************************************
  * Wfuzz 3.1.0 - The Web Fuzzer                         *
  ********************************************************

  Target: https://tpx.mx/FUZZ
  Total requests: 220560

  =====================================================================
  ID           Response   Lines    Word       Chars       Payload                                                                                                                                                                   
  =====================================================================

  000000025:   301        0 L      0 W        0 Ch        "contact"                                                                                                                                                                 
  000000003:   403        739 L    5799 W     154355 Ch   "# Copyright 2007 James Fisher"                                                                                                                                           
  000000007:   403        739 L    5279 W     148390 Ch   "# license, visit http://creativecommons.org/licenses/by-sa/3.0/"                                                                                                         
  000000001:   403        739 L    5279 W     148390 Ch   "# directory-list-2.3-medium.txt"                                                                                                                                         
  000000014:   403        739 L    5279 W     148390 Ch   "https://tpx.mx/"                                                                                                                                                         
  000000012:   403        739 L    5279 W     148390 Ch   "# on atleast 2 different hosts"                                                                                                                                          
  000000011:   403        739 L    5279 W     148390 Ch   "# Priority ordered case sensative list, where entries were found"                                                                                                        
  

  Total time: 0
  Processed Requests: 18
  Filtered Requests: 11
  Requests/sec.: 0
```

### OpenDoor

OWASP OpenDoor es un escaner de consola multifuncional. Esta aplicación consiste en encontrar todas las posibles formas de acceder a directorios raiz "/", terminales web, puntos de acceso restringidos, subdominios, datos ocultos y copias de seguridad. El escaneo es realizado por un diccionario todo en uno y listas customizadas.
Puede ser realizado mendiante el uso de servidores proxy con fin de mantener el anonimato y acelerar el proceso. La herramienta fue escrita con motivos informativos y es producto de codigo abierto (open source) bajo la lisencia GPL.

```console
  root@tpx.mx:$ git clone https://github.com/stanislav-web/OpenDoor.git
  root@tpx.mx:$ cd OpenDoor/
  root@tpx.mx:$ pip3 install -r requirements.txt
  root@tpx.mx:$ chmod +x opendoor.py

  root@tpx.mx:$ python3 opendoor.py --host https://tpx.mx
```

![OWASP_OpenDoor](https://camo.githubusercontent.com/1a3d43458e3997c2ce547ed761e1b4a735271338b77df1cbad9f9f3febc55725/687474703a2f2f646c332e6a6f78692e6e65742f64726976652f323031372f30312f33302f303030312f303337382f39303439302f39302f653330393734326235632e6a7067)

## Escaneo de vulnerabilidades

  Este proceso suele ser importante dentro de las auditorias, con el motivo de reducir el tiempo de detección manual, mediante el uso y busqueda de patrones de vulnerabilidades detectadas en sistemas pasados.

### OWASP ZAP

OWASP Zed Attack Proxy (ZAP) es una de las herramienta de seguridad gratuita mas popular a nivel mundial y cuenta con mantenimiento activo  por un equipo internacional de voluntarios. Puede ayudarte detectar automaticamente vulnerabilidades en aplicaciones web mientras desarrollas o testeas tus aplicaciónes. Tambien es una gran herramienta para pentesters experimentados para realizar pruebas de seguridad manuales.

### Burp Sutie

Burp o Burp Suite es un conjunto de herramientas utilizadas por pentesters de aplicaciones web. Esta se mantiene en constante desarrollo por la empresa Portswigger, el cual tambien es el alias de su fundador Dafydd Stuttard. Burpsuite tiene la vision de ser una de las herramientas todo en uno a si como una de sus capacidades este es soportar el uso de addons llamados Bapps.

### BeEF

BeEF es la abrebiatura de Browser Explotation Framework. La cual es una herramienta de pentesting la cual se enfoca en la navegación web.

Dada la creciente preocupación generada por los constantes ataques dirigidos a los entornos web y sus clientes, incliyendo clientes mobiles, BeEF permite a los profecionales en ciberseguridad realizar pruebas actuales tomando una postura de ataque al entorno de una forma client-side o del lado del cliente. A diferencia de otros frameworks de seguridad,  BeEF va más allá de los perimetros de la red y los sistemas del cliente, examina la explotabilidad sin el concepto "the one opendor: the web browser". BeEF puede hacer uso de uno o mas navegadores

### SNYK

SNYK es una empresa que nos brinda productos y servicios para detectar  y reparar vulnerabilidades dentro del codigo, dependencias, contenedores e infraestructura. Su herramienta gratuita en linea nos permite hacer una busqueda.

[SNYK Scanner](https://snyk.io/website-scanner/)

### Pentest Tools

Este sitio nos brinda bastantes herramientas para relizar analis a sitios web, verificando cabeceras, versiones de software, librerias, etre algunas otras funciones.

[Pentest tools](https://pentest-tools.com/website-vulnerability-scanning/website-scanner)

### NMAP  HTTP Scripts

Dentro de las cualidades de nmap contamos con una potente función dentro de su nucleo, el cual es el uso de scripts automaticos. Estos ***scripts*** nos permiten el relizar escaneos mas avanzados y dirigidos espesificamente a la información que seseamos obtener, como ejemplo, deteccion de versiones de frameworks, verificacion ssl, enumeracion de directorios entre otros.

```console
    root@tpx.mx:$ nmap --script=http-* -p80,443,8080 tpx.mx 

    PORT     STATE  SERVICE
    80/tcp   open   http
    |_http-mobileversion-checker: No mobile version detected.
    |_http-config-backup: ERROR: Script execution failed (use -d to debug)
    | http-brute:   
    |_  Path "/" does not require authentication
    | http-methods: 
    |_  Supported Methods: POST OPTIONS
    |_http-title: Site doesn't have a title (text/html).
    |_http-referer-checker: Couldn't find any cross-domain scripts.
    |_http-stored-xss: Couldn't find any stored XSS vulnerabilities.
    | http-headers: 
    |   Cache-control:no-cache, no-store, max-age=0
    |   Content-Type:text/html
    |   Pragma:no-cache
    |   Transfer-Encoding:chunked
    |   X-Frame-Options:SAMEORIGIN
    |   Connection:Keep-Alive
    |   X-XSS-Protection:1; mode=block
    |   Content-Security-Policy:default-src 'self' 'unsafe-inline' 'unsafe-eval'
    |   
    |_  (Request type: GET)
    | http-sitemap-generator: 
    |   Directory structure:
    |   Longest directory structure:
    |     Depth: 0
    |     Dir: /
    |   Total files found (by extension):
    |_    
    |_http-chrono: ERROR: Script execution failed (use -d to debug)
    | http-vhosts: 
    | 16 names had status ERROR
    |_112 names had status 404
    |_http-dombased-xss: Couldn't find any DOM based XSS.
    |_http-comments-displayer: Couldn't find any comments.
    | http-useragent-tester: 
    |   Status for browser useragent: 200
    |   Allowed User Agents: 
    |     Mozilla/5.0 (compatible; Nmap Scripting Engine; https://nmap.org/book/nse.html)
    |     libwww
    |     lwp-trivial
    |     libcurl-agent/1.0
    |     PHP/
    |     Python-urllib/2.5
    |     GT::WWW
    |     Snoopy
    |     MFC_Tear_Sample
    |     HTTP::Lite
    |     PHPCrawl
    |     URI::Fetch
    |     Zend_Http_Client
    |     http client
    |     PECL::HTTP
    |     Wget/1.13.4 (linux-gnu)
    |_    WWW-Mechanize/1.34
    |_http-csrf: Couldn't find any CSRF vulnerabilities.
    |_http-feed: Couldn't find any feeds.
    |_http-fetch: Please enter the complete path of the directory to save data in.
    |_http-xssed: No previously reported XSS vuln.
    |_http-errors: Couldn't find any error pages.
    |_http-favicon: Unknown favicon MD5: A3E1F4B29FFC8DEB3E5EA97C62C493A4
    |_http-malware-host: false
    |_http-majordomo2-dir-traversal: ERROR: Script execution failed (use -d to debug)
    | http-traceroute: 
    |_  Possible reverse proxy detected.
    |_http-vuln-cve2014-3704: ERROR: Script execution failed (use -d to debug)
    | http-security-headers: 
    |   Strict_Transport_Security: 
    |     HSTS not configured in HTTPS Server
    |   X_Frame_Options: 
    |     Header: X-Frame-Options: SAMEORIGIN
    |     Description: The browser must not display this content in any frame from a page of different origin than the content itself.
    |   X_XSS_Protection: 
    |     Header: X-XSS-Protection: 1; mode=block
    |     Description: The browser will prevent the rendering of the page when XSS is detected.
    |   Content_Security_Policy: 
    |     Header: Content-Security-Policy: default-src 'self' 'unsafe-inline' 'unsafe-eval'
    |     Description: Define loading policy for all resources type in case of a resource type dedicated directive is not defined (fallback).
    |   Cache_Control: 
    |     Header: Cache-Control: no-cache, no-store, max-age=0
    |   Pragma: 
    |_    Header: Pragma: no-cache
    | http-slowloris: 
    |   Vulnerable:
    |   the DoS attack took +1m42s
    |   with 1001 concurrent connections
    |_  and 0 sent queries
    443/tcp  closed https
    8080/tcp closed http-proxy

    Nmap done: 1 IP address (1 host up) scanned in 1861.59 seconds

```
