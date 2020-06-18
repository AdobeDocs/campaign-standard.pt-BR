---
title: Retornar ao remetente
description: Saiba como ser notificado sobre um endereço incorreto e excluí-lo de comunicações futuras.
page-status-flag: never-activated
uuid: 11981c2f-0b7f-4166-9daa-ec6a6b4d5367
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: direct-mail
discoiquuid: 5f20ff3f-8242-4735-8c60-c57610edff52
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 012546e109b085b7ed968bcefa8f76482656ae0d
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 2%

---


# Retornar ao remetente{#return-to-sender}

Há suporte para trocas de arquivos simples com provedores de mala direta incorporando informações de Retorno ao remetente. Isso permite que endereços postais correspondentes sejam excluídos de futuras comunicações. Isso também permite que você seja notificado sobre um endereço incorreto e interaja com o cliente por meio de outros canais ou para incentivá-lo a atualizar seu endereço postal.

Por exemplo, um contato mudou-se para um novo local e não lhe forneceu seu novo endereço postal. O provedor recupera a lista de endereços errôneos e envia essas informações para a Adobe Campaign que adiciona automaticamente à lista de blocos os endereços errados.

Para que essa funcionalidade funcione, o template do delivery padrão de mala direta inclui, no conteúdo, a ID de log de delivery. Assim, o Adobe Campaign poderá sincronizar os dados do perfil e do delivery com as informações retornadas pelo provedor.

![](assets/direct_mail_return_sender_1.png)

Um template de importação está disponível em **[!UICONTROL Adobe Campaign > Resources > Templates > Import templates > Update Direct Mail quarantines and delivery logs]**. Duplicado este modelo para criar seu próprio. Para obter mais informações sobre como usar templates de importação, consulte [Uso de templates de importação](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates).

![](assets/direct_mail_return_sender_2.png)

Quando a importação é feita, o Adobe Campaign executa automaticamente as seguintes ações:

* Endereços incorretos são adicionados à lista de blocos no nível do perfil
* Os indicadores principais do delivery (KPIs) são atualizados
* Os logs do delivery são atualizados

