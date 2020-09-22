---
title: Perfis ativos
description: Você pode acessar um relatório dedicado sobre métricas do cliente e visualizar perfis ativos no banco de dados de Campanhas.
page-status-flag: never-activated
uuid: ee8ac493-c297-49ca-aed4-3976d8a685a4
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-profiles
discoiquuid: e029213f-0b65-41b1-8adf-34fa813b0c70
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c1147c4512b1485ae5d927a32970adcd41b540e7
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 11%

---


# Perfis ativos{#active-profiles}

A Adobe Campaign fornece um relatório que exibe o número de perfis ativos. Este relatório é apenas informativo, não tem impacto direto na cobrança. Somente os administradores podem acessar este relatório, em **[!UICONTROL Administration > Customer metrics]**.

![](assets/audience_active_profiles1.png)

>[!NOTE]
>
>Se você estiver hospedado no AWS e usando o Campaign Standard da compilação 10368, também poderá monitorar o número de perfis ativos usados em suas instâncias diretamente do Painel de controle do Campaign. Para obter mais informações, consulte a [documentação do Painel de controle do Campaign](https://docs.adobe.com/content/help/pt-BR/control-panel/using/performance-monitoring/active-profiles-monitoring.html).
>
>Observe que a métrica perfis ativos está disponível e é relevante apenas para instâncias **de** marketing. Não é aplicável nem está disponível para Instância de execução, o que significa ocorrências de MID (mid-sourcing) e RT (Message Center / Real-time messaging).


Os perfis que foram excluídos durante a preparação do delivery (regras de tipologia, quarentenas, grupos de controle) não são tidos em conta. Um perfil que foi direcionado por vários deliveries será contado apenas uma vez. Na parte inferior do relatório, você encontrará a lista de perfis ativos para cada targeting dimension.

Este relatório é gerado todos os meses pelo fluxo de trabalho **[!UICONTROL Billing]** técnico. Ele contém o número de perfis ativos direcionados durante o último período de rolagem de 12 meses.

Observe que os perfis que foram excluídos durante a preparação do delivery (regras de tipologia, quarentenas) não são considerados. Além disso, um perfil que foi alvo de vários delivery só será contado uma vez.

![](assets/audience_active_profiles2.png)

Na parte inferior do relatório, você encontrará a lista de perfis ativos processados pelo fluxo de trabalho de cobrança:

* A **[!UICONTROL NmsRecipient]** fonte inclui todos os clientes que foram contatados usando informações de seus perfis de Campaign Standard.

* Por outro lado, os clientes que foram direcionados usando apenas uma informação específica (endereço de e-mail, número de telefone), sem relação com o perfil da Campanha, aparecerão na **[!UICONTROL anonymous]** fonte.
