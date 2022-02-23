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

#### 7.5.1.1.2.- Certificados SSL

#### 7.5.1.1.3.- Dns resolution

#### 7.5.1.1.4.- Técnicas intrusivas

#### 7.5.1.1.5.- Bruteforce

#### 7.5.1.1.6.- Permutación

#### 7.5.1.1.7.- Recursión

#### 7.5.1.1.8.- Registros dns

#### 7.5.1.1.9.- Análisis de código fuente

#### 7.5.1.1.10.- Js scraping

#### 7.5.1.1.11.- Técnicas de obtención de ip

### 7.5.2.- Técnicas Web

#### 7.5.2.1.1.- Web screen shot

#### 7.5.2.2.1.- Waf detection

#### 7.5.2.3.1.- Web vuln scan

#### 7.5.2.4.1.- Fuzzing

#### 7.5.2.5.1.- CMS scan

#### 7.5.2.6.1.- Directory enumeración

#### 7.5.2.7.1.- Crawler

#### 7.5.2.7.1.- Js análisis

#### 7.5.2.8.1.- Cors check

#### 7.5.2.10.1.- Check robots wayback

### 7.5.3.1.1.- Osint

#### 7.5.3.1.1.- Domain info(whois,resistant)

#### 7.5.3.2.1.- Metadata

#### 7.5.3.3.1.- Emails, users, data leaks

#### 7.5.3.4.1.- Google dorks

#### 7.5.3.5.1.- Gihub dorks

### 7.5.4- Explotación Aplicaciones Web

#### 7.5.4.1- SQL Injection

#### 7.5.4.2- Autenticacion

#### 7.5.4.3- Divulgación de información

#### 7.5.4.4- Broken Access Control

#### 7.5.4.5- IDOR

#### 7.5.4.6- Directory Traversal

#### 7.5.4.7- Server-side request Forgery (SSRF)

#### 7.5.4.8- XXE Injection

#### 7.5.4.9- Remote Code Execution

#### 7.5.4.10- BUSINESS LOGIC

#### 7.5.4.11 CSRF Cross Site Request For forgery

#### 7.5.4.12 WebSockets

#### 7.5.4.13- Cross Site Scripting

#### 7.5.4.14- DOM (Document Object Model)

#### 7.5.4.15- Click jacking

#### 7.5.4.16- CORS

#### 7.5.4.17- O-Auth

#### 7.5.4.18- Insecure Deserealization

#### 7.5.4.19- HTTP Request Smuggling

#### 7.5.4.20- Web Cache Poisoning

#### 7.5.4.21- Server Side Template Injection

#### 7.5.4.22- Web Cache Poisoning

#### 7.5.4.23- Attacking GraphQL

### 7.5.3- Post Explotación Aplicaciones Web
