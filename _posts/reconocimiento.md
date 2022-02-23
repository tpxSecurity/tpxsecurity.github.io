---
title: "Reconocimiento"
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

Durante la fase de recolección de información o mejor conocido como reconocimiento, se basa en la recopilación de información sobre el sistema o infraestructura a auditar. El objetivo es identificar datos desconocidos o no proporcionados por ejemplo:

* Direcciones de IP
* Topología de la red
* Tecnologías utilizadas
* Versiones de librerias
* Dsispositivos red y más.

Ahora se mostraran las diferentes técnicas para realizar la recopilación de información:

## Análisis de subdominios

La enumeración de subdominios es el proceso para encontrar subdominios de un objetivo.
Para realizar este proceso se puede hacer uso de herramientas de internet como [dnsdumpster](https://dnsdumpster.com/), [RapidDNS](https://rapiddns.io/) entre otras, otra forma de enumeración es mediante Técnicas como:

1. [Pasivo](/posts/analisis-subdominios/#pasivo)
2. [Certificados SSL](/posts/analisis-subdominios/#certificados-ssl)
3. [Dns resolution](/posts/analisis-subdominios/#dns-resolution)
4. [Técnicas intrusivas](/posts/analisis-subdominios/#técnicas-intrusivas)
   * Bruteforce
   * Permutación
   * Recursión
5. [Registros dns](/posts/analisis-subdominios/#registros-dns)
6. [Análisis de código fuente](/posts/analisis-subdominios/#análisis-de-código-fuente-y-js-scraping)
7. [Js scraping](/posts/analisis-subdominios/#análisis-de-código-fuente-y-js-scraping)
8. [Técnicas de obtención de ip](/posts/analisis-subdominios/#técnicas-de-obtención-de-ip)
  
## Web

1. Web screen shot

    ```console
      firefox --display :11 https://tpx.mx
    ```

2. Waf detection

    ```console
      wafw00f https://tpx.mx
          
                    ______
                  /      \
                  (  W00f! )
                  \  ____/
                  ,,    __            404 Hack Not Found
              |`-.__   / /                      __     __
              /"  _/  /_/                       \ \   / /
              *===*    /                         \ \_/ /  405 Not Allowed
            /     )__//                           \   /
        /|  /     /---`                        403 Forbidden
        \\/`   \ |                                 / _ \
        `\    /_\\_              502 Bad Gateway  / / \ \  500 Internal Error
          `_____``-`                             /_/   \_\

                            ~ WAFW00F : v2.1.0 ~
            The Web Application Firewall Fingerprinting Toolkit
        
    [*] Checking https://tpx.mx
    [+] The site https://tpx.mx is behind Cloudflare (Cloudflare Inc.) WAF.
    [~] Number of requests: 2
    ```

3. [Web vuln scan](/posts/herramientas-analisis-vun-web/#escaneo-de-vulnerabilidades)
4. Fuzzing
5. CMS scan
6. Directory enumeración
7. Crawler
8. Github endpoints
9. Js análisis
10. Cors check
11. Check robots wayback

## Osint

OSINT (Open Source INTelligence) es el conjunto de técnicas y herramientas para recopilar información pública, analizar datos y correlacionar esa información, convirtiéndola en conocimiento útil.

1. [Domain info(whois,resistant)](/posts/Reccon-Osint/#domain-infowhois--whoxy-whoisxmlapi-dnslytics-resistant)
2. [Metadata](/posts/Reccon-Osint/#metadata)
3. [Emails, users, data leaks](/posts/Reccon-Osint/#data-leaks)
4. [Google dorks](/posts/Reccon-Osint/#google-dorks)
5. [Gihub dorks](/posts/Reccon-Osint/#gihub-dorks)
