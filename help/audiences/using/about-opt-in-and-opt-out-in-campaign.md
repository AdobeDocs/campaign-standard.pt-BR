---
title: Sobre participação e não participação no Campaign
description: A recusa (ou a lista negra) resulta em um perfil que não é mais direcionado por nenhuma entrega ou por entregas de um canal específico.
page-status-flag: nunca ativado
uuid: 501d9485-976b-4de7-b242-6886f2814c6c
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: referência
topic-tags: processos de aceitação-participação e opção-não-participação
discoiquuid: 2f26ec22-0809-4541-b2a1-e84ff868ba6e
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Sobre participação e não participação no Campaign{#about-opt-in-and-opt-out-in-campaign}

A recusa (ou a lista negra) resulta em um perfil que não é mais direcionado por nenhuma entrega ou por entregas de um canal específico.

Para dar aos perfis a capacidade de aceitar ou rejeitar, é necessário criar uma página de aterrissagem dedicada. Para obter mais informações, consulte [Configuração de páginas](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#setting-up-opt-in-and-opt-out-landing-pages)iniciais de aceitação e não participação.

Os perfis também podem ser optados ou removidos manualmente por um operador. Para obter mais informações, consulte [Gerenciamento de participação e não participação em um perfil](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#managing-opt-in-and-opt-out-from-a-profile).

Os perfis de não participação são excluídos automaticamente durante a análise de entrega para acelerar as entregas (a taxa de erro tem um efeito significativo na velocidade de entrega).

>[!NOTE]
>
>A opção de não participação se aplica a **Perfis**, em vez de quarentena, vinculada a um endereço **de** email ou número **de** telefone. A recusa de um perfil excluirá, portanto, das entregas todos os endereços vinculados a ele. Se um usuário tiver dois perfis no banco de dados, ele ainda será direcionado por entregas, pois apenas um de seus perfis é a opção de não participação. Para certificar-se de que todos os seus endereços sejam excluídos, adicione-os aos endereços das quarentena. Para obter mais informações, consulte [esta página](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-the-entire-platform).

For more on services subscriptions, refer to [this page](../../audiences/using/about-subscriptions.md).
