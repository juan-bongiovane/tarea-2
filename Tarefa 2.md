# Tarea 2

### **Vulnerabilidad *M5: Comunicación Insegura**

**Puesta en producción segura.**

**Docente: José Fernández Gómez**

**Alumno: Juan Pablo Bongiovane Amado**

[TOC]

## **Introducción**

La Open Web Application Security Project (OWASP) es una fundación sin fines de lucro que se dedica a mejorar las aplicaciones web y móviles. La OWASP genera una lista de los 10 principales riesgos más comunes que se encuentran en aplicaciones móviles.

Los 10 principales riesgos móviles se actualizan periódicamente. En el año 2023, en la lista Beta 3, se enumeraron los siguientes riesgos:

- M1: Uso Incorrecto de Credenciales
- M2: Seguridad Inadecuada en la Cadena de Suministro
- M3: Autenticación/Autorización Insegura
- M4: Validación Insuficiente de Entrada/Salida
- M5: Comunicación Insegura
- M6: Controles de Privacidad Inadecuados
- M7: Protecciones Binarias Insuficientes
- M8: Configuración de Seguridad Incorrecta
- M9: Almacenamiento Inseguro de Datos
- M10: Criptografía Insuficiente

En esta tarea, analizaremos la vulnerabilidad M5, que se refiere a las comunicaciones inseguras.

## **Análisis de Vulnerabilidades**

La vulnerabilidad M5 Insecure Communication se refiere a las comunicaciones inseguras. Un agente de amenaza que escuche una transmisión puede interceptar y modificar los datos si son transmitidos en texto sin formato o utilizando un protocolo obsoleto. Los motivos principales son el robo de información confidencial, realizar espionaje, robo de identidad, etc.

Los siguientes agentes de amenaza son un adversario que comparte su red local o WIFI comprometida o monitoreada. Dispositivos de red local u operadores no autorizados, como enrutadores, torres de telefonía móvil, proxy, etc., y malware en su dispositivo móvil.

Abarcan todas las tecnologías de comunicación que pueden utilizar los dispositivos móviles: TCP/IP, WiFi, Bluetooth/Bluetooth-LE, NFC, audio, infrarrojos, GSM, 3G, SMS, etc.

Todos los problemas de comunicaciones TLS, NFC, Bluetooth y WIFI.

Los riesgos habituales de una comunicación insegura están relacionados con la integridad de los datos, la confidencialidad de los datos y la integridad del origen. Los datos pueden ser modificados cuando están en tránsito sin ser detectados utilizando un ataque de intermediario. Los datos confidenciales pueden exponerse, apoderarse o ser observados mientras ocurren y atacar más tarde. Otro problema es no validar correctamente una conexión TLS, utilizando cifrados débiles, no verificar los certificados u otros problemas de configuración.

## **Escenarios**

Existen algunos escenarios comunes que se descubren con frecuencia en las inspecciones de seguridad en las comunicaciones de la aplicación móvil, se detallarán tres de los principales escenarios.

##### **Omisión de autenticación de dos factores**

La aplicación móvil recibe un identificador de sesión desde un punto final a través de canales no seguros en lugar de SSL/TLS, permitiendo a un adversario eludir la capa adicional de seguridad proporcionada por la autenticación de dos factores al inicio de sesión.

Un atacante puede aprovechar esta vulnerabilidad interceptando el tráfico entre la aplicación móvil y el punto final. Una vez que el atacante tiene el identificador de sesión, puede utilizarlo para acceder a la aplicación como si fuera el usuario legítimo.

Para mitigar este riesgo, las aplicaciones móviles deben implementar una variedad de métodos de 2FA, como códigos de verificación enviados por SMS, tokens de seguridad físicos o aplicaciones de terceros para autenticación. Además, deben utilizar cifrado para proteger el tráfico entre la aplicación y el punto final.

##### **Fuga de información de credenciales**

Las aplicaciones móviles transmiten las credenciales de los usuarios a un punto final a través de canales no seguros en lugar de SSL/TLS. Esto permite a un adversario interceptar esas credenciales en texto sin cifrar, obteniendo las credenciales del usuario, como nombre de usuario y contraseña.

Esto se produce por no utilizar un protocolo de seguridad seguro, como SSL/TLS, no implementar correctamente el cifrado de las credenciales o la utilización de protocolos de seguridad obsoletos o inseguros.

Una vez que el atacante tiene las credenciales del usuario, puede utilizarlas para acceder a la cuenta o servicio del usuario.

Para mitigar esto, se deben utilizar contraseñas seguras y únicas para cada cuenta, activar la autenticación de dos factores cuando esté disponible y estar atento a signos de phishing y otros ataques de seguridad.

##### **Negociación de apretón de manos débil**

Cuando la aplicación se conecta con el punto final, necesitan acordar un tipo de cifrado para que la conexión sea segura. El cliente y el servidor negocian el uso de cifrado débil. Esto provoca que un cifrado débil sea fácil de descifrar para un atacante, poniendo en peligro la confidencialidad de la comunicación.

Esta situación puede ocurrir porque los dispositivos no son compatibles con un cifrado más fuerte, equipos configurados incorrectamente o un atacante puede engañar a los dispositivos para utilizar un cifrado débil por error.

##### **Recreación de la vulnerabilidad elegida**

No se logró realizar la recreación de la vulnerabilidad.

##### Bibliografía

- [OWASP Mobile Top 10 2023 - M5: Insecure Communication](https://owasp.org/www-project-mobile-top-10/2023-risks/m5-insecure-communication)
- [OWASP Mobile Top 10 2023 - M5: Insecure Communication (Detalles)](https://owasp.org/www-project-mobile-top-10/2023-risks/m5-insecure-communication.html)
- [OWASP Web Security Testing Guide - Fingerprint Web Server](https://owasp.org/www-project-web-security-testing-guide/v42/4-Web_Application_Security_Testing/01-Information_Gathering/02-Fingerprint_Web_Server)
- [OWASP Testing Guide v4 (PDF)](https://owasp.org/www-project-web-security-testing-guide/assets/archive/OWASP_Testing_Guide_v4.pdf)
