---
title: "7.- Auditoría orientada a entornos web"
author: 
  name: Julio Romo T
  link: https://github.com/TishcaTpx
date: 2021-12-25 23:22:00 +0800
categories: [Seguridad]
tags: [Seguridad]
image:
  src: 
  width: 800
  height: 500
  alt: Auditoría orientada a entornos web
---

## 7.1.- Estándares de desarrollo y sus características

### 7.1.1.- API REST

Explicar aqui

### 7.1.2.- SOAP

Explicar aqui

## 7.2.- Explorando los diferentes tipos de servidores y tecnologías

Explicar Otro post

## 7.3.- Alcance y proceso de una auditoría Web

Explicar Otro post

## 7.4.- Metodologías de seguridad orientadas hacia aplicaciones Web

Explicar Otro post

## 7.5.- Fases de una auditoría Web

Explicar Otro post

### 7.5.1.- Reconocimiento Aplicaciones Web

Durante la fase de recolección de información o mejor conocido como reconocimiento, se basa en la recopilación de información sobre el sistema o infraestructura a auditar. El objetivo es identificar datos desconocidos o no proporcionados por ejemplo:

* Direcciones de IP
* Topología de la red
* Tecnologías utilizadas
* Versiones de librerias
* Dsispositivos red y más.

Ahora se mostraran las diferentes técnicas para realizar la recopilación de información:

#### 7.5.1.1- Análisis de subdominios

La enumeración de subdominios es el proceso para encontrar subdominios de un objetivo.
Para realizar este proceso se puede hacer uso de herramientas de internet como [dnsdumpster](https://dnsdumpster.com/), [RapidDNS](https://rapiddns.io/) entre otras, otra forma de enumeración es mediante Técnicas como:

#### 7.5.1.1.1.- Pasivo

La información se obtiene sin interacción directa con el objetivo mediante el uso de técnicas como búsquedas en Internet, rastreo de redes. Algunas de estas Técnicas involucran el uso de buscadores o indexadores de contenido.

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

#### 7.5.1.2.1.- Waf detection

#### 7.5.1.2.2.- Web vuln scan

#### 7.5.1.2.3.- Fuzzing

#### 7.5.1.2.4.- CMS scan

#### 7.5.1.2.5.- Directory enumeración

#### 7.5.1.2.6.- Crawler

#### 7.5.1.2.7.- Js análisis

#### 7.5.1.2.8.- Cors check

#### 7.5.1.2.9.- Check robots wayback

### 7.5.1.3.- Osint

#### 7.5.1.3.1.- Domain info(whois,resistant)

#### 7.5.1.3.2.- Metadata

#### 7.5.1.3.3.- Emails, users, data leaks

#### 7.5.1.3.4.- Google dorks

#### 7.5.1.3.5.- Gihub dorks

### 7.5.2.- Explotación Aplicaciones Web

#### 7.5.2.1- SQL Injection

#### 7.5.2.2- Autenticacion

#### 7.5.2.3- Divulgación de información

#### 7.5.2.4- Broken Access Control

#### 7.5.2.5- IDOR

#### 7.5.2.6- Directory Traversal

#### 7.5.2.7- Server-side request Forgery (SSRF)

#### 7.5.2.8- XXE Injection

#### 7.5.2.9- Remote Code Execution

#### 7.5.2.10- BUSINESS LOGIC

#### 7.5.2.11 CSRF Cross Site Request For forgery

#### 7.5.2.12 WebSockets

#### 7.5.2.13- Cross Site Scripting

#### 7.5.2.14- DOM (Document Object Model)

#### 7.5.2.15- Click jacking

#### 7.5.2.16- CORS

#### 7.5.2.17- O-Auth

#### 7.5.2.18- Insecure Deserealization

#### 7.5.2.19- HTTP Request Smuggling

#### 7.5.2.20- Web Cache Poisoning

#### 7.5.2.21- Server Side Template Injection

#### 7.5.2.22- Web Cache Poisoning

#### 7.5.2.23- Attacking GraphQL

### 7.5.3- Post Explotación Aplicaciones Web
