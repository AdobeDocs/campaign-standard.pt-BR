---
title: Sobre aceitação e recusa no Campaign
description: A opção de não participação resulta em um perfil não sendo mais direcionado por qualquer delivery ou por deliveries de um canal específico.
audience: audiences
content-type: reference
topic-tags: understanding-opt-in-and-opt-out-processes
feature: Audiences
role: User
level: Beginner
exl-id: ccb35aeb-2b32-4444-969b-50021111a0d6
TQID: 'https://experienceleague.adobe.com/9fzQiPrBRAFlTxX5EKo-Qvph3nYZYoA29kMrm6cXVLs'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: afa4204e-6d08-4e29-bc35-26aafb656d48
    internal-label: Profiles and audiences
subfeature_v2:
  - id: d6330382-c886-4f7a-a4f7-74e3f36c0d9c
    internal-label: Audiences
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 10%
---
# Sobre aceitação e recusa no Campaign{#about-opt-in-and-opt-out-in-campaign}

A opção de não participação resulta em um perfil não sendo mais direcionado por qualquer delivery ou por deliveries de um canal específico.

Para conceder aos perfis a capacidade de aceitar ou recusar, é necessário criar uma página de aterrissagem dedicada. Para obter mais informações, consulte [Configuração de páginas de aterrissagem de aceitação e recusa](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#setting-up-opt-in-and-opt-out-landing-pages).

Os perfis também podem ser aceitos ou recusados manualmente por um operador. Para obter mais informações, consulte [Gerenciamento de aceitação e recusa em um perfil](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#managing-opt-in-and-opt-out-from-a-profile).

Os perfis de recusa são excluídos automaticamente durante a análise de entrega para acelerar as entregas (a taxa de erro tem um efeito significativo na velocidade de entrega).

>[!NOTE]
>
>A recusa se aplica a **Perfis**, em vez da quarentena que está vinculada a um **endereço de email** ou **número de telefone**. Portanto, a recusa de um perfil excluirá dos deliveries todos os endereços vinculados a ele. No entanto, se um usuário tiver dois perfis no banco de dados, ele ainda será direcionado pelos deliveries, pois somente um de seus perfis será recusado. Para garantir que todos os endereços sejam excluídos, adicione-os aos endereços em quarentena. Para obter mais informações, consulte [esta página](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-the-entire-platform).

Para obter mais informações sobre assinaturas de serviços, consulte [esta página](../../audiences/using/about-subscriptions.md).
