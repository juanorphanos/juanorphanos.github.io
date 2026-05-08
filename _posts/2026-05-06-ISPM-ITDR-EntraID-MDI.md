---
layout: post
title: ISPM + ITDR con Entra ID y MDI
---

Este será el primero de una serie de blog posts relacionados a un tema clave en Seguridad: Seguridad de Identidades, y en particular dos prácticas que cada dia tienen mas relevancia se van formalizando: ITDR e ISPM.

En Seguridad, y en particular en Seguridad de Identidades, detectar ataques sobre nuestras identidades es parte del trabajo, pero no la única. Uno de los grandes problemas suele ser como operar un ciclo continuo que combine las prácticas de IAM (Identity and Access Management), ISPM (Identity Security Posture Management) e ITDR (Identity Threat Detection and Response). 

## ISPM y ITDR

ISPM (Identity Security Posture Management) se refiere a la capacidad de identificar configuraciones debiles, exposición y malas prácticas en los sistemas de identidades. Es una práctica principalmente proactiva. Pensemos en preguntas como:
- ¿Tengo cuentas privilegiadas expuestas? ¿ hay delegaciones potencialmente peligrosas?
- ¿Existen configuraciones inseguras como NTLMv1 o LDAP sin cifrar?
- ¿Estoy usando MFA en todos mis usuarios cloud?
- ¿Estoy adoptando medidas contra ataques AiTM como Phishing Resitant MFA?
- Las Configuraciones de mi entidad certificadora, ¿me dejan expuesto a vulnerabilidades "ESC"?
- ¿Hay configuraciones inseguras en mi Entra ID Connect?

Por otro lado cuando nos referimos a ITDR (Identity Threat Detection and Response) es la práctica de proteger, prevenir, detectar, responder y mitigar ataques basados en identidad. Es un esfuerzo compartido entre los equipos de seguridad (principalmente SOC) e identidades.
Responde a cuestiones tales como:
- Detección de password filtradas en la web
- ¿Hay inicios de sesión anormales/riesgosos?
- Detectar actividad de movimiento lateral
- Descubrir caminos de movimiento lateral
- Revocar sesiones, forzar MFA, resetear password o bloquear acceso de forma automatica para contener.
- Correlación de señales de Identidad, Endpoint, Correo y Aplicaciones.


## ¿Motivos? escoja su favorito

Podemos enumerar varios motivos de la complejidad de securizar nuestras identidades, una serie de blogs enorme. Sin embargo, a simple vista surgen varios aspectos de la gestión de identidades que hace dificil su tratamiento.

- Variedad de proveedores de identidad en la misma organización (no es extraño encontrar en la misma organización Okta, Active Directory, y varios tenants de Entra ID en paralelo, ni hablar de otros sistemas relacionados como ADFS, servicios de sincronización como Entra ID Connect (o Cloud Sync), MIM etc.
- Plataformas como Directorio Activo o las plataformas de sincronización suelen estar en el dominio del departamento de TI y no de Seguridad. (responsabilidad compartida).
- La Identidad es un servicio core en la red corporativa, cualquier cambio en la plataforma puede tener efectos a traves de varias aplicaciones, escenarios o usuarios.
- El universo de activos a proteger es enorme (usuarios, service pricipals, identidades de equipo-computer accounts, grupos de seguridad, secrets, keys, certificados etc).
- Inserte su propio motivo favorito aqui.

## MDI + Entra ID

Microsoft Defender for Identity, consolida señales desde diversas plataformas de identidad como Active Directory, Microsoft Entra ID, Okta, Active Directory Certificate Services, ADFS, servicios de Entra ID Connect, SailPoint o CyberArk.

<img alt="image" src="https://raw.githubusercontent.com/juanorphanos/juanorphanos.github.io/refs/heads/master/images/ITDR.png" />

### Mapeo de features de Entra ID/MDI a ISPM

| Funcionalidad | Relación con ISPM | Ejemplos de recomendaciones o señales |
|---|---|---|
| Microsoft Entra Recommendations | Evalúa la configuración del tenant contra best practices de MS, y genera recomendaciones accionables. (Se ve en el portal de Entra ID) |Cobertura de MFA, legacy authentication, configuraciones débiles, etc|
| Identity Secure Score | Métricas de seguridad que expresan en un porcentaje el cumplimiento de configuraciones alineado a las recomendaciones de MS. (se ven en el portal de Defender) | MFA, Conditional Access, SSPR, etc |
| Conditional Access Coverage dashboard | Recomendaciones de cobertura de Conditional Access en portal de Entra ID  Apps sin proteger, usuarios sin cobertura, policy summary, etc |

