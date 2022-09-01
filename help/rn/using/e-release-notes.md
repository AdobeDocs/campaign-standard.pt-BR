---
title: Notas de versão anteriores
description: Notas de versão anteriores
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: 471c0e66f1742346798f61ed8e8912695e9c95b6
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Notas de versão anteriores {#e-new-release}

Esta página descreve aprimoramentos e correções incluídos na próxima versão do Campaign Standard.

>[!CAUTION]
>
> Esse conteúdo está sujeito a alterações sem aviso prévio até a data de atualização dos ambientes de estágio. Saiba mais na [página de planejamento de versão](../../rn/using/release-planning.md).

## Versão 22.3 - Setembro de 2022 {#e-rn-2022}

<!--
### Improvement{#e-rn-improvements}

**Accessibility**

Campaign Standard 22.3 comes with accessibility fixes and improvements which facilitate users to navigate and get the most out of Adobe Campaign.

These capabilities are released in Limited Availability and rolled out to a set of customers only. To have these improvements enabled on your Campaign environment(s), contact your Adobe representative.


* **Data retention**

    Data retention periods have been reduced to avoid overloading Campaign server. However, you can still modify these values and define a custom period of time based on your needs and data retention policies. To change retention periods, contact Adobe.
-->

### Atualização de segurança{#e-rn-security}

Esta versão vem com a seguinte atualização de segurança: O Apache Tomcat foi atualizado da v7.0 para a v8.0.

### Correções{#e-rn-fixes}

* Correção de um problema com relatórios agendados, que eram acionados uma hora antes do tempo agendado. (CAMP-51502)
* Correção de um problema nos Indicadores de delivery no Painel de delivery que não correspondia aos Logs de envio (nms:broadLogRcp). (CAMP-51127)
* Correção de um problema que impedia a extensão de recursos personalizados com o ACS Connector (Prime Offering). (CAMP-51033)
* Aprimorado o processo de publicação de respostas de solicitações de Privacidade para evitar atraso. (CAMP-50613)