---
solution: Campaign Standard
product: campaign
title: Perfis ativos do Campaign
description: Saiba como acessar métricas do cliente e perfis ativos
feature: Perfis
role: Business Practitioner
level: Intermediate
exl-id: 22516348-7695-4579-99eb-480e5b723ccc
source-git-commit: d2fcf2ca22bb5fe3632280f922dfed0972f6eb09
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 11%

---

# Métricas do cliente {#customer-metrics}

Os administradores funcionais de campanha podem acessar o relatório **[!UICONTROL Customer metrics]** de **[!UICONTROL Administration > Customer metrics]**.

![](assets/audience_active_profiles1.png)

Este relatório exibe:

* a Experience Cloud ID
* a IMS Organization ID
* o número de **perfis ativos**
* a lista de targeting dimensions disponíveis na instância

Este relatório é gerado todos os meses pelo workflow técnico **[!UICONTROL Billing]**.

## Perfis ativos{#active-profiles}

De acordo com seu contrato, cada uma das instâncias do Campaign é provisionada com um número específico de perfis ativos. Consulte seu contrato de licença para obter uma referência sobre o número de perfis ativos adquiridos.

>[!NOTE]
>
>Como um usuário administrador, você também pode monitorar o número de perfis ativos usados em suas instâncias diretamente do Painel de controle do Campaign. Para obter mais informações, consulte a [documentação do Painel de controle do Campaign](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html?lang=pt-BR#performance-monitoring).


Um &quot;Perfil&quot; é um registro de informações que representam um cliente final, um prospecto ou um cliente potencial. Os perfis são considerados **ativos** se tiverem sido direcionados por um delivery de Campanha nos últimos 12 meses por meio de qualquer canal. Os perfis excluídos durante a preparação do delivery (por regras de tipologia ou mecanismo de quarentena, por exemplo) não são considerados. Um perfil que foi direcionado por vários deliveries será contado apenas uma vez. Este relatório é apenas informativo, não tem impacto direto na cobrança.

![](assets/audience_active_profiles2.png)

Na parte inferior do relatório, você encontrará a lista de perfis ativos para cada targeting dimension. Ele mostra o número de perfis ativos que foram direcionados durante os últimos 12 meses do período.

* A fonte **[!UICONTROL NmsRecipient]** inclui todos os perfis que foram contatados usando informações do perfil do Campaign Standard.

* A fonte **[!UICONTROL anonymous]** dos clientes mostra o número de perfis que foram direcionados usando apenas uma parte específica das informações (endereço de email, número de telefone), sem relação com o perfil do Campaign.
