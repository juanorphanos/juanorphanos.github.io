---
layout: post
title: ISPM + ITDR con Entra ID y MDI
---

En Seguridad, y en particular en Seguridad de Identidades, detectar ataques sobre nuestras identidades es parte del trabajo, pero no la única. Uno de los grandes problemas suele ser como operar un ciclo continuo que combine las prácticas de IAM (Identity and Access Management), ISPM (Identity Security Posture Management) e ITDR (Identity Threat Detection and Response). 

## ¿Motivos? escoja su favorito

Podemos enumerar varios motivos de la complejidad de securizar nuestras identidades, una serie de blogs enorme. Sin embargo, a simple vista surgen varios aspectos de la gestión de identidades que hace dificil su tratamiento.

- Variedad de proveedores de identidad en la misma organización (no es extraño encontrar en la misma organización Okta, Active Directory, y varios tenants de Entra ID en paralelo, ni hablar de otros sistemas relacionados como ADFS, servicios de sincronización como Entra ID Connect (o Cloud Sync), MIM etc.
- Plataformas como Directorio Activo o las plataformas de sincronización suelen estar en el dominio del departamento de TI y no de Seguridad. (responsabilidad compartida).
- La Identidad es un servicio core en la red corporativa, cualquier cambio en la plataforma puede tener efectos a traves de varias aplicaciones, escenarios o usuarios.
- El universo de activos a proteger es enorme (usuarios, service pricipals, identidades de equipo-computer accounts, grupos de seguridad, secrets, keys, certificados etc).
- Inserte su propio motivo favorito aqui.

## MDI + Entra ID

Microsoft Defender for Identity, consolida señales desde diversas plataformas de identidad como Active Directory, Microsoft Entra ID, Okta, Active Directory Certificate Services, ADFS, servicios de Entra ID Connect, SailPoint o CyberArk.

<img width="1672" height="941" alt="image" src="https://github.com/user-attachments/assets/72d3c4c6-ddbf-44a7-ae6d-32013c7ef6ca" />

