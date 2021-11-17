---
title: Retornar ao remetente
description: Saiba como ser notificado de um endereço incorreto e excluí-lo de comunicações futuras.
audience: channels
content-type: reference
topic-tags: direct-mail
feature: Direct Mail
role: User
level: Intermediate
exl-id: 6783aa68-7fd7-4f53-86bf-853c0fea5899
source-git-commit: 8be43668d1a4610c3388ad27e493a689925dc88c
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 2%

---

# Retornar ao remetente{#return-to-sender}

Há suporte para trocas de arquivos simples com provedores de Correspondência direta incorporando informações Retornar para o remetente. Isso permite que endereços postais correspondentes sejam excluídos de futuras comunicações. Isso também permite que você seja notificado sobre um endereço incorreto e interaja com o cliente por meio de outros canais ou incentive-o a atualizar seu endereço postal.

Por exemplo, um contato foi movido para um novo local e não lhe forneceu o novo endereço postal. O provedor recupera a lista de endereços incorretos e envia essas informações para a Adobe Campaign, que lista de bloqueios automaticamente os endereços incorretos.

Para que essa funcionalidade funcione, o template do delivery padrão da correspondência direta inclui, no conteúdo, a ID de log do delivery. Assim, o Adobe Campaign poderá sincronizar o perfil e os dados do delivery com as informações retornadas pelo provedor.

![](assets/direct_mail_return_sender_1.png)

Um template de importação está disponível em **[!UICONTROL Adobe Campaign > Resources > Templates > Import templates > Update Direct Mail quarantines and delivery logs]**. Duplique esse template para criar o seu próprio. Para obter mais informações sobre o uso de templates de importação, consulte [Uso de templates de importação](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates).

![](assets/direct_mail_return_sender_2.png)

Quando a importação é concluída, o Adobe Campaign executa automaticamente as seguintes ações:

* Endereços incorretos são adicionados à lista de bloqueios no nível do perfil
* Os indicadores principais de delivery (KPIs) são atualizados
* Os logs do delivery são atualizados
