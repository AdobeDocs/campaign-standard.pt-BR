---
title: Sobre importação e exportação de dados
description: Saiba mais sobre as diferentes maneiras de importar e exportar dados com o Adobe Campaign.
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
feature: Workflows
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 208e8629-c3e2-4f36-bae7-46ffc3f56a1b
TQID: https://experienceleague.adobe.com/WP1mlY9lQQu5qWqIx5L89VE6MxnOhxoYewTWAYwfFTI
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 324
ht-degree: 24%

---

# Sobre importação e exportação de dados{#about-data-import-and-export}

Dependendo das suas necessidades comerciais, você tem várias maneiras de importar e exportar dados com o Adobe Campaign:

* **Pacotes**: pacotes são arquivos XML que permitem exportar e importar configurações e conjuntos de dados de uma instância do Adobe Campaign para outra. As atualizações de sistema também são realizadas por meio de importações de pacotes.
* **Listas**: todas as telas de listas podem ser configuradas e os dados exibidos podem ser exportados em um arquivo separado.
* **Fluxos de trabalho**: importe dados de arquivos e use-os para atualizar o banco de dados ou enviar emails. Você também pode selecionar dados para exportar em arquivos. Os workflows são a melhor maneira de automatizar atualizações regulares, como importações de perfis.

   * A atividade **[!UICONTROL Load file]** permite importar dados em um formulário estruturado para usá-los no Adobe Campaign. Os dados são temporariamente importados e outra atividade é necessária para integrá-los definitivamente ao banco de dados do Adobe Campaign. Para obter mais informações sobre como usar esta atividade, consulte [esta seção](../../automating/using/load-file.md).
   * A atividade **[!UICONTROL Transfer file]** permite receber ou enviar arquivos, testar se há arquivos ou listar arquivos no Adobe Campaign. Você pode usar esta atividade antes de um **[!UICONTROL Load file]**, caso precise recuperar o arquivo de uma fonte externa. Para obter mais informações sobre como usar esta atividade, consulte [esta seção](../../automating/using/transfer-file.md).

Ao projetar processos de importação, é uma prática recomendada usar modelos de fluxo de trabalho que você pode adaptar para atender às suas necessidades. Para obter mais informações sobre como configurar um modelo de fluxo de trabalho para importar dados, consulte [este caso de uso](../../automating/using/creating-import-workflow-templates.md).

O Adobe Campaign também oferece uma maneira simplificada de executar importações regulares que consiste em criar **modelos de importação**. Os templates de importação são modelos de fluxo de trabalho especializados disponíveis em uma tela dedicada. Depois de projetado, o usuário que executa a importação só precisa fazer upload do arquivo para importar em uma visualização simplificada.

**Tópicos relacionados**:

* [Importação de dados com modelos de importação](../../automating/using/importing-data-with-import-templates.md)
* [Definição de modelos de importação](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates)
* [Gerenciamento de pacotes](../../automating/using/managing-packages.md)
