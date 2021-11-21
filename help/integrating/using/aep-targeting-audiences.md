---
title: Direcionamento de públicos da Adobe Experience Platform
description: Saiba como direcionar públicos do Adobe Experience Platform em fluxos de trabalho.
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
>O serviço Audience Destinations está atualmente em beta, o que pode estar sujeito a atualizações frequentes sem aviso prévio. Os clientes precisam ser hospedados no Azure (atualmente em beta somente para a América do Norte) para acessar esses recursos. Entre em contato com o Atendimento ao cliente do Adobe se desejar acesso.

Depois de criar uma [Público-alvo do Adobe Experience Platform](../../integrating/using/aep-about-audience-destinations-service.md) usando o Construtor de segmentos, você pode usá-lo da mesma maneira que usaria um público-alvo da Campanha em fluxos de trabalho para personalizar e enviar mensagens.

Para ativar um público-alvo da Adobe Experience Platform nos workflows, siga estas etapas:

1. Adicione um **[!UICONTROL Read audience]** atividade no workflow e depois a abra.

1. Selecione o **[!UICONTROL Adobe Experience Platform]** opção em **[!UICONTROL Type of audience]**, em seguida, adicione o público-alvo desejado.

   ![](assets/aep_wkf_readaudience.png)

1. (Opcional) Após selecionar o público-alvo, você pode clicar no botão de olhos para revisar e/ou editar a definição do segmento (certifique-se de salvar as alterações novamente).

   Clicar no botão de olho simplesmente direcionará você para o Construtor de segmentos (em outra guia) associado ao público selecionado no Campaign.

1. Selecione um **[!UICONTROL Platform data mapping]** elemento para especificar o targeting dimension desejado para o público-alvo selecionado do Adobe Experience Platform.

   Por padrão, a chave primária (por exemplo, iRecipientID para a tabela Profile, iAppSubscriptionID para a tabela AppSubscription) usada para reconciliação estará disponível automaticamente na lista suspensa. Para direcionar fora da chave primária, você deve criar um **Namespace**.

   >[!NOTE]
   >
   >Para destinos fora da chave primária, você também deve criar um Mapeamento de Destino personalizado que corresponda ao Namespace personalizado. Para obter mais informações sobre o Target Mapping, consulte [esta seção](../../administration/using/target-mappings-in-campaign.md).

   ![](assets/aep_wkf_readaudience_namespace.png)

   Esta lista contém todos os mapeamentos do Experience Data Model (XDM) que foram configurados em sua instância. Para obter mais informações sobre o Adobe Experience Platform Data Connector, consulte [este documento dedicado](../../integrating/using/aep-about-data-connector.md).

   ![](assets/aep_wkf_readaudience_namespace2.png)

1. Depois que o público-alvo e os targeting dimensions estiverem configurados corretamente, clique no link **[!UICONTROL Confirm]** para salvar as alterações.

Agora é possível configurar o workflow com outras atividades. Você pode, por exemplo, vincular uma **[!UICONTROL Email delivery]** atividade para enviar um email para o público selecionado.

![](assets/aep_wkf_email.png)

>[!NOTE]
>
>O Campaign Standard permite direcionar públicos do Adobe Experience Platform em todos os canais de delivery: Emails, mensagens SMS, mensagens de mala direta, notificações por push e mensagens no aplicativo.
>
>*Observação: Para todas as mensagens de push e no aplicativo, o Campaign Standard só oferece suporte a deliveries para perfis conhecidos.

Para obter mais informações sobre como usar workflows e deliveries, consulte estas seções:

* [Introdução aos workflows](../../automating/using/get-started-workflows.md)
* [Criação de um workflow](../../automating/using/building-a-workflow.md)
* [Introdução aos canais de comunicação](../../channels/using/get-started-communication-channels.md)
* [Sobre as atividades de canal](../../automating/using/about-channel-activities.md)
