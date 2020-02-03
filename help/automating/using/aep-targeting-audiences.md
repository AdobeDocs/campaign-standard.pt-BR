---
title: Definição de metas para públicos-alvo da plataforma Adobe Experience
description: Saiba como direcionar os públicos-alvo da Adobe Experience PLatform nos fluxos de trabalho.
page-status-flag: never-activated
uuid: 528d9472-e447-47af-a6b2-3181aa5fb5ad
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: channel-activities
discoiquuid: 19796aca-6e9e-4d3a-8917-ba660ec7993c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1059b840d9a2d0c89a6cbd1808b645862747a76c

---


# Definição de metas para públicos-alvo da plataforma Adobe Experience {#targeting-aep-audiences}

>[!IMPORTANT]
>
>O serviço de Destinos de público-alvo está atualmente em beta, o que pode estar sujeito a atualizações frequentes sem aviso prévio. Os clientes precisam estar hospedados no Azure (atualmente em beta somente para a América do Norte) para acessar esses recursos. Entre em contato com o Atendimento ao cliente da Adobe se desejar acessar.

Depois de criar um público-alvo [da plataforma](../../audiences/using/aep-about-audience-destinations-service.md) Adobe Experience usando o construtor de segmentos de Perfil unificado, você pode usá-lo da mesma forma que faria para um público-alvo da campanha em fluxos de trabalho para personalizar e enviar mensagens.

Para ativar um público-alvo da plataforma Adobe Experience nos fluxos de trabalho, siga estas etapas:

1. Adicione uma **[!UICONTROL Read audience]**atividade ao fluxo de trabalho e abra-a.

1. Selecione a **[!UICONTROL Adobe Experience Platform]**opção em**[!UICONTROL Type of audience]** e adicione o público desejado.

   ![](assets/aep_wkf_readaudience.png)

1. (Opcional) Depois que o público-alvo é selecionado, você pode clicar no botão de olho para revisar e/ou editar a definição do segmento (certifique-se de salvar as alterações novamente).

   Clicar no botão de olho simplesmente o direcionará para o Construtor de segmentos unificado (em outra guia) associado ao público selecionado no Campaign.

1. Selecione um **[!UICONTROL Platform data mapping]**elemento para especificar a dimensão de direcionamento desejada para o público-alvo selecionado da Adobe Experience Platform.

   Por padrão, a chave primária (por exemplo, iRecipientID para a tabela Perfil, iAppSubscriptionID para a tabela AppSubscription) usada para reconciliação estará automaticamente disponível na lista suspensa. Para direcionar fora da chave primária, você deve criar um **Namespace** personalizado.

   >[!NOTE]
   >
   >Para destinos fora da chave primária, você também deve criar um Mapeamento de Destino personalizado que corresponda ao Namespace personalizado. For more information on Target Mapping, refer to [this section](../../administration/using/target-mappings-in-campaign.md).

   ![](assets/aep_wkf_readaudience_namespace.png)

   Esta lista contém todos os mapeamentos do Modelo de Dados de Experiência (XDM) que foram configurados em sua instância. Para obter mais informações sobre o Adobe Experience Platform Data Connector, consulte [este documento](../../administration/using/aep-about-data-connector.md)dedicado.

   ![](assets/aep_wkf_readaudience_namespace2.png)

1. Depois que as dimensões de público-alvo e direcionamento estiverem configuradas corretamente, clique no **[!UICONTROL Confirm]**botão para salvar suas alterações.

Agora você pode configurar seu fluxo de trabalho com outras atividades. Você pode, por exemplo, vincular uma **[!UICONTROL Email delivery]**atividade para enviar um email ao público que foi selecionado.

![](assets/aep_wkf_email.png)

>[!NOTE]
>
>O Campaign Standard permite que você direcione públicos-alvo da plataforma Adobe Experience em todos os canais de entrega: Emails, mensagens SMS, mensagens de mala direta, notificações por push e mensagens no aplicativo.

Para obter mais informações sobre como usar fluxos de trabalho e entregas, consulte estas seções:

* [Descobrir fluxos de trabalho](../../automating/using/discovering-workflows.md)
* [Criação de um fluxo de trabalho](../../automating/using/building-a-workflow.md)
* [Descobrir canais de comunicação](../../channels/using/discovering-communication-channels.md)
* [Sobre as atividades de canal](../../automating/using/about-channel-activities.md)
