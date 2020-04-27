---
title: Conceitos do modelo de dados
description: Saiba mais sobre o modelo de dados Adobe Campaign e como modificá-lo.
page-status-flag: never-activated
uuid: cacd563f-6936-4b3e-83e3-5d4ae31d44e8
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: about-custom-resources
discoiquuid: 4e0468da-3052-4ce5-8174-45aba1f5c4ed
context-tags: cusResource,overview;eventCusResource,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 8852adb5edeb42eba1acf2911c988071104f1401

---


# Conceitos do modelo de dados{#data-model-concepts}

O Adobe Campaign vem com um modelo de dados predefinido. Esse modelo de dados pode ser modificado por [administradores](../../administration/using/users-management.md#functional-administrators) que podem adicionar novos recursos ou extensões aos recursos existentes.

>[!CAUTION]
>
>Criar e modificar recursos são operações confidenciais que devem ser executadas somente por usuários especialistas.

O menu **[!UICONTROL Administration]** > **[!UICONTROL Development]** , acessado pelo logotipo do Adobe Campaign, permite gerenciar seus recursos **** personalizados, **publicá** -los e **acessar as ferramentas** de diagnóstico.

Os dados usados pelo Adobe Campaign são definidos por meio de diferentes recursos. Você pode **aprimorar o modelo** de dados fornecido criando seus próprios recursos personalizados, como tabelas de produtos ou de compras.

Os recursos incorporados (como campanha, e-mails ou audiência) não podem ser modificados. Entretanto, os recursos personalizados podem ser estendidos para adicionar novos campos.

Os campos de extensão são gerados com um prefixo para que nunca entrem em conflito com os campos incorporados.

>[!NOTE]
>
>Você pode encontrar uma representação de modelo de dados para os recursos incorporados [desta página](../../developing/using/datamodel-introduction.md).

Você também pode [configurar a navegação](configuring-the-screen-definition.md) nas telas correspondentes ao recurso criado.

É possível **exportar e importar** recursos personalizados, por exemplo de um desenvolvimento para um ambiente de produção. Para obter mais informações, consulte este caso [de uso passo a](../../automating/using/exporting-importing-custom-resources.md)passo.
