---
title: "4.- Introducción a las pruebas de seguridad"
author: 
  name: Eduardo Rosales Meoño
  link: https://github.com/TishcaTpx
date: 2021-12-09 23:22:00 +0800
categories: [Seguridad]
tags: [Seguridad]
image:
  src: 
  width: 800
  height: 500
  alt: Introducción a las pruebas de seguridad
---

## 4.1.- Metodologías y estándares de pruebas de seguridad

* OSSTMM

    Ostmm (Metodología de prueba de código abierto) es un marco detallado bien conocido en la industria. Este marco ofrece un método científico para la prueba y la vulnerabilidad de la invasión de la red.
    La guía perfecta del equipo de desarrollo de redes y productos importantes determina la vulnerabilidad de la seguridad de la red.
    La metodología OSTMM permite un avance de las pruebas técnicas y de adaptación de la organización que corresponden a necesidades específicas. Las evaluaciones personales proporcionan una visión general de la seguridad de la red y las soluciones de confianza que toman las decisiones apropiadas. Esto es para proteger a su organización.

* OWASP

    El OWASP (Open Web Application Security Project) es otro estándar reconocido que permite a las organizaciones controlar las vulnerabilidades de las aplicaciones. Este framework ayuda a identificar vulnerabilidades en aplicaciones web y móviles. Al mismo tiempo, el OWASP también complica los defectos lógicos que surgen en las prácticas de desarrollo inseguras.
    La guía actualizada de OWASP proporciona más de 66 controles para identificar y evaluar vulnerabilidades con numerosas funcionalidades que se encuentran en las últimas aplicaciones. Sin embargo, equipa a las organizaciones con los recursos para asegurar sus aplicaciones y posibles pérdidas comerciales. Al aprovechar el estándar OWASP en la evaluación de seguridad, el hacker ético garantiza vulnerabilidades casi nulas. Además, también mejora las recomendaciones realistas a características y tecnologías específicas en las aplicaciones.

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

## 4.2.- Fases de una prueba de seguridad.

Una **prueba de penetración** ( también conocida como pentest), se lleva acabo bajo una metodología que permite identificar las vulnerabilidades que afectan el sistema o aplicación (o aquello que se audite), mediante la explotación controlada de estas, con el fin de entregar un reporte que ayude a remediar y mejorar la seguridad de la información.

En esta sección, aprenderemos sobre las pruebas de penetración y lo que implican.

* [Reconocimiento](/posts/reconocimiento):  
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
