---
title: Perfis ativos do Campaign
description: Saiba como acessar métricas do cliente e perfis ativos
feature: Profiles
role: User
level: Intermediate
exl-id: 22516348-7695-4579-99eb-480e5b723ccc
source-git-commit: 0ae2501b5c3ecf6dc9562bb53b5354c52aff7323
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 12%

---

# Perfis ativos{#active-profiles}

Você pode acessar os detalhes dos perfis ativos no **[!UICONTROL Customer metrics]** relatório. Este relatório está disponível somente para administradores funcionais do Campaign. Para acessar esse relatório, clique no ícone do Adobe Campaign na parte superior esquerda da variável [interface do usuário](../../start/using/interface-description.md#advanced-menu)e navegue até **[!UICONTROL Administration > Customer metrics]**.

![](assets/audience_customer_metrics.png)

Esse relatório é gerado todos os meses pela variável **[!UICONTROL Billing]** do fluxo de trabalho técnico e exibe o número de **perfis ativos**. Saiba mais sobre workflows técnicos no [esta página](../../administration/using/technical-workflows.md).

Um &quot;Perfil&quot; é um registro de informações que representam um cliente final, um prospecto ou um cliente potencial. Os perfis são considerados **ative** se tiverem sido direcionados por um delivery do Campaign nos últimos 12 meses por meio de qualquer canal.

De acordo com seu contrato, cada uma das instâncias do Campaign é provisionada com um número específico de perfis ativos. Consulte seu contrato de licença para obter uma referência sobre o número de perfis ativos adquiridos.

![](assets/audience_active_profiles_list.png)



* Os perfis excluídos durante a preparação do delivery (por regras de tipologia ou mecanismo de quarentena, por exemplo) não são considerados.

* Os recipients das Mensagens transacionais são contados em Perfis ativos.

* Um perfil que foi direcionado por vários deliveries será contado apenas uma vez.

* Este relatório é apenas informativo, não tem impacto direto na cobrança.

Na parte inferior da página, os targeting dimensions estão listados com o número de perfis para cada. Os recipients de mensagens transacionais estão associados à variável **Anônimo** dimensão.

>[!NOTE]
>
>Como um usuário administrador, você também pode monitorar o número de perfis ativos usados em suas instâncias diretamente do Painel de controle do Campaign. Para obter mais informações, consulte a [documentação do Painel de controle do Campaign](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html?lang=pt-BR).
