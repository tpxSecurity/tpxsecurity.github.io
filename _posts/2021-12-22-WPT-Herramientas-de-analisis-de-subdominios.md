---
title: "Herramientas de análisis de subdominios"
author: 
  name: Julio Romo T
  link: https://github.com/TishcaTpx
date: 2021-12-22 00:00:00 +0800
categories: [Seguridad,Web, Herramientas Web]
tags: [Seguridad,Web, Herramientas Web]
image:
  src: /assets/img/posts/banner-herramientas-subdomain.png
  width: 800
  height: 500
  alt: Herramientas de análisis de subdominios
---


El análisis de subdominios es fundamental dentro la realización de un pentest bajo el entendimiento de que no todo lo que esta dentro de un sistema es completamente visible o se tiene conocimiento de ello dentro de la realización de un pentest, de esta forma se van descubriendo nuevos caminos al realizar pruebas y fortalecer la infraestructura.

## Análisis pasivo

El análisis pasivo de subdominios, hace uso de varias técnicas, entre una de ellas es la recolección de información indexada dentro de los buscadores mejor conocida como dorks, además algunos de estos sitios realizan sus propios ataques con diccionario para la obtención de subdominios extra.

* [DNS Dumpster](https://dnsdumpster.com/):
  
  Esta herramienta principalmente nos ofrece información solo de los subdominios indexados dentro de internet, una de las ventajas de este es la característica de interfaz gráfica que nos brinda, nos permite ver un diagrama de la composición del dominio.

* [RapidDNS](https://rapiddns.io/)
  
  RapidDNS tiene la propiedad de realizar una serie de búsquedas con diccionarios además de la indexación brindando una lista de subdominios más acercada a la real.

* [Virustotal](https://www.virustotal.com/gui/domain/tpx.mx/relations)
  
  Virustotal una de las bases de datos de virus más grande del mundo añadio una característica dentro de la funcionabilidad de su sitio la cual nos permite analizar un dominio para detectar malware dentro de el. El cual dentro del análisis realiza tambien una detección dentro de los subdominios.

* [Pentest-tools](https://pentest-tools.com/information-gathering/find-subdomains-of-domain)
  
  El sitio pentest-tools consta con una recopilación de las herramientas más importantes durante una auditoría de seguridad, la cual nos facilita el realizar análisis desde la red.

* [Spyse](https://spyse.com/search?target=domain&query=)
  
  Spyse es una herramienta estilo shodan la cual indexa y realiza análisis a IP, Dominios y Organizaciónes. Este nos permite verificar los dominios activos que logré identificar además de las tecnologías implementadas.

* [DNSLOOKUP](https://dnslookup.es/)
DNS LookUp es una herramienta de diagnóstico de DNS y consulta de registros de DNS que permite conocer el estado de servidores DNS y registros de DNS.



## Análisis Activo

### Gobuster

Esta herramienta nos brinda la capacidad de enumerar mediante fuerza bruta, dentro de las capacidades de este nos permite enumerar subdominios y directorios de una manera bastante rápida dado su opción de uso de hilos.

 ```console
  root@tpx.mx:$ gobuster  dns  -d tpx.mx -w /usr/share/wordlists/dirbuster/directory-list-lowercase-2.3-medium.txt  =============================================================== 
  Gobuster v3.1.0 
  by OJ Reeves (@TheColonial) & Christian Mehlmauer (@firefart) 
  ===============================================================
  [+] Domain:     tpx.mx 
  [+] Threads:    10 
  [+] Timeout:    1s 
  [+] Wordlist:   /usr/share/wordlists/dirbuster/directory-list-lowercase-2.3-medium.txt
  =============================================================== 
  2022/02/28 14:17:12 Starting gobuster in DNS enumeration mode 
  =============================================================== 
  Found: info.tpx.mx            
  Found: i.tpx.mx               
  Found: www.tpx.mx              
  Found: c.tpx.mx                
  Found: u.tpx.mx                
  Found: form.tpx.mx             
  Found: status.tpx.mx           
  Found: gifs.tpx.mx             
  =============================================================== 
  2022/02/28 14:17:19 Finished 
  ===============================================================                                 
 ```

### Knockpy

Knockpy es una herramienta hecha en python3 diseñada para enumerar rápidamente subdominios en  dominio objetivo a través de un ataque con diccionario.

```console
  root@tpx.mx:$ git clone https://github.com/guelfoweb/knock.git
  root@tpx.mx:$ cd knock
  root@tpx.mx:$ pip3 install -r requirements.txt
  root@tpx.mx:$ python3 knockpy.py tpx.mx
```

### Amass (OWASP®)

El proyecto de OWASP Amass realiza un mapeo de la red mediante ataques sobre la red y descubrimiento externo de activos con el uso de técnicas Open Source Information Gathering y reconocimiento activo.

```console
  root@tpx.mx:$ sudo snap install amass
  root@tpx.mx:$ amass enum -passive -d tpx.mx -src
```

### DNSRecon

DNSRecon es un script en python que nos permite realizar las siguientes técnicas:

* Check all NS Records for Zone Transfers.
* Enumerate General DNS Records for a given Domain (MX, SOA, NS, A, AAAA, SPF and TXT).
* Perform common SRV Record Enumeration.
* Top Level Domain (TLD) Expansion.
* Check for Wildcard Resolution.
* Brute Force subdomain and host A and AAAA records given a domain and a wordlist.
* Perform a PTR Record lookup for a given IP Range or CIDR.
* Check a DNS Server Cached records for A, AAAA and CNAME
* Records provided a list of host records in a text file to check.
* Enumerate Hosts and Subdomains using Google

```console
  root@tpx.mx:$ dnsrecon -d tpx.mx -D /usr/share/wordlists/dnsmap.txt -t std
  [*] Performing General Enumeration of Domain:tpx.mx
  [*] DNSSEC is configured for tpx.mx
  [*] DNSKEYs:
  [*]     None KSk ECDSAP256SHA256 99db2cc14cabdc33d6d77da63a2f15f7 1112584f234e8d1dc428e39e8a4a97e1 aa271a555dc90701e17e2a4c4b6f120b 7c32d44f4ac02bd894cf2d4be7778a19
  [*]     None ZSK ECDSAP256SHA256 a09311112cf9138818cd2feae970ebbd 4d6a30f6088c25b325a39abbc5cd1197 aa098283e5aaf421177c2aa5d714992a 9957d1bcc18f98cd71f1f1806b65e148
  [*]      SOA jean.ns.cloudflare.com 173.245.58.121
  [*]      SOA jean.ns.cloudflare.com 172.64.32.121
  [*] Enumerating SRV Records
```
