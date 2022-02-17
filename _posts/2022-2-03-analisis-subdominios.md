---
title: "Análisis de subdominios"
author: "Julio Alberto Romo T"
date: 2022-2-03 23:22:00 +0800
categories: [Seguridad,Tecnicas]
tags: [Seguridad]

image:
  src: /assets/img/posts/subdominios.svg
  width: 800
  height: 500
  alt: Análisis de subdominios
---


## Análisis de subdominios

### Pasivo

La información se obtiene sin interacción directa con el objetivo mediante el uso de técnicas como búsquedas en Internet, rastreo de redes. Algunas de estas tecnicas involucran el uso de buscadores o indexadores de contenido.

Tecnica/Herramientas:

* Whois [ [Whoxy](https://www.whoxy.com), [Whoisxmlapi](https://www.whoisxmlapi.com), [Dnslytics](https://dnslytics.com/) ] (Obtener información acerca de los registradores de dominios, detectar dominios extra pertenecientes a la empresa).
* Host Info [ [Host.io](Host.io) ] (Obtenención de información de registros A, AAAA, MX, NS, TXT, CNAME).
* [CIDR Discover](https://www.manageengine.com/network-monitoring/faq/cidr.html)
* Subdomain Discovery [ [DNS Dumpster](https://dnsdumpster.com), [RapidDNS](https://rapiddns.io), [SubFinder](https://github.com/projectdiscovery/subfinder) ]
* [Wayback Machine](https://web.archive.org)
* [Amass](https://github.com/OWASP/Amass)
* [Urlscan.io](https://urlscan.io/)

### Certificados SSL

Un SSL (Secure Socket Layer) es un certificado digital que autentica un sitio web y habilita una conexión cifrada.

```console
root@tpx.mx:$ git clone https://github.com/drwetter/testssl.sh.git

Cloning into 'testssl.sh'...
remote: Enumerating objects: 13444, done.
remote: Counting objects: 100% (101/101), done.
remote: Compressing objects: 100% (74/74), done.
remote: Total 13444 (delta 51), reused 57 (delta 27), pack-reused 13343
Receiving objects: 100% (13444/13444), 83.05 MiB | 20.50 MiB/s, done.
Resolving deltas: 100% (8271/8271), done.

root@tpx.mx:$ cd testssl.sh

root@tpx.mx:$ ./testssl.sh tpx.mx
```

![SSL TEST](/assets/img/posts/ssl_testing.png)

### DNS resolution

Es un servicio que apunta el nombre de dominio a la IP del sitio web para que las personas puedan acceder fácilmente al sitio web a través del nombre de dominio registrado. Una dirección IP es una dirección numérica que identifica un sitio en la red. La resolución de dominio es el proceso de convertir nombres de dominio en direcciones IP.

```console
root@tpx.mx:$ nslookup tpx.mx
Server:         192.168.100.1
Address:        192.168.100.1#53

Non-authoritative answer:
Name:   tpx.mx
Address: 172.67.222.152
Name:   tpx.mx
Address: 104.21.25.37
Name:   tpx.mx
Address: 2606:4700:3037::6815:1925
Name:   tpx.mx
Address: 2606:4700:3030::ac43:de98
```

### Técnicas intrusivas

* Bruteforce
  
    Esta es una técnica en la que uno toma una larga lista de subdominios populares y les agrega su objetivo y, en función de la respuesta, determina si son válidos o no. Esto es similar al ataque de un diccionario.

    ```console
      root@tpx.mx:$ gobuster dns  -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -d tpx.mx
      ===============================================================
      Gobuster v3.1.0
      by OJ Reeves (@TheColonial) & Christian Mehlmauer (@firefart)
      ===============================================================
      [+] Domain:     tpx.mx
      [+] Threads:    10
      [+] Timeout:    1s
      [+] Wordlist:   /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt
      ===============================================================
      2022/02/08 16:27:48 Starting gobuster in DNS enumeration mode
      ===============================================================
      Found: info.tpx.mx           
      Found: i.tpx.mx              
      Found: www.tpx.mx            
      Found: c.tpx.mx
    ```

* Permutación

    Generar listas de subdominios mediante permutaciones (subdominios, bitsquat, guiones, repetición, omisión, reemplazo, transposición, adición, intercambio de vocales), para   comprobar a través de dns resolution si son subdominios válidos.

* Recursión

    Es la realización de diferentes variantes obtenidas de la permutación en la recursión se permite verificar si es correcta la información obtenida.

### Registros dns

Los registros DNS son varias cadenas de caracteres que se utilizan para indicar acciones a un servidor DNS. Estas letras también se conocen como sintaxis DNS.
  
```console
root@tpx.mx:$ dig tpx.mx all

; <<>> DiG 9.16.22-Debian <<>> tpx.mx all
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 16765
;; flags: qr rd ra; QUERY: 1, ANSWER: 2, AUTHORITY: 0, ADDITIONAL: 0

;; QUESTION SECTION:
;tpx.mx.                                IN      A

;; ANSWER SECTION:
tpx.mx.                 181     IN      A       104.21.25.37
tpx.mx.                 181     IN      A       172.67.222.152
```

### Análisis de código fuente y Js scraping

Es la depuración de código con el objetivo de encontrar errores y fallas en el código del sistema.
Se utilizan herramientas para examinar los archivos js(javascript) con el fin de obtener información de estos.

https://github.com/jaeles-project/gospider

## Tecnicas de obtención de ip

* Favicon ip

  Favicon es la imagen de la aplicación la cual si se convierte a md5 obtendremos un código el cual luego se realiza una búsqueda de ip con el md5 obtenido.

  ```console
    root@tpx.mx:$ git clone https://github.com/pielco11/fav-up.git
    Cloning into 'fav-up'...
    remote: Enumerating objects: 158, done.
    remote: Total 158 (delta 0), reused 0 (delta 0), pack-reused 158
    Receiving objects: 100% (158/158), 37.48 KiB | 590.00 KiB/s, done.
    Resolving deltas: 100% (80/80), done.

    root@tpx.mx:$ pip3 install -r requirements.txt
    root@tpx.mx:$ python3 favUp.py --favicon-file favicon.ico -sc -k SHODAN_API_KEY
  ```

* DNS Zone tranfers

  La transferencia de zona (en un servidor DNS) es el proceso de transferir información en el archivo de zona de un servidor de nombres principal a un servidor de nombres secundario. Este es uno de varios mecanismos disponibles para que los administradores repliquen la base de datos DNS en un conjunto de servidores DNS.
  
  ```console
  root@tpx.mx:$ nslookup tpx.mx
  Server:         192.168.100.1
  Address:        192.168.100.1#53

  Non-authoritative answer:
  Name:   tpx.mx
  Address: 172.67.222.152
  Name:   tpx.mx
  Address: 104.21.25.37
  Name:   tpx.mx
  Address: 2606:4700:3037::6815:1925
  Name:   tpx.mx
  Address: 2606:4700:3030::ac43:de98
  ```

* Subdomain takeover

  Si descubres algún dominio (dominio.tld) que está siendo utilizado por algún servicio dentro del ámbito pero la empresa ha perdido la propiedad del mismo, puedes intentar registrarlo (si es lo suficientemente barato) e informar a la empresa. Si este dominio está recibiendo alguna información sensible como una cookie de sesión a través del parámetro GET o en la cabecera Referer, esto es sin duda una vulnerabilidad.

* CDN/WAF FILTER

  * CDN:
      Una red de entrega de contenido (CDN) se compone de un grupo de servidores dispersos geográficamente que trabajan juntos para entregar contenido de Internet rápidamente.
  * WAF:
      WAF es un tipo de firewall que protege los servidores web contra ciberataques.

  ```console
    root@tpx.mx:$ wafw00f https://tpx.mx
        
                    ______
                  /      \
                  (  W00f! )
                  \  ____/
                  ,,    __            404 Hack Not Found
              |`-.__   / /                      __     __
              /"  _/  /_/                       \ \   / /
              *===*    /                          \ \_/ /  405 Not Allowed
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

* Test SSL

  Un ssl(Secure Socket Layer) es un certificado  digital que autentica un sitio web y habilita una conexión cifrada.
  Los certificados ssl se pueden usar para encontrar diferente nombres de dominio, para realiza esto se pude utilizar censys, crt.sh entre otros, esto para obtener los certificados de un nombre de dominio.

    ```console
    
      root@tpx.mx:$ sudo openssl s_client -connect www.tpx.mx:443    
      
      CONNECTED(00000003)
      depth=2 C = IE, O = Baltimore, OU = CyberTrust, CN = Baltimore CyberTrust Root
      verify return:1
      depth=1 C = US, O = "Cloudflare, Inc.", CN = Cloudflare Inc ECC CA-3
      verify return:1
      depth=0 C = US, ST = California, L = San Francisco, O = "Cloudflare, Inc.", CN = sni.cloudflaressl.com
      verify return:1

      ---
      Certificate chain
      0 s:C = US, ST = California, L = San Francisco, O = "Cloudflare, Inc.", CN = sni.cloudflaressl.com
        i:C = US, O = "Cloudflare, Inc.", CN = Cloudflare Inc ECC CA-3
      1 s:C = US, O = "Cloudflare, Inc.", CN = Cloudflare Inc ECC CA-3
        i:C = IE, O = Baltimore, OU = CyberTrust, CN = Baltimore CyberTrust Root
      ---
      Server certificate
      -----BEGIN CERTIFICATE-----
      MIIFLDCCBNGgAwIBAgIQChVX+vGLNwzYa8ejrM7QJDAKBggqhkjOPQQDAjBKMQsw
      CQYDVQQGEwJVUzEZMBcGA1UEChMQQ2xvdWRmbGFyZSwgSW5jLjEgMB4GA1UEAxMX
      Q2xvdWRmbGFyZSBJbmMgRUNDIENBLTMwHhcNMjEwNzA3MDAwMDAwWhcNMjIwNzA2
      MjM1OTU5WjB1MQswCQYDVQQGEwJVUzETMBEGA1UECBMKQ2FsaWZvcm5pYTEWMBQG
      A1UEBxMNU2FuIEZyYW5jaXNjbzEZMBcGA1UEChMQQ2xvdWRmbGFyZSwgSW5jLjEe
      MBwGA1UEAxMVc25pLmNsb3VkZmxhcmVzc2wuY29tMFkwEwYHKoZIzj0CAQYIKoZI
      zj0DAQcDQgAEbFdvMkFrATvvG8CcrYzm72omCNXpbKfHJIsIFy/lMON+9MlZohfO
      pJDBFmqHDSYIclC+G0ayj41mp7TfEZpM/KOCA2wwggNoMB8GA1UdIwQYMBaAFKXO
      N+rrsHUOlGeItEX62SQQh5YfMB0GA1UdDgQWBBR+R+6i1rBPF3qikMPFsFpDMyGa
      jjAyBgNVHREEKzApggZ0cHgubXiCCCoudHB4Lm14ghVzbmkuY2xvdWRmbGFyZXNz
      bC5jb20wDgYDVR0PAQH/BAQDAgeAMB0GA1UdJQQWMBQGCCsGAQUFBwMBBggrBgEF
      BQcDAjB7BgNVHR8EdDByMDegNaAzhjFodHRwOi8vY3JsMy5kaWdpY2VydC5jb20v
      Q2xvdWRmbGFyZUluY0VDQ0NBLTMuY3JsMDegNaAzhjFodHRwOi8vY3JsNC5kaWdp
      Y2VydC5jb20vQ2xvdWRmbGFyZUluY0VDQ0NBLTMuY3JsMD4GA1UdIAQ3MDUwMwYG
      Z4EMAQICMCkwJwYIKwYBBQUHAgEWG2h0dHA6Ly93d3cuZGlnaWNlcnQuY29tL0NQ
      UzB2BggrBgEFBQcBAQRqMGgwJAYIKwYBBQUHMAGGGGh0dHA6Ly9vY3NwLmRpZ2lj
      ZXJ0LmNvbTBABggrBgEFBQcwAoY0aHR0cDovL2NhY2VydHMuZGlnaWNlcnQuY29t
      L0Nsb3VkZmxhcmVJbmNFQ0NDQS0zLmNydDAMBgNVHRMBAf8EAjAAMIIBfgYKKwYB
      BAHWeQIEAgSCAW4EggFqAWgAdQBGpVXrdfqRIDC1oolp9PN9ESxBdL79SbiFq/L8
      cP5tRwAAAXqBa8KsAAAEAwBGMEQCIBElKR+Be7GguCw37OZ0SGpPYj4mOeQfJdnX
      J5siqdw6AiAXAhffZBJGd7S2AvTRcrlh9FGYODhmZ05sdt4Did47zAB2AFGjsPX9
      AXmcVm24N3iPDKR6zBsny/eeiEKaDf7UiwXlAAABeoFrwpkAAAQDAEcwRQIgFS6M
      C/Zt25W6sy6VNC7zMpIm//QFoLO2IttLjTX7mVcCIQC1Q2t0aSbaZ+phHSqvf9q3
      Vy5tIsqzv96MtAQufwE5vwB3AEHIyrHfIkZKEMahOglCh15OMYsbA+vrS8do8JBi
      lgb2AAABeoFrwoYAAAQDAEgwRgIhAO2IRHncuXw9p6Ugu85hApCKBJZkjpML+TYX
      m924KUSZAiEAx4w1Fz6YfmdSJkKgw2M3RrFIimHdUcp40b0ez7RLcoQwCgYIKoZI
      zj0EAwIDSQAwRgIhAO+H1y5wSrnD3K1WuCGfdtMaXsFkjhbaNxF6fVq94WsMAiEA
      /4R3j9iflj+taMcDTIRRrh0DpOPV0i1dhvw3CjVMoek=
      -----END CERTIFICATE-----
      subject=C = US, ST = California, L = San Francisco, O = "Cloudflare, Inc.", CN = sni.cloudflaressl.com

      issuer=C = US, O = "Cloudflare, Inc.", CN = Cloudflare Inc ECC CA-3
      ---
      No client certificate CA names sent
      Peer signing digest: SHA256
      Peer signature type: ECDSA
      Server Temp Key: X25519, 253 bits
      ---
      SSL handshake has read 2773 bytes and written 397 bytes
      Verification: OK
      ---
      New, TLSv1.2, Cipher is ECDHE-ECDSA-CHACHA20-POLY1305
      Server public key is 256 bit
      Secure Renegotiation IS supported
      Compression: NONE
      Expansion: NONE
      No ALPN negotiated
      SSL-Session:
          Protocol  : TLSv1.2
          Cipher    : ECDHE-ECDSA-CHACHA20-POLY1305
          Session-ID: 80C5CBCCD92FA162FE72887488F7964851408B73E2070B0105B05087348991FA
          Session-ID-ctx: 
          Master-Key: 3AC4C1713BECEDD88A825EDEDEBFC1EF43B1FF7DE6F13C181467C024FE20342FA93BFFFE79C7A3B69BAC263305222FA8
          PSK identity: None
          PSK identity hint: None
          SRP username: None
          TLS session ticket lifetime hint: 64800 (seconds)
          TLS session ticket:
          0000 - 55 71 d3 c0 2c 46 64 33-ed 9f 92 1b a5 6b 53 ed   Uq..,Fd3.....kS.
          0010 - 28 78 4a e2 14 a7 78 3a-33 03 4e d7 b4 ab b5 e0   (xJ...x:3.N.....
          0020 - da e9 b3 78 10 d3 43 c8-7a da 72 ed 88 1d ed a7   ...x..C.z.r.....
          0030 - bd 9d 3c 55 28 e3 35 d7-5b a3 48 d4 7e 4c 7d c9   ..<U(.5.[.H.~L}.
          0040 - 0e 53 82 e1 8b d4 b8 43-3c a8 3d e7 4e c1 d2 3b   .S.....C<.=.N..;
          0050 - 9e 1c cb 1e c6 11 c9 8e-33 91 ed bb 0a ed 57 73   ........3.....Ws
          0060 - 76 16 50 6a b1 31 e2 ef-13 7d 83 c2 20 60 b1 d1   v.Pj.1...}.. `..
          0070 - 38 9f 56 fb f7 8c ec 0e-a4 53 ae 27 6c 9d 56 83   8.V......S.'l.V.
          0080 - 9f 59 55 72 d2 89 59 12-a9 f6 6d 10 79 1b 55 34   .YUr..Y...m.y.U4
          0090 - 12 98 fc c3 96 85 a6 ce-b1 db 16 d2 a6 b1 0a 50   ...............P
          00a0 - b4 a2 11 ac 08 04 cd a4-34 e2 89 db 2d 65 88 20   ........4...-e. 
          00b0 - 1b 47 09 af 7d 8a 00 1c-08 72 03 ef 06 f0 de f2   .G..}....r......

          Start Time: 1644617480
          Timeout   : 7200 (sec)
          Verify return code: 0 (ok)
          Extended master secret: yes
      ---
    ```

* Testear puertos web comunes

  La verificación de puertos web es verificarlos puertos destinados al uso de las aplicaciones web a continuación se describirá el uso de cada puerto:

  Puerto 80: HTTP (Protocolo de transferencia de hipertexto)

  Puerto 443: SSL / HTTPS (Protocolo de transferencia de hipertexto seguro)

  Puerto 8080: Servicio de caché del World Wide Web (WWW)

    ```console
      root@tpx.mx:$ sudo nmap --script=http-enum.nse -p80,443,8080 tpx.mx 

      Starting Nmap 7.92 ( https://nmap.org ) at 2022-02-11 15:50 CST
      Nmap scan report for tpx.mx (172.67.222.152)
      Host is up (0.0097s latency).
      Other addresses for tpx.mx (not scanned): 104.21.25.37 2606:4700:3030::ac43:de98 2606:4700:3037::6815:1925

      PORT     STATE SERVICE
      80/tcp   open  http
      443/tcp  open  https
      8080/tcp open  http-proxy

      Nmap done: 1 IP address (1 host up) scanned in 97.02 seconds
    ```
