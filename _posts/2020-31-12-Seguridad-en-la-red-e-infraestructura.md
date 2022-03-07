---
title: "Seguridad en la red e infraestructura - Cheat Sheet"
author: 
  name: Julio Romo T
  link: https://github.com/TishcaTpx
date: 2020-12-31 00:00:00 +0800
categories: [Seguridad]
tags: [Seguridad]
pin: true
image:
  src: /assets/img/7f81085e1dc317d445db7d06780e0e17.png
  width: 800
  height: 500 
  alt: Fundamentos
---

* 1.- Funcionamiento de las redes
  * 1.1.- Funcionamiento de la Red /modelo OSI a detalle.
  * 1.2.- ¿Qué es un servicio?
  * 1.3.- ¿Qué es un protocolo?
  * 1.4.- ¿Cómo viaja tu información a través de la red?
* 2.- Equipos dentro de la red
  * 2.1.- Equipos cliente o Nodos
    * 2.1.1.- Descripción y funcionamiento
    * 2.1.2.- Servicios y protocolos comunes
    * 2.1.3.- Vulnerabilidades y ataques más frecuentes
  * 2.2.- Equipos de transmisión
    * 2.2.1.- Descripción y funcionamiento
    * 2.2.2.- Servicios y protocolos comunes
    * 2.2.3.- Vulnerabilidades y ataques más frecuentes
  * 2.3.- Equipos de enrutamiento
    * 2.3.1.- Descripción y funcionamiento
    * 2.3.2.- Servicios y protocolos comunes
    * 2.3.3.- Vulnerabilidades y ataques más frecuentes
  * 2.4.- Equipos de proveedores de servicios
    * 2.4.1.- Descripción y funcionamiento
    * 2.4.2.- Servicios y protocolos comunes
    * 2.4.3.- Vulnerabilidades y ataques más frecuentes
* 3.- Auditando la Red
  * 3.1.- Descubriendo la topología de la red
  * 3.2.- Identificación de equipos
  * 3.3.- Análisis de vulnerabilidades
  * 3.4.- Auditoria Equipos cliente (nodos)
    * 3.4.1.- Ataques físicos
      * 3.4.1.1.- Bad USB
      * 3.4.1.2.- Rubber Ducky
      * 3.4.1.3.- Bash Bunny
      * 3.4.1.4.- Plunder BUG LAN TAP
      * 3.4.1.5.- Key Croc
      * 3.4.1.6.- Screen Crab
      * 3.4.1.7.- Packet Squirrel
      * 3.4.1.8.- Lan Turtle
      * 3.4.1.9 .- NetHunter (All in one)
    * 3.4.2.- Ataques Inalámbricos
      * 3.4.2.1.- Deauth Network Client
      * 3.4.2.2.- Bypass Hostpot ( Clonado de MAC )
      * 3.4.2.3.- Hacking bluetooth
      * 3.4.2.4.- Sniffing
    * 3.4.3.- Ataques en el enlace de datos
      * 3.4.3.1.- Spoofing DNS
      * 3.4.3.2.- Spoofing ARP
    * 3.4.4.- Ataque en red
      * 3.4.4.1.- Man in the middle
    * 3.4.5.- Ataque a la capa de presentación
      * 3.4.5.1.- Phishing
    * 3.4.6.- Ataques nivel aplicación
      * 3.4.6.1 Exploits
  * 3.5.- Auditoria Equipos de transmisión
    * 3.5.1.- Ataques Inalámbricos (Routers y Módems WIFI)
      * 3.5.1.1.- DOS Deauth attack
      * 3.5.1.2.- Sniffing
      * 3.5.1.3.- Cracking/Hacking WIFI
      * 3.5.1.4.- WPS Pixie Dust
      * 3.5.1.5.- WPS Bruteforce  & common Pins
      * 3.5.1.7.- WEP replay attack
      * 3.5.1.8.- WEP chopchop attack
      * 3.5.1.9.- WEP fragment attack
      * 3.5.1.10.- WEP hirte attack
      * 3.5.1.11.- WEP p0841 attack
      * 3.5.1.12.- WEP caffe-latte attack
      * 3.5.1.13.- WPA/2 Brute-Force Handshake
      * 3.5.1.14.- Evil Twin
      * 3.5.1.15.- Rouge AP
    * 3.4.2.- Ataques en el enlace de datos (SWITCH, HUBS)
      * 3.4.2.1.- Ataques susplantación DHCP
      * 3.4.2.2.- Ataques inanición DHCP
      * 3.4.2.3.- Ataques CDP
      * 3.4.2.4.- Ataques Telnet (Fuerza bruta)
      * 3.4.2.5.- Ataques Denial of Service
  * 3.6.- Equipos de enrutamiento
    * 3.6.1.- Denial of Service
    * 3.6.2.- Brute Force
    * 3.6.3.- Packet mistreating attacks
    * 3.6.4.- Router table poisoning
    * 3.6.5.- Persistent Attacks
    * 3.6.6.- Hit and Run
    * 3.6.7.- Syn Flood
    * 3.6.8.- Routopsy
  * 3.7.- Equipos proveedores de servicios (Servidor)
    * 3.7.1.- Reconocimiento (Enumeración de puertos y servicios)
      * 3.7.1.1.- Nmap y uso de scripts
    * 3.7.2.- Introducción base a servicios web y sus vulnerabilidades
    * 3.7.3.- Explotación de servicios comunes
      * 3.7.3.1.- SMTP
      * 3.7.3.2.- TELNET
      * 3.7.3.3.- FTP
      * 3.7.3.4.- SMB
      * 3.7.3.5.- RPC
      * 3.7.3.6.- POP3
    * 3.7.4.- Explotación de vulnerabilidades
      * 3.7.4.1.- Metasploit
      * 3.7.4.2.- Exploits externos
* 4.- Perimetrales
  * 4.1.- Firewalls
  * 4.2.- WAF
  * 4.3.- CDN
  * 4.4.- IPS
  * 4.5.- IDS
  * 4.6.- Control de acceso a la identidad
  * 4.7.- Honeypots
