---
solution: Campaign Standard
product: campaign
title: União
description: A atividade Union permite reagrupar o resultado de várias atividades em um único público-alvo.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: union,main
feature: Fluxos de trabalho
role: Arquiteto de dados
level: Intermediário
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 97%

---


# União{#union}

## Descrição {#description}

![](assets/union.png)

A atividade **[!UICONTROL Union]** permite reagrupar o resultado de várias atividades em um único público-alvo.

>[!NOTE]
>
>Os conjuntos não precisam ser necessariamente homogêneos.

## Contexto de uso {#context-of-use}

A atividade **[!UICONTROL Union]** é usada para combinar as populações das transições de entrada ao executar uma segmentação, definir um público-alvo ou preparar o público-alvo da mensagem, por exemplo.

**Tópicos relacionados:**

* [Caso de uso: União em dois públicos-alvo refinados](../../automating/using/union-on-two-refined-audiences.md)

## Configuração {#configuration}

1. Arraste e solte uma atividade **[!UICONTROL Union]** no seu fluxo de trabalho.
1. Conecte-a às outras atividades anteriores a ela, como consultas.
1. Selecione e abra a atividade usando o botão ![](assets/edit_darkgrey-24px.png) das ações rápidas exibidas.
1. Selecione o **[!UICONTROL Reconciliation type]** para definir como os duplicados são tratados a partir do confronto entre as populações de entrada:

   * **[!UICONTROL Keys only]**: este é o modo padrão. A atividade só mantém um elemento quando elementos de transições de entrada diferentes têm a mesma chave. Essa opção só poderá ser usada se as populações de entrada forem homogêneas.
   * **[!UICONTROL All shared columns]**: os dados são reconciliados com base em todas as colunas em comum com as transições de entrada. Portanto, é necessário selecionar o conjunto principal que será mantido no caso de um duplicado. Essa opção só poderá ser usada se os targeting dimensions da população de entrada forem diferentes.
   * **[!UICONTROL A selection of columns]**: selecione esta opção para definir a lista de colunas em que a reconciliação de dados será aplicada. Primeiro, selecione o conjunto principal (que contém os dados de origem) e, em seguida, as colunas a serem usadas para a junção.

1. Marque a caixa **[!UICONTROL Use common additional data only]** se quiser manter somente os dados adicionais existentes em todas as transições de entrada.
1. Se quiser limitar o tamanho da população final, marque a caixa **[!UICONTROL Limit size of generated population]**. O tamanho pode ser especificado no campo **[!UICONTROL Maximum number of records]**.
1. Se necessário, gerencie as [transições](../../automating/using/activity-properties.md) da atividade para acessar as opções avançadas da população calculada.
1. Confirme a configuração da sua atividade e salve o fluxo de trabalho.

## Exemplo {#example}

O exemplo a seguir mostra o resultado de dois queries cujo objetivo é reagrupar os perfis do banco de dados do Adobe Campaign com idades entre 18 e 27 anos e entre 34 e 40 anos. O resultado contém todos os perfis das duas consultas ou o número máximo de registros, se aplicável, conforme especificado durante a configuração.

![](assets/wkf_union_example.png)