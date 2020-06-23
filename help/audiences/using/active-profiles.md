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
source-git-commit: 4575c1152f1a33ff18b2200151346cc6e56b45fa
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 19%

---


# Perfis ativos{#active-profiles}

Adobe Campaign fornece um relatório que exibe o número de perfis ativos. Este relatório é apenas informativo, não tem impacto direto na cobrança. Somente os administradores podem acessar este relatório, em **[!UICONTROL Administration > Customer metrics]**.

![](assets/audience_active_profiles1.png)

O fluxo de trabalho **[!UICONTROL Billing]** técnico gera todos os meses um relatório contendo o número de perfis ativos que foram direcionados durante o último período acumulado de 12 meses.

Os perfis excluídos durante a preparação da entrega (regras de tipologia, quarentenas) não são levados em consideração. Um perfil que foi visado por várias entregas será contado apenas uma vez. Na parte inferior do relatório, você encontrará a lista de perfis ativos para cada targeting dimension.

![](assets/audience_active_profiles2.png)

Se estiver hospedado no AWS e usando o Campaign Standard da versão 10368, você também pode monitorar o número de perfis ativos usados em suas instâncias diretamente do Painel de controle. For more on this, refer to the [Control Panel documentation](https://docs.adobe.com/content/help/en/control-panel/using/performance-monitoring/active-profiles-monitoring.html).
