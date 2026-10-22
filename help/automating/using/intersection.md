---
title: Interseção
description: A atividade Intersecção permite manter somente os elementos comuns aos diferentes populações de entrada na atividade.
audience: automating
content-type: reference
topic-tags: targeting-activities
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 2a6a851c-df91-472b-a8a4-0b3876d51c1d
TQID: 'https://experienceleague.adobe.com/G9ptSqWfh2BTA76Ul-j2th1W2aHI-eiPvJBpcasLJXs'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '287'
ht-degree: 98%
---
# Interseção{#intersection}

## Descrição {#description}

![](assets/intersection.png)

A atividade **[!UICONTROL Intersection]** permite manter somente os elementos comuns aos diferentes populações de entrada na atividade.

## Contexto de uso {#context-of-use}

A atividade **[!UICONTROL Intersection]** é geralmente usada para fazer filtragem adicional em populações provenientes de transições de entrada.

## Configuração {#configuration}

1. Arraste e solte uma atividade **[!UICONTROL Intersection]** no seu fluxo de trabalho.
1. Conecte-a às outras atividades anteriores a ela, como consultas.
1. Selecione e abra a atividade usando o botão ![](assets/edit_darkgrey-24px.png) das ações rápidas exibidas.
1. Selecione o **[!UICONTROL Reconciliation type]**:

   * **[!UICONTROL Keys only]**: Modo padrão. A atividade só mantém um elemento quando elementos de transições de entrada diferentes têm a mesma chave.
   * **[!UICONTROL All shared columns]**: Os dados são reconciliados com base em colunas em comum com as transições de entrada. Portanto, é necessário selecionar o conjunto principal que servirá de base para comparação. Essa opção só poderá ser usada se as dimensões de direcionamento da população de entrada forem diferentes.
   * **[!UICONTROL A selection of columns]**: selecione esta opção para definir a lista de colunas em que a reconciliação de dados será aplicada. Primeiro, selecione o conjunto principal (aquele que contém os dados de origem), e especifique os campos a serem usados para a junção.

1. Marque a caixa **[!UICONTROL Use common additional data only]** se quiser manter somente os dados adicionais existentes em todas as transições de entrada.
1. Se necessário, gerencie as [Transições](../../automating/using/activity-properties.md) de atividade para acessar as opções avançadas para a população de saída.
1. Confirme a configuração da sua atividade e salve o fluxo de trabalho.

## Exemplo {#example}

O exemplo a seguir mostra a intersecção entre duas atividades de consulta. Ela está sendo usada aqui para examinar o banco de dados do Adobe Campaign e recuperar perfis com idade entre 18 e 27 anos e perfis cujo endereço de email foi fornecido, respectivamente.

![](assets/wkf_intersection_example.png)
