---
solution: Campaign Standard
product: campaign
title: Perfis ativos
description: Você pode acessar um relatório dedicado sobre as métricas do cliente e visualizar perfis ativos no banco de dados do Campaign.
audience: audiences
content-type: reference
topic-tags: managing-profiles
feature: Perfis
role: Profissional
level: Intermediário
translation-type: tm+mt
source-git-commit: 7979d8fd88b93a1cdd7b5a11bb66e894ab12f1c2
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 12%

---


# Perfis ativos{#active-profiles}

O Adobe Campaign fornece um relatório que exibe o número de perfis ativos. Este relatório é apenas informativo, não tem impacto direto na cobrança. Somente administradores podem acessar esse relatório, em **[!UICONTROL Administration > Customer metrics]**.

![](assets/audience_active_profiles1.png)

>[!NOTE]
>
>Se você estiver usando o Campaign Standard da build 10368, também poderá monitorar o número de perfis ativos usados em suas instâncias diretamente do Painel de controle do Campaign. Para obter mais informações, consulte a [documentação do Painel de controle do Campaign](https://docs.adobe.com/content/help/pt-BR/control-panel/using/performance-monitoring/active-profiles-monitoring.html).
>
>Observe que a métrica Perfis ativos está disponível e é relevante somente para **Instâncias de marketing**. Não é aplicável nem está disponível para instâncias de Execução, ou seja, instâncias de MID (mid-sourcing) e RT (Centro de mensagens/Mensagens em tempo real).

Os perfis excluídos durante a preparação do delivery (regras de tipologia, quarentenas, grupos de controle) não são considerados. Um perfil que foi direcionado por vários deliveries será contado apenas uma vez. Na parte inferior do relatório, você encontrará a lista de perfis ativos para cada targeting dimension.

Este relatório é gerado todos os meses pelo workflow técnico **[!UICONTROL Billing]**. Ele contém o número de perfis ativos que foram direcionados durante os últimos 12 meses do período.

Observe que os perfis excluídos durante a preparação do delivery (regras de tipologia, quarentenas) não são considerados. Além disso, um perfil que foi direcionado por vários deliveries será contado apenas uma vez.

![](assets/audience_active_profiles2.png)

Na parte inferior do relatório, você encontrará a lista de perfis ativos processados pelo workflow de cobrança:

* A fonte **[!UICONTROL NmsRecipient]** inclui todos os clientes que foram contatados usando informações de seu perfil do Campaign Standard.

* Por outro lado, os clientes que foram direcionados usando apenas uma parte específica das informações (endereço de email, número de telefone), sem relação com o perfil do Campaign, ficarão na fonte **[!UICONTROL anonymous]**.
