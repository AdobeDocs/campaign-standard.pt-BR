---
title: Assimilar públicos-alvos da Adobe Experience Platform no Campaign
description: Saiba como assimilar públicos-alvo da Adobe Experience Platform na Campaign Standard.
audience: integrating
content-type: reference
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 5c266c44-535b-4954-862d-74c83a6f6406
TQID: https://experienceleague.adobe.com/LdVWEXa90p4yOKgPGG5LUOGRk3xWE8kJ8SkKM7ODBXk
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
subfeature_v2:
  - id: b70f632b-2cfd-43d0-9266-284281100d70
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 331
ht-degree: 69%

---

# Assimilar públicos-alvos da Adobe Experience Platform no Campaign {#destinations}

Para assimilar públicos-alvos da Adobe Experience Platform no Campaign e usá-los em seus workflows, primeiro é necessário conectar o Adobe Campaign como um **Destino** da Adobe Experience Platform e configurá-lo com o segmento a ser exportado.

Depois que o Destino for configurado, os dados serão exportados para o local de armazenamento e você precisará criar um fluxo de trabalho dedicado no Campaign Standard para assimilá-los.

## Conectar o Adobe Campaign como um destino

Na Adobe Experience Platform, configure uma conexão com o Adobe Campaign selecionando um local de armazenamento para os segmentos exportados. Essas etapas também permitem selecionar os segmentos a serem exportados e especificar campos XDM adicionais para inclusão.

Para obter mais informações, consulte a [Documentação de destinos](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/email-marketing/adobe-campaign.html?lang=pt-BR).

Após o Destino ser configurado, a Adobe Experience Platform cria um arquivo .txt ou .csv delimitado por tabulação no local de armazenamento fornecido. Esta operação é agendada e executada uma vez a cada 24 horas.

Agora você pode configurar um fluxo de trabalho do Campaign Standard para assimilar o segmento no Campaign.

## Criar um fluxo de trabalho de importação no Campaign Standard

Depois que o Campaign Standard for configurado como um Destino, será necessário criar um fluxo de trabalho dedicado para importar o arquivo que foi exportado pelo Adobe Experience Platform.

Para fazer isso, é necessário adicionar e configurar uma atividade **[!UICONTROL Transfer file]**. Para obter mais informações sobre como configurar essa atividade, consulte [esta seção](../../automating/using/transfer-file.md).

![](assets/rtcdp-transfer-file.png)

Em seguida, você pode criar o fluxo de trabalho de acordo com suas necessidades (atualizar o banco de dados usando os dados do segmento, enviar entregas entre canais para o segmento etc.)

Como exemplo, o fluxo de trabalho abaixo faz o download do arquivo do local de armazenamento diariamente e atualiza o banco de dados do Campaign com os dados do segmento.

![](assets/rtcdp-workflow.png)

Exemplos de fluxos de trabalho de gerenciamento de dados estão disponíveis na seção [casos de uso de fluxos de trabalho](../../automating/using/about-workflow-use-cases.md#management).

Tópicos relacionados:

* [Atividades de gerenciamento de dados](../../automating/using/about-data-management-activities.md)
* [Sobre importação e exportação de dados](../../automating/using/about-data-import-and-export.md)
