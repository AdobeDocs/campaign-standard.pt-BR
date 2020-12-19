---
solution: Campaign Standard
product: campaign
title: Sobre participação e não participação no Campaign
description: A opção de não participação resulta em um perfil que não é mais direcionado por nenhum delivery ou por delivery de um canal específico.
audience: audiences
content-type: reference
topic-tags: understanding-opt-in-and-opt-out-processes
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 9%

---


# Sobre participação e não participação no Campaign{#about-opt-in-and-opt-out-in-campaign}

A opção de não participação resulta em um perfil que não é mais direcionado por nenhum delivery ou por delivery de um canal específico.

Para dar aos perfis a capacidade de opt in ou opt out, é necessário criar uma landing page dedicada. Para obter mais informações, consulte [Configuração de landings page de aceitação e não participação](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#setting-up-opt-in-and-opt-out-landing-pages).

Os perfis também podem ser opt in ou removidos manualmente por um operador. Para obter mais informações, consulte [Gerenciar aceitação e não participação de um perfil](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#managing-opt-in-and-opt-out-from-a-profile).

Os perfis de opção são excluídos automaticamente durante a análise do delivery para acelerar os delivery (a taxa de erro tem um efeito significativo na velocidade do delivery).

>[!NOTE]
>
>A opção de não participação se aplica a **Perfis**, em vez de à quarentena vinculada a um **endereço de email** ou **número de telefone**. Opt out um perfil excluirá, portanto, dos delivery todos os endereços a ele vinculados. Se um usuário tiver dois perfis no banco de dados, ele ainda será alvo de delivery, pois apenas um de seus perfis é a opção de não participação. Para garantir que todos os seus endereços sejam excluídos, adicione-os aos endereços das quarentenas. Para obter mais informações, consulte [esta página](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-the-entire-platform).

Para obter mais informações sobre subscrições de serviços, consulte [esta página](../../audiences/using/about-subscriptions.md).
