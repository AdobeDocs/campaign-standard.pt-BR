---
title: Conceitos do modelo de dados
description: Saiba mais sobre o modelo de dados do Adobe Campaign e como modificá-lo.
audience: developing
content-type: reference
topic-tags: about-custom-resources
context-tags: cusResource,overview;eventCusResource,overview
feature: Data Model
role: Developer
level: Experienced
exl-id: 6e9e016a-473b-4a51-8bd6-c23c7b3d3610
TQID: https://experienceleague.adobe.com/jOKJ64oRWaLCf7C9V8ZTbrtSphd4cJrGLlyw0K4sFB8
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 251
ht-degree: 79%

---

# Conceitos do modelo de dados{#data-model-concepts}

O Adobe Campaign vem com um modelo de dados predefinido. Ele pode ser modificado pelos [administradores](../../administration/using/users-management.md#functional-administrators) que podem adicionar novos recursos ou extensões aos recursos existentes.

>[!CAUTION]
>
>A criação e a modificação de recursos são operações confidenciais que só devem ser realizadas por especialistas.

O menu **[!UICONTROL Administration]** > **[!UICONTROL Development]**, acessado pelo logotipo do Adobe Campaign, permite gerenciar os **recursos personalizados**, **publicá-los** e **acessar as ferramentas de diagnóstico**.

Os dados usados pelo Adobe Campaign são definidos com recursos diferentes. Você pode **aprimorar o modelo de dados** criando recursos personalizados, como tabelas de produtos ou de compras.

Os recursos integrados (como campanhas, emails ou públicos-alvos) não podem ser modificados. Entretanto, os recursos personalizados podem ser estendidos para adicionar novos campos.

Os campos de extensão são gerados com um prefixo para não entrarem em conflito com os campos integrados.

>[!NOTE]
>
>Você pode encontrar uma representação de modelo de dados para os recursos internos em [esta página](../../developing/using/datamodel-introduction.md).

Você também pode [configurar a navegação](configuring-the-screen-definition.md) nas telas correspondentes ao recurso criado.

É possível **exportar e importar** recursos personalizados, por exemplo, de um ambiente de desenvolvimento para um de produção. Para saber mais, consulte este [caso de uso detalhado](../../automating/using/exporting-importing-custom-resources.md).

>[!CAUTION]
>
>Somente [administradores](../../administration/using/users-management.md#functional-administrators) funcionais, com função **[!UICONTROL Administration]** e acesso a **Todas** unidades, podem acessar logs de envio, logs de mensagens, logs de rastreamento, de exclusão ou de assinatura. Um usuário não administrador pode direcionar esses logs, mas começando por uma tabela vinculada (perfis, delivery).
