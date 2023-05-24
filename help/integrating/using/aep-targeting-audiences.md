---
title: Direcionamento de públicos da Adobe Experience Platform
description: Saiba como direcionar públicos-alvo da Adobe Experience Platform em fluxos de trabalho.
audience: automating
content-type: reference
topic-tags: channel-activities
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: 11e2cd7e-99b7-45cc-a0c2-41049128fe49
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 5%

---

# Direcionamento de públicos da Adobe Experience Platform {#targeting-aep-audiences}

>[!IMPORTANT]
>
>O serviço Audience Destinations está atualmente em versão beta, que pode estar sujeita a atualizações frequentes sem aviso prévio. Os clientes precisam ser hospedados no Azure (atualmente na versão beta somente para a América do Norte) para acessar esses recursos. Entre em contato com o Atendimento ao cliente do Adobe se desejar obter acesso.

Depois de criar um [Público-alvo do Adobe Experience Platform](../../integrating/using/aep-about-audience-destinations-service.md) com o Construtor de segmentos, você pode usá-lo da mesma forma que faria para um público do Campaign em workflows para personalizar e enviar mensagens.

Para ativar um público-alvo do Adobe Experience Platform em seus workflows, siga estas etapas:

1. Adicionar um **[!UICONTROL Read audience]** atividade no workflow e, em seguida, abra-a.

1. Selecione o **[!UICONTROL Adobe Experience Platform]** opção em **[!UICONTROL Type of audience]**, em seguida, adicione o público-alvo desejado.

   ![](assets/aep_wkf_readaudience.png)

1. (Opcional) Depois que o público-alvo é selecionado, você pode clicar no botão do olho para revisar e/ou editar a definição do segmento (salve as alterações novamente).

   Clicar no botão de olho simplesmente direcionará você para o Construtor de segmentos (em outra guia) associado ao público-alvo selecionado no Campaign.

1. Selecione um **[!UICONTROL Platform data mapping]** elemento para especificar o targeting dimension desejado para o público-alvo do Adobe Experience Platform selecionado.

   Por padrão, a chave primária (por exemplo, iRecipientID para a tabela de Perfil, iAppSubscriptionID para a tabela AppSubscription ) usada para reconciliação estará automaticamente disponível na lista suspensa. Para direcionar para fora da chave primária, você deve criar uma **Namespace**.

   >[!NOTE]
   >
   >Para destinos fora da chave primária, você também deve criar um Target Mapping personalizado que corresponda ao namespace personalizado. Para obter mais informações sobre Target Mapping, consulte [nesta seção](../../administration/using/target-mappings-in-campaign.md).

   ![](assets/aep_wkf_readaudience_namespace.png)

   Essa lista contém todos os mapeamentos do Experience Data Model (XDM) que foram configurados na sua instância. Para obter mais informações sobre o Conector de dados do Adobe Experience Platform, consulte [este documento dedicado](../../integrating/using/aep-about-data-connector.md).

   ![](assets/aep_wkf_readaudience_namespace2.png)

1. Depois que as dimensões de público-alvo e direcionamento forem configuradas corretamente, clique no link **[!UICONTROL Confirm]** botão para salvar as alterações.

Agora você pode configurar o fluxo de trabalho com outras atividades. É possível, por exemplo, vincular um **[!UICONTROL Email delivery]** atividade para enviar um email para o público-alvo que foi selecionado.

![](assets/aep_wkf_email.png)

>[!NOTE]
>
>O Campaign Standard permite direcionar públicos-alvo da Adobe Experience Platform em todos os canais de entrega: emails, mensagens SMS, mensagens de correspondência direta, notificações por push e mensagens no aplicativo.
>
>*Observação: para todas as mensagens por push e no aplicativo, o Campaign Standard aceita apenas deliveries para perfis conhecidos.

Para obter mais informações sobre como usar workflows e deliveries, consulte estas seções:

* [Introdução aos workflows](../../automating/using/get-started-workflows.md)
* [Criação de um workflow](../../automating/using/building-a-workflow.md)
* [Introdução aos canais de comunicação](../../channels/using/get-started-communication-channels.md)
* [Sobre as atividades de canal](../../automating/using/about-channel-activities.md)
