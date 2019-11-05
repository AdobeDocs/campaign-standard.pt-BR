---
title: Retornar ao remetente
description: Saiba como ser notificado sobre um endereço incorreto e excluí-lo de comunicações futuras.
page-status-flag: nunca ativado
uuid: 11981c2f-0b7f-4166-9daa-ec6a6b4d5367
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: canais
content-type: referência
topic-tags: correio direto
discoiquuid: 5f20ff3f-8242-4735-8c60-c57610edff52
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Retornar ao remetente{#return-to-sender}

Há suporte para trocas de arquivos simples com provedores de Mala direta incorporando informações de Retorno ao remetente. Isso permite que endereços postais correspondentes sejam excluídos de futuras comunicações. Isso também permite que você seja notificado sobre um endereço incorreto e interaja com o cliente por meio de outros canais ou para incentivá-lo a atualizar seu endereço postal.

Por exemplo, um contato mudou-se para um novo local e não lhe forneceu seu novo endereço postal. O provedor recupera a lista de endereços incorretos e envia essas informações para o Adobe Campaign, que automaticamente faz a lista negra dos endereços incorretos.

Para que essa funcionalidade funcione, o modelo de entrega padrão de mala direta inclui, no conteúdo, a ID do log de entrega. Assim, o Adobe Campaign poderá sincronizar o perfil e os dados de entrega com as informações retornadas pelo provedor.

![](assets/direct_mail_return_sender_1.png)

Um modelo de importação está disponível em **[!UICONTROL Adobe Campaign > Resources > Templates > Import templates > Update Direct Mail quarantines and delivery logs]**. Duplique este modelo para criar seu próprio. Para obter mais informações sobre como usar modelos de importação, consulte [Uso de modelos](../../automating/using/defining-import-templates.md)de importação.

![](assets/direct_mail_return_sender_2.png)

Quando a importação é concluída, o Adobe Campaign executa automaticamente as seguintes ações:

* Endereços incorretos são bloqueados no nível do perfil
* Os indicadores principais de entrega (KPIs) são atualizados
* Os registros de entrega são atualizados

