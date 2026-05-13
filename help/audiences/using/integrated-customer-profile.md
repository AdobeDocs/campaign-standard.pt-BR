---
title: Perfil de cliente integrado
description: 'Rastreie todas as interações do cliente em uma única visualização: o perfil de cliente integrado da Adobe Campaign é atualizado durante todo o ciclo de vida do cliente.'
audience: audiences
content-type: reference
topic-tags: managing-profiles
context-tags: marketingHistory,main
feature: Profiles
role: User
level: Beginner
exl-id: cf3c6408-7fa0-423a-b34b-f4fee771fb47
TQID: https://experienceleague.adobe.com/a-v47cX0DxN6dzLQs-r4e2yMajLD6GHIVXXEX9Ol-lY
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 282
ht-degree: 41%

---

# Perfil de cliente integrado{#integrated-customer-profile}

Um perfil de cliente integrado está disponível para cada contato do banco de dados. Este histórico de marketing combina todas as informações de marketing relevantes relacionadas ao contato com um cliente em uma única visualização. Em seguida, você pode acessar todos os comportamentos digitais e as transações online e offline em um local central: informações de contato, emails recebidos, logs de rastreamento, assinaturas e cancelamento de assinatura etc.

Para acessar o perfil do cliente integrado, siga estas etapas:

1. Na home page do Adobe Campaign, clique no cartão **[!UICONTROL Customer profiles]** ou na guia **Perfis** para exibir a lista de perfis.

1. Para pesquisar um perfil com base em um campo específico, abra o painel de pesquisa e selecione o campo no qual deseja realizar a pesquisa.


   ![](assets/profile-search.png)

1. Especifique o valor que deseja pesquisar e pressione Enter.

   >[!NOTE]
   >
   >Observe que as pesquisas podem ser executadas com base nos campos de email, nome e sobrenome, bem como em campos personalizados que foram adicionados ao estender o recurso.
   >
   >As pesquisas diferenciam maiúsculas de minúsculas e são executadas somente em prefixos. Por exemplo, você não poderá procurar um perfil usando as últimas letras do nome.

1. Selecione um contato para abrir seu perfil.

   ![](assets/mkt_hist_access.png)

Em seguida, você pode acessar o **Histórico de marketing** desse contato.

As informações principais sobre o perfil estão agrupadas nesta página, bem como a lista de eventos.

Clique em um evento na lista para abri-lo: você pode acessar as mensagens que foram enviadas ou os serviços aos quais o perfil se inscreveu.

![](assets/mkt_hist_view.png)

>[!NOTE]
>
>Também é possível acessar o Histórico de marketing usando a API do Adobe Campaign Standard. Para obter mais informações, consulte a [documentação dedicada](../../api/using/interacting-with-marketing-history.md).
