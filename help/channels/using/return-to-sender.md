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
TQID: https://experienceleague.adobe.com/g-0yLI3-qYRfbF-gXuO8AtyCI3Qr5F7an5hqVzaQCE8
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 214
ht-degree: 2%

---

# Retornar ao remetente{#return-to-sender}

São compatíveis trocas de arquivos simples com provedores de Correspondência direta incorporando informações Retornar para o remetente. Isso permite que os endereços postais correspondentes sejam excluídos de comunicações futuras. Isso também permite que você seja notificado sobre um endereço incorreto e interaja com o cliente por meio de outros canais ou incentivá-lo a atualizar seu endereço postal.

Por exemplo, um contato foi movido para um novo local e não forneceu seu novo endereço postal. O provedor recupera a lista de endereços incorretos e envia essas informações à Adobe Campaign, que automaticamente exibe os endereços incorretos.

Para que essa funcionalidade funcione, o template do delivery padrão de correspondência direta inclui, no conteúdo, a ID do log de delivery. Assim, o Adobe Campaign poderá sincronizar o perfil e os dados do delivery com as informações retornadas pelo provedor.

![](assets/direct_mail_return_sender_1.png)

Um modelo de importação está disponível em **[!UICONTROL Adobe Campaign > Resources > Templates > Import templates > Update Direct Mail quarantines and delivery logs]**. Duplique este template para criar o seu próprio template. Para obter mais informações sobre o uso de modelos de importação, consulte [Uso de modelos de importação](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates).

![](assets/direct_mail_return_sender_2.png)

Quando a importação é concluída, o Adobe Campaign executa automaticamente as seguintes ações:

* Endereços incorretos são adicionados ao incluo na lista de bloqueios no nível do perfil
* Os indicadores principais de delivery (KPIs) são atualizados
* Os logs do delivery são atualizados
