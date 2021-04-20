---
solution: Campaign Standard
product: campaign
title: Sobre participação e não participação no Campaign
description: A recusa resulta em um perfil que não é mais direcionado por qualquer delivery ou delivery de um canal específico.
audience: audiences
content-type: reference
topic-tags: understanding-opt-in-and-opt-out-processes
feature: Audiences
role: Business Practitioner
level: Beginner
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 9%

---


# Sobre participação e não participação no Campaign{#about-opt-in-and-opt-out-in-campaign}

A recusa resulta em um perfil que não é mais direcionado por qualquer delivery ou delivery de um canal específico.

Para dar aos perfis a capacidade de aceitar ou rejeitar, é necessário criar uma página de aterrissagem dedicada. Para obter mais informações, consulte [Configuração de landing pages de opt-in e opt-out](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#setting-up-opt-in-and-opt-out-landing-pages).

Os perfis também podem ser aceitos ou rejeitados manualmente por um operador. Para obter mais informações, consulte [Gerenciamento de participação e não participação de um perfil](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#managing-opt-in-and-opt-out-from-a-profile).

Os perfis de cancelamento são excluídos automaticamente durante a análise de delivery para acelerar os deliveries (a taxa de erro tem um efeito significativo na velocidade do delivery).

>[!NOTE]
>
>A recusa se aplica a **Profiles**, em vez de quarentena que está vinculada a um **endereço de email** ou **número de telefone**. A recusa de um perfil excluirá dos deliveries todos os endereços vinculados a ele. Se um usuário tiver dois perfis no banco de dados, ele ainda será direcionado por deliveries, pois apenas um desses perfis é de opt out. Para garantir que todos os endereços sejam excluídos, adicione-os aos endereços em quarentena. Para obter mais informações, consulte [esta página](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-the-entire-platform).

Para obter mais informações sobre assinaturas de serviços, consulte [esta página](../../audiences/using/about-subscriptions.md).
