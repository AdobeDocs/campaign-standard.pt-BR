---
solution: Campaign Standard
product: campaign
title: Perfis ativos do Campaign
description: Saiba como acessar métricas do cliente e perfis ativos
feature: Perfis
role: Business Practitioner
level: Intermediate
exl-id: 22516348-7695-4579-99eb-480e5b723ccc
source-git-commit: d30ce292ca07b9eb0b6965e47e12ddd4e24041ad
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 17%

---

# Perfis ativos{#active-profiles}

Os administradores funcionais de campanha podem acessar o relatório **[!UICONTROL Customer metrics]** de **[!UICONTROL Administration > Customer metrics]**.

![](assets/audience_customer_metrics.png)

Este relatório é gerado todos os meses pelo workflow técnico **[!UICONTROL Billing]** e exibe o número de **perfis ativos**.

Um &quot;Perfil&quot; é um registro de informações que representam um cliente final, um prospecto ou um cliente potencial. Os perfis são considerados **ativos** se tiverem sido direcionados por um delivery de Campanha nos últimos 12 meses por meio de qualquer canal.

De acordo com seu contrato, cada uma das instâncias do Campaign é provisionada com um número específico de perfis ativos. Consulte seu contrato de licença para obter uma referência sobre o número de perfis ativos adquiridos.

![](assets/audience_active_profiles_list.png)

Os perfis excluídos durante a preparação do delivery (por regras de tipologia ou mecanismo de quarentena, por exemplo) não são considerados. Um perfil que foi direcionado por vários deliveries será contado apenas uma vez. Este relatório é apenas informativo, não tem impacto direto na cobrança.

>[!NOTE]
>
>Como um usuário administrador, você também pode monitorar o número de perfis ativos usados em suas instâncias diretamente do Painel de controle do Campaign. Para obter mais informações, consulte a [documentação do Painel de controle do Campaign](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html?lang=pt-BR#performance-monitoring).

