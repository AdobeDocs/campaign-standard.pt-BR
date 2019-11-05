---
title: Ler público-alvo
description: A atividade Ler público-alvo permite recuperar um público existente e refiná-lo aplicando condições de filtragem adicionais.
page-status-flag: nunca ativado
uuid: 58c54e71-f4a7-4ae9-80a3-33c379ab1db9
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: automatização
content-type: referência
topic-tags: atividades de definição de metas
discoiquuid: 674684e5-8830-4d2f-ba97-59ed4ba7422f
context-tags: readAudience,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Ler público-alvo{#read-audience}

## Descrição {#description}

![](assets/prefill.png)

A **[!UICONTROL Read audience]** atividade permite recuperar um público-alvo existente e refiná-lo aplicando condições de filtragem adicionais.

## Contexto de utilização {#context-of-use}

A **[!UICONTROL Read audience]** atividade é uma versão mais simples da **[!UICONTROL Query]** atividade projetada para casos em que você só precisa selecionar um público-alvo existente.

## Configuração {#configuration}

1. Solte uma **[!UICONTROL Read audience]** atividade em seu fluxo de trabalho.
1. Selecione a atividade e abra-a usando o ![](assets/edit_darkgrey-24px.png) botão das ações rápidas que aparecem.
1. Selecione o público que deseja recuperar na **[!UICONTROL Properties]** guia.

   Você pode recuperar públicos dos seguintes tipos: **[!UICONTROL List]**, **[!UICONTROL Query]**, **[!UICONTROL File]** e **[!UICONTROL Experience Cloud]**. Para obter mais informações sobre tipos de público-alvo, consulte a documentação [Públicos-alvo](../../audiences/using/about-audiences.md) .

   A **[!UICONTROL Use a dynamic audience]** opção permite definir o nome do público-alvo a ser direcionado com base nas variáveis de eventos do fluxo de trabalho. Para obter mais informações, consulte a seção [Personalizar atividades com variáveis](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) de eventos.

   ![](assets/readaudience_activity1.png)

1. Se desejar aplicar filtragem adicional ao público-alvo selecionado, adicione condições por meio da **[!UICONTROL Source filtering]** guia da atividade.

   Para obter mais informações sobre como criar condições de filtragem, consulte a documentação [Criação de consultas](../../automating/using/editing-queries.md#creating-queries) .

1. Confirme a configuração da atividade e salve o fluxo de trabalho.

## Exemplo: Reconciliar um público-alvo de Arquivo com o banco de dados {#example--reconcile-a-file-audience-with-the-database}

Este exemplo mostra como usar a **[!UICONTROL Read audience]** atividade para reconciliar um público-alvo criado diretamente de uma importação de arquivo.

Ao executar uma importação de arquivo, você pode salvar diretamente seu conteúdo em um público-alvo. Esse público é um público-alvo de Arquivo e seus dados não estão vinculados a nenhum recurso do banco de dados.

O fluxo de trabalho de importação foi projetado da seguinte forma:

![](assets/readaudience_activity_example3.png)

* Uma atividade [Carregar arquivo](../../automating/using/load-file.md) carrega um arquivo contendo dados de perfis que foram extraídos de uma ferramenta externa.

   Por exemplo:

   ```
   lastname;firstname;birthdate;email;crmID
   Smith;Hayden;23/05/1989;hayden.smith@example.com;124365
   Mars;Daniel;17/11/1987;dannymars@example.com;123545
   Smith;Clara;08/02/1989;hayden.smith@example.com;124567
   Durance;Allison;15/12/1978;allison.durance@example.com;120987
   Lucassen;Jody;28/03/1988;jody.lucassen@example.com;127634
   Binder;Tom;19/01/1982;tombinder@example.com;128653
   Binder;Tommy;19/01/1915;tombinder@example.com;134576
   Connor;Jade;10/10/1979;connor.jade@example.com;132452
   Mack;Clarke;02/03/1985;clarke.mack@example.com;149876
   Ross;Timothy;04/07/1986;timross@example.com;157643
   ```

* Uma atividade [Salvar público](../../automating/using/save-audience.md) salva os dados recebidos como um público-alvo. Como os dados ainda não foram reconciliados, o público-alvo é um público-alvo de Arquivo e seus dados ainda não são reconhecidos como dados de perfil.

O fluxo de trabalho de reconciliação foi projetado da seguinte forma:

![](assets/readaudience_activity_example2.png)

* Uma **[!UICONTROL Read audience]** atividade carrega o público-alvo Arquivo criado no fluxo de trabalho de importação. Os dados do público-alvo ainda não foram reconciliados com o banco de dados do Adobe Campaign.
* Uma atividade de [Reconciliação](../../automating/using/reconciliation.md) identifica os dados recebidos como perfis por meio de sua **[!UICONTROL Identification]** guia. Por exemplo, usando o campo de **email** como critérios de reconciliação.
* Uma atividade [Atualizar dados](../../automating/using/update-data.md) insere e atualiza o recurso de perfis do banco de dados com os dados recebidos. Como os dados já estão identificados como perfis, você pode selecionar a **[!UICONTROL Directly using the targeting dimension]** opção e selecionar **[!UICONTROL Profiles]** na **[!UICONTROL Identification]** guia da atividade. Em seguida, basta adicionar a lista de campos que precisam ser atualizados na guia de acordo.

## Exemplo: União em duas audiências refinadas {#example--union-on-two-refined-audiences}

O fluxo de trabalho definido neste exemplo mostra a união de duas **[!UICONTROL Read audience]** atividades. O objetivo deste fluxo de trabalho é enviar um email para membros Gold ou Silver com idade entre 18 e 30 anos.

Públicos-alvo específicos já foram criados no sistema para rastrear os membros Gold e Silver.

O fluxo de trabalho é projetado da seguinte forma:

![](assets/readaudience_activity_example1.png)

* Uma primeira **[!UICONTROL Read audience]** atividade que recupera o público-alvo dos membros Ouro e o refina selecionando somente perfis com idade entre 18 e 30 anos.
* Uma segunda **[!UICONTROL Read audience]** atividade que recupera o público-alvo dos membros do Silver e o refina selecionando somente perfis com idade entre 18 e 30 anos.
* Uma **[!UICONTROL Union]** atividade que une populações de ambas as **[!UICONTROL Read audiences]** atividades em uma população final.
* Uma **[!UICONTROL Email delivery]** atividade que envia o email para a população proveniente da **[!UICONTROL Union]** atividade.

