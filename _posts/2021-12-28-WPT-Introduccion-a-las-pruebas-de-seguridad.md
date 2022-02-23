---
title: "4.- Introducción a las pruebas de seguridad"
author: 
  name: Eduardo Rosales Meoño
date: 2021-12-28 00:00:00 +0000
categories: [Seguridad]
tags: [Seguridad]
image:
  src: /assets/img/7f81085e1dc317d445db7d06780e0e17.png
  width: 800
  height: 500
  alt: Introducción a las pruebas de seguridad
---

## 4.1.- Metodologías y estándares de pruebas de seguridad

* OSSTMM

    Ostmm (Metodología de prueba de código abierto) Esta metodologia se relaciona con la seguridad operativa. Se basa en el conocimiento y la medición de las operaciones de seguridad empresarial. Con la ayuda del método OSSTMM, las auditorías de seguridad pueden obtener una comprensión más profunda de cómo se conectan las cosas.

    Esta metodología está dividida en 4 grupos clave:

    El alcance: Se define un proceso que recolecta de información en todos los bienes en el ambiente objetivo.

    El canal: Nos determinar el tipo de comunicación e interacción que habrá con los bienes los cuales pueden ser físicos, espectros y comunicativos. Todos estos canales representan un único set de los componentes de seguridad y deben ser testados y verificados durante el periodo de evaluación.

    El índice: Clasifica bienes objetivo que se corresponde con sus particulares identificaciones como la dirección MAC o la dirección IP.
    
    El vector: Se concluye en qué dirección puede el perito informático evaluar y analizar cada bien funcional.


* OWASP

    El OWASP (Open Web Application Security Project) Es una técnica de auditoría web de seguridad abierta y colaborativa que se centra en el análisis de seguridad de las aplicaciones web y se utiliza como referencia para las auditorías de seguridad. Todas las auditorías de seguridad web se basan en los métodos de auditoría de OWASP para analizar y evaluar los riesgos.

* NIST

    El NIST (National Institute of Standards and Technology) varía los manuales de seguridad informática que difieren de otros manuales de seguridad de la información. En cierto modo, NIST ofrece pautas más específicas intrínsecas a las pruebas de penetración para mejorar la ciberseguridad general de una organización.
    La mayoría de las organizaciones y socios con sede en Estados Unidos deben cumplir con el cumplimiento normativo del framework NIST. Además, el estándar garantiza la seguridad de la información en industrias como la banca, las comunicaciones y la energía.
    Existe la probabilidad de personalizar los estándares para satisfacer tus necesidades específicas. Significativamente, NIST contribuye a la innovación de seguridad en las industrias estadounidenses.
    Para cumplir con los estándares NIST, las organizaciones deben realizar pruebas de penetración en sus aplicaciones y redes. Sin embargo, las organizaciones deben seguir pautas preestablecidas. Estas pautas aseguran que las organizaciones cumplan con sus obligaciones de seguridad cibernética y mitigan los riesgos de posibles ataques cibernéticos.

* PTES

    El PTES (Penetration Testing Methodologies and Standards) recomienda un enfoque estructurado para una prueba de penetración. Por un lado, el PTES te guía a través de las fases de las pruebas de penetración, comenzando con las fases de comunicación, recopilación de información y modelado de amenazas. Por otro lado, los hackers éticos se familiarizan con los procesos de la organización. Esto también ayuda a identificar las áreas más vulnerables que son propensas a los ataques.
    PTES proporciona pautas posteriores a la explotación a los pentester. Si es necesario, pueden validar la corrección exitosa de vulnerabilidades previamente identificadas. El estándar tiene siete fases que garantizan pruebas de penetración exitosas con recomendaciones en las que confiar.

* ISSAF

    El ISSAF (Information System Security Assessment Framework) es un enfoque especializado y estructurado para las pruebas de penetración. Más importante aún, el framework proporciona metodologías avanzadas que están personalizadas para el contexto.
    Estos estándares le permiten al pentester planificar y ejecutar cada paso del proceso de prueba de penetración. Por lo tanto, satisface todos los requisitos del proceso de prueba de penetración. Como hacker ético, si estás utilizando diferentes herramientas, ISSAF es un framework crucial. Por ejemplo, vincula cada paso a una herramienta específica y, por lo tanto, reduce la complejidad.
    ISSAF ofrece información adicional sobre varios vectores de ataque, así como el resultado de la vulnerabilidad después de la explotación. Toda esta información permite a los evaluadores planificar un ataque avanzado que garantiza beneficios al tiempo que protege los sistemas de los ataques cibernéticos.

## 4.2.- Fases de una prueba de seguridad

Una **prueba de penetración** ( también conocida como pentest), se lleva acabo bajo una metodología que permite identificar las vulnerabilidades que afectan el sistema o aplicación (o aquello que se audite), mediante la explotación controlada de estas, con el fin de entregar un reporte que ayude a remediar y mejorar la seguridad de la información.

En esta sección, aprenderemos sobre las pruebas de penetración y lo que implican.

* [Reconocimiento](/posts/WPT-Auditoria-orientada-a-entornos-Web/#751--reconocimiento-aplicaciones-web):  
    La fase de recolección de información o mejor conocida como reconocimiento,se basa el la recopilación de información sobre el sistema o infraestructura a auditar. El objetivo es recolectar un cantidad inmensa de datos, la cual sera utilizada posteriormente.

* Busqueda de vulnerabilidades:  
    Un escaneo de vulnerabilidades es una práctica de seguridad que escanea un sistema en busca de vulnerabilidades potenciales que puedan ser utilizadas por un atacante.

* Explotación:  
    La fase de explotación es el proceso de atacar al objetivo. Esta fase consta de varios pasos que se centran realizar una explotación a los serviciós del objetivo, para lograr la ejecución de código y obtener arbitrario restricciones al sistema.

* Post-Explotación:  
    La post explotación es una fase del proceso de pruebas de penetración la cual  se realiza una vez se logra obtener un acceso mediante la explotación, esta fase realiza con el fin de obtener un mayor privilegio al obtenido anteriormente.

* Reporte:  
    Tras la finalización de las fases, se realiza un entregable en el cual se muestra lo realizado, ademas de los descubrimiento o vulnerabilidades detectadas.

## 4.3.- Caja blanca, Caja negra y Caja gris

**Caja negra (“Black Box”):** se basan en que los pentesters no disponen de conocimiento previo acerca de la infraestructura que va a ser probada. Es el tipo de test de intrusión más parecido a un ataque real. Suele ser realizado por personal especializado externo a las organizaciones.

**Caja blanca (“White Box”):** se trata del test más completo ya que se parte de un conocimiento completo previo de la infraestructura a ser probada. Normalmente lo realiza personal interno de las organizaciones o se contrata a alguien externo si la empresa no dispone de trabajadores especializados.

**Caja gris (“Grey Box”):** se parte de un conocimiento parcial previo de la infraestructura objetivo del test. Suele ser el tipo de pentest recomendado cuando se contrata a empresas especializadas.
