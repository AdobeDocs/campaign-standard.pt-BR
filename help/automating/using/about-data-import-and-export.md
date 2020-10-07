---
title: Sobre a importação e exportação de dados
description: Saiba mais sobre as diferentes maneiras de importar e exportar dados com a Adobe Campaign.
page-status-flag: never-activated
uuid: f6810364-555c-4b72-8a9c-4ae2fcb2ba63
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
discoiquuid: 31215773-6c0c-48f1-9101-da0ea2a366da
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 24%

---


# Sobre a importação e exportação de dados{#about-data-import-and-export}

Dependendo das necessidades de sua empresa, você tem várias maneiras de importar e exportar dados com a Adobe Campaign:

* **Pacotes**: os pacotes são arquivos XML que permitem exportar e importar configurações e conjuntos de dados de uma instância do Adobe Campaign para outra. As atualizações do sistema também são executadas por meio de importações de pacotes.
* **Listas**: todas as telas de lista podem ser configuradas e os dados exibidos exportados em um arquivo separado.
* **Workflows**: importe dados de arquivos e use-os para atualizar o banco de dados ou enviar emails. Você também pode selecionar dados para exportar em arquivos. Os workflows são a melhor maneira de automatizar atualizações regulares, como as importações de perfis.

   * A atividade **[!UICONTROL Load file]** permite importar dados em um formulário estruturado para usá-los no Adobe Campaign. Os dados são temporariamente importados e outra atividade é necessária para integrá-los definitivamente ao banco de dados do Adobe Campaign. For more on how to use this activity, refer to [this section](../../automating/using/load-file.md).
   * A atividade **[!UICONTROL Transfer file]** permite receber ou enviar arquivos, testar se há arquivos ou listar arquivos no Adobe Campaign. Você pode usar essa atividade antes de uma **[!UICONTROL Load file]** caso precise recuperar o arquivo de uma fonte externa. For more on how to use this activity, refer to [this section](../../automating/using/transfer-file.md).

Ao projetar processos de importação, é uma prática recomendada usar modelos de fluxo de trabalho que você pode adaptar para atender às suas necessidades. Para obter mais informações sobre como configurar um modelo de fluxo de trabalho para importar dados, consulte [este caso](../../automating/using/creating-import-workflow-templates.md)de uso.

A Adobe Campaign também oferta uma maneira simplificada de realizar importações regulares, que consiste em projetar **templates de importação**. Os templates de importação são modelos de fluxo de trabalho especializados disponíveis por meio de uma tela dedicada. Depois de projetado, o usuário que executa a importação só precisa carregar o arquivo para importá-lo em uma visualização simplificada.

**Tópicos relacionados**:

* [Importação de dados com modelos de importação](../../automating/using/importing-data-with-import-templates.md)
* [Definição de templates de importação](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates)
* [Gerenciamento de pacotes](../../automating/using/managing-packages.md)
