---
title: Sobre aceitação e exclusão no Campaign
seo-title: Sobre aceitação e exclusão no Campaign
description: Sobre aceitação e exclusão no Campaign
seo-description: Recusar (ou lista negra) resulta em um perfil não sendo mais direcionado por qualquer entrega ou por entregas de um canal específico.
page-status-flag: nunca ativado
uuid: 501 d 9485-976 b -4 de 7-b 242-6886 f 2814 c 6 c
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: públicos-alvo
content-type: reference
topic-tags: entendendo os processos de participação e opt-out
discoiquuid: 2 f 26 ec 22-0809-4541-b 2 a 1-e 84 ff 868 ba 6 e
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# About opt-in and opt-out in Campaign{#about-opt-in-and-opt-out-in-campaign}

Recusar (ou lista negra) resulta em um perfil não sendo mais direcionado por qualquer entrega ou por entregas de um canal específico.

Para conceder perfis a possibilidade de aceitar ou recusar, é necessário criar uma página de aterrissagem dedicada. For more on this, refer to [Setting up opt-in and opt-out landing pages](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#setting-up-opt-in-and-opt-out-landing-pages).

Os perfis também podem ser admitidos ou enviados manualmente por um operador. For more on this, refer to [Managing opt-in and opt-out from a profile](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#managing-opt-in-and-opt-out-from-a-profile).

Os perfis de opção são excluídos automaticamente durante a análise de entrega para acelerar as entregas (a taxa de erro tem um efeito significativo na velocidade de entrega).

>[!NOTE]
>
>Opt-out applies to **Profiles**, as opposed to quarantine which is linked to an **email address** or **phone number**. Portanto, recusar um perfil excluirá de entregas todos os endereços vinculados a ela. Se um usuário tiver dois perfis no banco de dados, ele ainda será direcionado por entregas, pois apenas um dos perfis é cancelado. Para garantir que todos os adições sejam excluídos, adicione-os aos endereços de quarentena. For more on this, refer to [this page](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-the-entire-platform).

For more on services subscriptions, refer to [this page](../../audiences/using/about-subscriptions.md).
