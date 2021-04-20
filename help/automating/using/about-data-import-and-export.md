---
solution: Campaign Standard
product: campaign
title: Sobre a importação e exportação de dados
description: Saiba mais sobre as diferentes maneiras de importar e exportar dados com o Adobe Campaign.
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
feature: Workflows
role: Data Architect
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 24%

---


# Sobre a importação e exportação de dados{#about-data-import-and-export}

Dependendo das necessidades de sua empresa, você tem várias maneiras de importar e exportar dados com o Adobe Campaign:

* **Pacotes**: são arquivos XML que permitem exportar e importar configurações e conjuntos de dados de uma instância do Adobe Campaign para outra. As atualizações do sistema também são executadas por meio de importações de pacotes.
* **Listas**: todas as telas de lista podem ser configuradas e os dados exibidos podem ser exportados em um arquivo separado.
* **Fluxos de trabalho**: importe dados de arquivos e use-os para atualizar o banco de dados ou enviar emails. Você também pode selecionar dados para exportar em arquivos. Os fluxos de trabalho são a melhor maneira de automatizar atualizações regulares, como importações de perfil.

   * A atividade **[!UICONTROL Load file]** permite importar dados em um formulário estruturado para usá-los no Adobe Campaign. Os dados são temporariamente importados e outra atividade é necessária para integrá-los definitivamente ao banco de dados do Adobe Campaign. Para obter mais informações sobre como usar essa atividade, consulte [esta seção](../../automating/using/load-file.md).
   * A atividade **[!UICONTROL Transfer file]** permite receber ou enviar arquivos, testar se há arquivos ou listar arquivos no Adobe Campaign. Você pode usar essa atividade antes de um **[!UICONTROL Load file]** caso precise recuperar o arquivo de uma fonte externa. Para obter mais informações sobre como usar essa atividade, consulte [esta seção](../../automating/using/transfer-file.md).

Ao projetar processos de importação, é uma prática recomendada usar modelos de fluxo de trabalho que você pode adaptar para atender às suas necessidades. Para obter mais informações sobre como configurar um template de workflow para importar dados, consulte [este caso de uso](../../automating/using/creating-import-workflow-templates.md).

A Adobe Campaign também oferece uma maneira simplificada de executar importações regulares, que consiste em projetar **modelos de importação**. Os templates de importação são templates de workflow especializados, disponíveis por meio de uma tela dedicada. Depois de criado, o usuário que estiver executando a importação só precisará fazer upload do arquivo para importá-lo em uma visualização simplificada.

**Tópicos relacionados**:

* [Importação de dados com modelos de importação](../../automating/using/importing-data-with-import-templates.md)
* [Definição de templates de importação](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates)
* [Gerenciamento de pacotes](../../automating/using/managing-packages.md)
