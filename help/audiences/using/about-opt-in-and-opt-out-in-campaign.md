---
title: Sobre participação e não participação no Campaign
description: A opção de não participação resulta em um perfil que não é mais direcionado por nenhum delivery ou por delivery de um canal específico.
page-status-flag: never-activated
uuid: 501d9485-976b-4de7-b242-6886f2814c6c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: understanding-opt-in-and-opt-out-processes
discoiquuid: 2f26ec22-0809-4541-b2a1-e84ff868ba6e
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 9%

---


# Sobre participação e não participação no Campaign{#about-opt-in-and-opt-out-in-campaign}

A opção de não participação resulta em um perfil que não é mais direcionado por nenhum delivery ou por delivery de um canal específico.

Para dar aos perfis a capacidade de opt in ou opt out, é necessário criar uma landing page dedicada. Para obter mais informações, consulte [Configuração de landings page](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#setting-up-opt-in-and-opt-out-landing-pages)de aceitação e não participação.

Os perfis também podem ser opt in ou removidos manualmente por um operador. Para obter mais informações, consulte [Gerenciamento de participação e não participação de um perfil](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#managing-opt-in-and-opt-out-from-a-profile).

Os perfis de opção são excluídos automaticamente durante a análise do delivery para acelerar os delivery (a taxa de erro tem um efeito significativo na velocidade do delivery).

>[!NOTE]
>
>A opção de não participação se aplica a **Perfis**, em vez de quarentena vinculada a um endereço **de** email ou número **de** telefone. Opt out um perfil excluirá, portanto, dos delivery todos os endereços a ele vinculados. Se um usuário tiver dois perfis no banco de dados, ele ainda será alvo de delivery, pois apenas um de seus perfis é a opção de não participação. Para garantir que todos os seus endereços sejam excluídos, adicione-os aos endereços das quarentenas. Para obter mais informações, consulte [esta página](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-the-entire-platform).

For more on services subscriptions, refer to [this page](../../audiences/using/about-subscriptions.md).
