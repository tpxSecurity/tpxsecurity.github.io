---
title: "Técnicas y herramientas de análisis web"
author: 
  name: Eduardo Rosales Meoño
date: 2021-12-22 00:00:00 +0800
categories: [Seguridad,Web, Herramientas Web]
tags: [Seguridad,Web, Herramientas Web]
image:
  src: 
  width: 800
  height: 500
  alt: Técnicas y herramientas de análisis web
---

Desntro del contenido de este post se exploraran algunas tecniacas y herramientas, las cuales nos facilitaran y apoyaran a la realización de una auditoria de seguridad en la fase de reconocimiento de información web.

### 7.5.1.2.- Técnicas Web

Dentro de la fase de reconocimiento se intenta obtener la mayor parte información orientada a la plataforma a auditar, de lo cual destacan, librerías, software de terceros, frameworks, rutas o endpoints. Con el resultado de ello se procede a identificar vulnerabilidades, con las versiones de software detectadas así como el realizar una serie de pruebas controladas o detección de patrones en variables y rutas.

#### 7.5.1.2.1.- Waf detection

wafw00f es una herramienta utilizada para verificar si extste un firewall para las aplicaciones web, entre los clientes y el sitio web.

```console
  root㉿kali)-[~]
└─$ wafw00f https://tpx.mx/            

                   ______
                  /      \                                                                       
                 (  Woof! )                                                                      
                  \  ____/                      )                                                
                  ,,                           ) (_                                              
             .-. -    _______                 ( |__|                                             
            ()``; |==|_______)                .)|__|                                             
            / ('        /|\                  (  |__|                                             
        (  /  )        / | \                  . |__|                                             
         \(_)_))      /  |  \                   |__|                                             

                    ~ WAFW00F : v2.1.0 ~
    The Web Application Firewall Fingerprinting Toolkit                                          
                                                                                                 
[*] Checking https://tpx.mx/
[+] The site https://tpx.mx/ is behind Cloudflare (Cloudflare Inc.) WAF.
[~] Number of requests: 2
```

 [Fuzzing](#75123--fuzzing).

#### 7.5.1.2.3.- Fuzzing

Esta técnica se basa en enviar datos erroneos a formularios, dentro de una aplicación de una forma automatizada o semiautomatizada mediante el uso de diccionarios.
Dentro de estos dicciónarios nos encontramos payloads los cuales incluyen, números, letras, caracteres especiales hasta código para generar una falla o comportamiento inesperado dentro del sistema.

## PortSwigger Burp Suite
Burp Suite Professional, de PortSwigger, es el conjunto de herramientas de prueba de seguridad web líder en el mundo, con herramientas manuales y automatizadas diseñadas por expertos, puede probar de manera más inteligente, no más difícil.

#### 7.5.1.2.4.- CMS scan
## wpscan
```console
(root㉿kali)-[]
└─$ wpscan --url https://tpx.mx/ --disable-tls-checks --random-user-agent                                                                                                                                                                4 ⨯
_______________________________________________________________
         __          _______   _____
         \ \        / /  __ \ / ____|
          \ \  /\  / /| |__) | (___   ___  __ _ _ __ ®
           \ \/  \/ / |  ___/ \___ \ / __|/ _` | '_ \
            \  /\  /  | |     ____) | (__| (_| | | | |
             \/  \/   |_|    |_____/ \___|\__,_|_| |_|

         WordPress Security Scanner by the WPScan Team
                         Version 3.8.20
       Sponsored by Automattic - https://automattic.com/
       @_WPScan_, @ethicalhack3r, @erwan_lr, @firefart
_______________________________________________________________

[+] URL: https://tpx.mx/ [104.21.25.37]
[+] Started: Wed Mar  2 15:14:42 2022
```


#### 7.5.1.2.5.- Directory enumeración

## gobuster

```console                                                                                    
┌──(root㉿kali)-[~]
└─$ sudo gobuster dir -u https://tpx.mx/ -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -e -x txt,php,html,asp
===============================================================
Gobuster v3.1.0
by OJ Reeves (@TheColonial) & Christian Mehlmauer (@firefart)
===============================================================
[+] Url:                     https://tpx.mx/
[+] Method:                  GET
[+] Threads:                 10
[+] Wordlist:                /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt
[+] Negative Status codes:   404
[+] User Agent:              gobuster/3.1.0
[+] Extensions:              txt,php,html,asp
[+] Expanded:                true
[+] Timeout:                 10s
===============================================================
2022/03/02 15:56:33 Starting gobuster in directory enumeration mode
```

```console

```

#### 7.5.1.2.6.- Crawler

Los crawlers son programas que exploran páginas web.
Su objetivo principal es rastrear cada enlace de cada sitio web. Luego guarda una copia de todo lo que ve en los archivos. De esta manera, se crea un enlace único para reunir millones de páginas web que se encuentran en Internet y todo el contenido de cada página web.



#### 7.5.1.2.7.- Js análisis

El análisis de JS se basa en una técnica de depuración de código para detectar: fallas lógicas, peticiones e incluso vulnerabilidades. Dentro de estos archivos también podemos detectar Api keys las cuales nos permitan obtener mayor información como Firebase.

## visual studio code
Visual Studio Code es un editor de código actualizado y mejorado para la creacion y la depuración de aplicaciones web y en la nube. Este editor es gratis, el caul se puede desacragar en el seiguiente link.
https://code.visualstudio.com/

#### 7.5.1.2.8.- Cors check

CORS o Cross origin resource sharing es una característica fundamental dentro del desarrollo web, esta característica brinda la capacidad de realizar comunicación entre sistemas. Habilitando el acceso o parcial a la aplicacón, eso se ve reflejado dentro del mundo de las Apis y los permisos de acceso. El detalle de esto es el que pude ser una ventaja así como un gran riesgo.

Un gran ejemplo de ello solia ser un ataque muy famoso en 2008 - 2010 dentro de Facebook el cual era tan simple como mandar una url maliciosa en la cual dentro del codigo js existiera una petición bien formulada, el alcance que esa falla lograba alcanzar, realizaba un account takeover sin que el usuario realizara nada mas que un solo click.

```console
MY_URL=http://tpx.mx

curl -I -X OPTIONS \
  -H "Origin: ${MY_URL}" \
  -H 'Access-Control-Request-Method: GET' \
  "${MY_URL}/SOMETHING" 2>&1 | grep -i 'Access-Control-Allow-Origin'

```

#### 7.5.1.2.9.- [Check robots wayback](http://web.archive.org/):
)

Wayback machine es un sitio el cual nos permite regresar años e incluso decadas al pasado, permitiendonos visualizar nuestro objetivo, conocerlo y estudiar la estructura, diseño, programación e incluso viejos archivos. Entre ellos visiatar los Robots los cuales nos brinda información de rutas existentes las cuales no deben ser indexadas por un motor de búsqueda.



## Buscar Robots.txt:
 Wayback Machine muestra casi todo lo que encuentra en el sitio, incluido el archivo robots.txt. Esto es bueno porque si su sitio tiene un problema tecnico o de rastreo, se  puede averiguar la fecha o una aproximacion de cuándo se realizaron los cambios que causaron los problemas en robots.txt.
 