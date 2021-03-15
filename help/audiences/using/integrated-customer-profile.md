---
solution: Campaign Standard
product: campaign
title: Perfil de cliente integrado
description: '“Rastreie todas as interações do cliente em uma única visualização: O perfil de cliente integrado do Adobe Campaign é atualizado durante todo o ciclo de vida do cliente.”'
audience: audiences
content-type: reference
topic-tags: managing-profiles
context-tags: marketingHistory,main
feature: Perfis
role: Profissional
level: Iniciante
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 48%

---


# Perfil de cliente integrado{#integrated-customer-profile}

Um perfil de cliente integrado está disponível para cada contato do banco de dados. Este histórico de marketing combina todas as informações de marketing relevantes relacionadas ao contato com um cliente em uma única visualização. Em seguida, você pode acessar todos os comportamentos digitais e as transações online e offline em um local central: informações de contato, emails recebidos, logs de rastreamento, assinaturas e cancelamento de assinatura etc.

Para acessar o perfil do cliente integrado, siga estas etapas:

1. Na página inicial do Adobe Campaign, clique no cartão **[!UICONTROL Customer profiles]** ou na guia **Profiles** para exibir a lista de perfis.

1. Para pesquisar um perfil com base em um campo específico, abra o painel de pesquisa e selecione o campo no qual deseja realizar a pesquisa.


   ![](assets/profile-search.png)

1. Especifique o valor que deseja pesquisar e pressione Enter.

   >[!NOTE]
   >
   >Observe que as pesquisas podem ser executadas com base nos campos de email, nome e sobrenome, bem como nos campos personalizados que foram adicionados ao estender o recurso.
   >
   >As pesquisas fazem distinção entre maiúsculas e minúsculas e são executadas somente em prefixos. Por exemplo, você não poderá procurar um perfil usando as últimas letras do seu sobrenome.

1. Selecione um contato para abrir seu perfil.

   ![](assets/mkt_hist_access.png)

Em seguida, você pode acessar o **Histórico de marketing** desse contato.

As informações principais sobre o perfil estão agrupadas nesta página, bem como a lista de eventos.

Clique em um evento na lista para abri-lo: é possível acessar as mensagens enviadas ou os serviços aos quais o perfil se inscreveu.

![](assets/mkt_hist_view.png)

>[!NOTE]
>
>Também é possível acessar o Histórico de marketing usando a API do Adobe Campaign Standard. Para obter mais informações, consulte a [documentação dedicada](../../api/using/interacting-with-marketing-history.md).
