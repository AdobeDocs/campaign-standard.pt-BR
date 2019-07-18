---
title: Retornar ao remetente
seo-title: Retornar ao remetente
description: Retornar ao remetente
seo-description: Saiba como ser notificado sobre um endereço incorreto e excluí-lo de futuras comunicações.
page-status-flag: nunca ativado
uuid: 11981 c 2 f -0 b 7 f -4166-9 daa-ec 6 a 6 b 4 d 5367
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canais
content-type: reference
topic-tags: direta
discoiquuid: 5 f 20 ff 3 f -8242-4735-8 c 60-c 57610 edff 52
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 855db33971afdf9f02bf1b00be67c9e3f50bee06

---


# Return to sender{#return-to-sender}

Há suporte para trocas de arquivos simples com fornecedores de Correspondência direta incorporando informações Retornar para remetente. Isso permite que endereços postais correspondentes sejam excluídos de comunicações futuras. Isso também permite que você seja notificado sobre um endereço incorreto e interaja com o cliente por meio de outros canais ou para incentivá-lo a atualizar seu endereço postal.

Por exemplo, um contato foi movido para um novo lugar e não fornece seu novo endereço postal. O provedor recupera a lista de endereços errôneos e envia essas informações para o Adobe Campaign, que lista automaticamente os endereços errôneos.

Para que essa funcionalidade funcione, o modelo de entrega padrão de mala direta incluirá, no conteúdo, a ID do log de entrega. Assim, o Adobe Campaign será capaz de sincronizar os dados de perfil e entrega com as informações retornadas pelo provedor.

![](assets/direct_mail_return_sender_1.png)

An import template is available under **[!UICONTROL Adobe Campaign > Resources > Templates > Import templates > Update Direct Mail quarantines and delivery logs]**. Duplique esse modelo para criar os seus próprios. For more on using import templates, refer to [Using import templates](../../automating/using/defining-import-templates.md).

![](assets/direct_mail_return_sender_2.png)

Quando a importação é feita, o Adobe Campaign realiza automaticamente as seguintes ações:

* Os endereços incorretos estão na lista negra no nível do perfil
* Os indicadores principais de entrega (kpis) são atualizados
* Os logs de entrega são atualizados

