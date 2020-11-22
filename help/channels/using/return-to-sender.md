---
solution: Campaign Standard
product: campaign
title: Retornar ao remetente
description: Saiba como ser notificado sobre um endereço incorreto e excluí-lo de comunicações futuras.
audience: channels
content-type: reference
topic-tags: direct-mail
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 2%

---


# Retornar ao remetente{#return-to-sender}

Há suporte para trocas de arquivos simples com provedores de mala direta incorporando informações de Retorno ao remetente. Isso permite que endereços postais correspondentes sejam excluídos de futuras comunicações. Isso também permite que você seja notificado sobre um endereço incorreto e se envolva com o cliente por meio de outros canais ou para incentivá-lo a atualizar seu endereço postal.

Por exemplo, um contato mudou-se para um novo local e não lhe forneceu seu novo endereço postal. O provedor recupera a lista de endereços incorretos e envia essas informações para a Adobe Campaign, que lista de bloqueios automaticamente os endereços incorretos.

Para que essa funcionalidade funcione, o template do delivery padrão de mala direta inclui, no conteúdo, a ID de log de delivery. Assim, a Adobe Campaign poderá sincronizar os dados do perfil e do delivery com as informações retornadas pelo provedor.

![](assets/direct_mail_return_sender_1.png)

Um template de importação está disponível em **[!UICONTROL Adobe Campaign > Resources > Templates > Import templates > Update Direct Mail quarantines and delivery logs]**. Duplicado este modelo para criar seu próprio. Para obter mais informações sobre como usar templates de importação, consulte [Uso de templates de importação](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates).

![](assets/direct_mail_return_sender_2.png)

Quando a importação é feita, a Adobe Campaign executa automaticamente as seguintes ações:

* Endereços incorretos são adicionados lista de bloqueios no nível do perfil
* Os indicadores principais do delivery (KPIs) são atualizados
* Os logs do delivery são atualizados
