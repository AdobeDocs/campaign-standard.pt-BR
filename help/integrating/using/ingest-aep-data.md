---
solution: Campaign Standard
product: campaign
title: Assimilar públicos da Adobe Experience Platform no Campaign
description: Saiba como assimilar públicos-alvo do Adobe Experience Platform no Campaign Standard.
audience: integrating
content-type: reference
feature: Fontes e destinos
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 894d691f1df3a613bacc74e149e5fdf7f4531d92
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 3%

---


# Assimilar públicos-alvo da Adobe Experience Platform no Campaign {#destinations}

Para assimilar públicos do Adobe Experience Platform no Campaign e usá-los em seus fluxos de trabalho, primeiro é necessário conectar o Adobe Campaign como um Adobe Experience Platform **Destination** e configurá-lo com o segmento a ser exportado.

Depois que o Destino for configurado, os dados serão exportados para o local de armazenamento e você precisará criar um fluxo de trabalho dedicado no Campaign Standard para assimilá-lo.

## Conectar o Adobe Campaign como um destino

Na Adobe Experience Platform, configure uma conexão com o Adobe Campaign selecionando um local de armazenamento para os segmentos exportados. Essas etapas também permitem selecionar os segmentos a serem exportados e especificar campos XDM adicionais para inclusão.

Para obter mais informações, consulte a [documentação de Destinos](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/email-marketing/adobe-campaign.html).

Após o Destino ter sido configurado, o Adobe Experience Platform cria um arquivo .txt ou .csv delimitado por tabulação no local de armazenamento fornecido. Esta operação é agendada e executada uma vez por 24 horas.

Agora você pode configurar um fluxo de trabalho do Campaign Standard para assimilar o segmento no Campaign.

## Criar um workflow de importação no Campaign Standard

Depois que o Campaign Standard tiver sido configurado como um Destino, será necessário criar um fluxo de trabalho dedicado para importar o arquivo que foi exportado pelo Adobe Experience Platform.

Para fazer isso, é necessário adicionar e configurar uma atividade **[!UICONTROL Transfer file]** . Para obter mais informações sobre como configurar essa atividade, consulte [esta seção](../../automating/using/transfer-file.md).

![](assets/rtcdp-transfer-file.png)

Em seguida, você pode criar o workflow de acordo com suas necessidades (atualizar o banco de dados usando os dados do segmento, enviar deliveries entre canais para o segmento, etc.)

Como exemplo, o workflow abaixo baixa o arquivo do local de armazenamento diariamente e atualiza o banco de dados do Campaign com os dados do segmento.

![](assets/rtcdp-workflow.png)

Exemplos de workflows de gerenciamento de dados estão disponíveis na seção [workflows use cases](../../automating/using/about-workflow-use-cases.md#management) .

Tópicos relacionados:

* [Atividades de gestão de dados](../../automating/using/about-data-management-activities.md)
* [Sobre a importação e exportação de dados](../../automating/using/about-data-import-and-export.md)
