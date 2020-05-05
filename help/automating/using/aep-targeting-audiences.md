---
title: Definição de públicos da Adobe Experience Platform
description: Saiba como público alvo audiências de formato Adobe Experience em workflows.
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
source-git-commit: 68e825bc3b6b7f94f61875e7da2bc8f63f06d9cb

---


# Definição de públicos da Adobe Experience Platform {#targeting-aep-audiences}

>[!IMPORTANT]
>
>O serviço Destinos de Audiência está atualmente em beta, o que pode estar sujeito a atualizações frequentes sem aviso prévio. Os clientes precisam estar hospedados no Azure (atualmente em beta somente para a América do Norte) para acessar esses recursos. Entre em contato com o Atendimento ao cliente da Adobe se desejar acessar.

Depois de criar uma audiência [da plataforma](../../audiences/using/aep-about-audience-destinations-service.md) Adobe Experience usando o construtor de segmentos do Perfil unificado, você pode usá-la da mesma forma que usaria para uma audiência de Campanha dentro dos workflows para personalizar e enviar mensagens.

Para ativar uma audiência da plataforma Adobe Experience em seus workflows, siga estas etapas:

1. Adicione uma **[!UICONTROL Read audience]** atividade ao fluxo de trabalho e abra-a.

1. Selecione a **[!UICONTROL Adobe Experience Platform]** opção em **[!UICONTROL Type of audience]** e adicione a audiência desejada.

   ![](assets/aep_wkf_readaudience.png)

1. (Opcional) Depois que a audiência é selecionada, você pode clicar no botão de olho para revisar e/ou editar a definição do segmento (certifique-se de salvar as alterações novamente).

   Clicar no botão de olho simplesmente o direcionará para o Construtor de segmentos unificado (em outra guia) associado à audiência selecionada dentro da Campanha.

1. Selecione um **[!UICONTROL Platform data mapping]** elemento para especificar o targeting dimension desejado para a audiência selecionada da plataforma Adobe Experience.

   Por padrão, a chave primária (por exemplo, iRecipientID para a tabela do Perfil, iAppSubscriptionID para a tabela AppSubscription) usada para reconciliação estará automaticamente disponível na lista suspensa. Para público alvo fora da chave primária, é necessário criar uma **Namespace** personalizada.

   >[!NOTE]
   >
   >Para públicos alvos fora da chave primária, você também deve criar um Target mapping personalizado que corresponda à Namespace personalizada. For more information on Target Mapping, refer to [this section](../../administration/using/target-mappings-in-campaign.md).

   ![](assets/aep_wkf_readaudience_namespace.png)

   Esta lista contém todos os mapeamentos do Modelo de Dados de Experiência (XDM) que foram configurados em sua instância. Para obter mais informações sobre o Adobe Experience Platform Data Connector, consulte [este documento](../../developing/using/aep-about-data-connector.md)dedicado.

   ![](assets/aep_wkf_readaudience_namespace2.png)

1. Depois que a audiência e os targeting dimension forem configurados corretamente, clique no **[!UICONTROL Confirm]** botão para salvar as alterações.

Agora você pode configurar seu fluxo de trabalho com outras atividades. Por exemplo, você pode vincular uma **[!UICONTROL Email delivery]** atividade para enviar um email para a audiência selecionada.

![](assets/aep_wkf_email.png)

>[!NOTE]
>
>O Campaign Standard permite público alvo das audiências da plataforma Adobe Experience em todos os canais do delivery: Emails, mensagens SMS, Mensagens de mala direta, Notificações por push e Mensagens no aplicativo.
>
>*Observação: Para todas as mensagens de push e no aplicativo, o Campaign Standard só oferece suporte a delivery para perfis conhecidos.

Para obter mais informações sobre como usar workflows e delivery, consulte estas seções:

* [Descobrir fluxos de trabalho](../../automating/using/get-started-workflows.md)
* [Criação de um fluxo de trabalho](../../automating/using/building-a-workflow.md)
* [Descobrir canais de comunicação](../../channels/using/get-started-communication-channels.md)
* [Sobre as atividades de canal](../../automating/using/about-channel-activities.md)
