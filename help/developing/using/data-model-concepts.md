---
solution: Campaign Standard
product: campaign
title: Conceitos do modelo de dados
description: Saiba mais sobre o modelo de dados do Adobe Campaign e como modificá-lo.
audience: developing
content-type: reference
topic-tags: about-custom-resources
context-tags: cusResource,overview;eventCusResource,overview
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 84%

---


# Conceitos do modelo de dados{#data-model-concepts}

O Adobe Campaign vem com um modelo de dados predefinido. Ele pode ser modificado pelos [administradores](../../administration/using/users-management.md#functional-administrators) que podem adicionar novos recursos ou extensões aos recursos existentes.

>[!CAUTION]
>
>A criação e a modificação de recursos são operações confidenciais que só devem ser realizadas por especialistas.

O menu **[!UICONTROL Administration]** > **[!UICONTROL Development]**, acessado pelo logotipo do Adobe Campaign, permite gerenciar os **recursos personalizados**, **publicá-los** e **acessar as ferramentas de diagnóstico**.

Os dados usados pelo Adobe Campaign são definidos com recursos diferentes. Você pode **aprimorar o template de dados** criando recursos personalizados, como tabelas de produtos ou de compras.

Os recursos incorporados (como campanhas, emails ou públicos) não podem ser modificados. Entretanto, os recursos personalizados podem ser estendidos para adicionar novos campos.

Os campos de extensão são gerados com um prefixo para não entrarem em conflito com os campos incorporados.

>[!NOTE]
>
>Uma representação de modelo de dados para os recursos incorporados está disponível [nesta página](../../developing/using/datamodel-introduction.md).

Você também pode [configurar a navegação](configuring-the-screen-definition.md) nas telas correspondentes ao recurso criado.

É possível **exportar e importar** recursos personalizados, por exemplo, de um ambiente de desenvolvimento para um de produção. Para saber mais, consulte este [caso de uso detalhado](../../automating/using/exporting-importing-custom-resources.md).

>[!CAUTION]
>
>Somente os [administradores](../../administration/using/users-management.md#functional-administrators) funcionais, com a função **[!UICONTROL Administration]** e o acesso a **Todas** unidades podem acessar registros de envio, registros de mensagens, logs de rastreamento, exclusão ou registros de subscrições. Um usuário não administrativo pode público alvo desses registros, mas iniciando em uma tabela vinculada (perfis, delivery).
