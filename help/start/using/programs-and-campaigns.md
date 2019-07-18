---
title: Programas e campanhas
seo-title: Programas e campanhas
description: Programas e campanhas
seo-description: No Adobe Campaign, os programas e campanhas permitem agrupar e orquestrar as diferentes atividades de marketing que estão vinculadas a eles. Relatórios sobre programas e campanhas permitem analisar o impacto.
page-status-flag: nunca ativado
uuid: fe 2812 a 8-196 f -4 aba-a 739-fbbfffd 754 cb
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: planos de marketing
discoiquuid: 21 b 84028-d 1 a 7-4 ad 6-891 a -862 a 94565514
context-tags: campanha, visão geral; Campaignexplorer, main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: cb6396228e42f99f7e184a82e6c894b09a164cd9

---


# Programs and campaigns{#programs-and-campaigns}

## About plans, programs and campaigns {#about-plans--programs-and-campaigns}

O Adobe Campaign permite que você planeje campanhas de marketing em que pode criar e gerenciar diferentes tipos de atividades: e-mails, mensagens SMS, notificações por push, fluxos de trabalho e páginas de aterrissagem. Essas campanhas e seu conteúdo podem ser coletados em programas.

Os programas e campanhas permitem que você recupere e visualize as diferentes atividades de marketing que estão vinculadas a eles.

* A **program** may contain other programs as well as campaigns, workflows, and landing pages. Ela aparece na linha do tempo e ajuda você a organizar suas atividades de marketing: você pode separá-los por país, por marca, por unidade, etc.
* A **campaign** enables you to gather all the marketing activities of your choice under a single entity. Uma campanha pode conter emails, SMS, notificações por push, mails diretos, fluxos de trabalho e páginas de aterrissagem.

Para organizar melhor seus planos de marketing, a Adobe recomenda a seguinte hierarquia: Programa &gt; Subprogramas &gt; Campanhas &gt; Fluxos de trabalho &gt; Entregas.

Relatórios sobre programas e campanhas permitem analisar o impacto. Por exemplo, você pode criar relatórios no nível da campanha para agregar dados em todas as entregas contidas nessa campanha.

**Tópicos relacionados:**

* [Linha do tempo](../../start/using/timeline.md)
* [Sobre relatórios dinâmicos](../../reporting/using/about-dynamic-reports.md)

## Creating a program {#creating-a-program}

O programa é o primeiro nível de organização. Ele pode conter subprogramas, campanhas, fluxos de trabalho ou páginas de aterrissagem.

1. From the Adobe Campaign home page, select the **[!UICONTROL Programs & Campaigns]** card.
1. Click on the **[!UICONTROL Create]** button.
1. In the **[!UICONTROL Creation mode]** screen, select a program type.

   ![](assets/programs_and_campaigns_2.png)

   The program types available are based on templates defined in the **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Program templates]** section. For more on this, refer to the [Managing templates](../../start/using/about-templates.md) section.

1. In the **[!UICONTROL Properties]** screen, enter the name and ID of the program.

   ![](assets/programs_and_campaigns_3.png)

1. Selecione uma data de início e fim para o seu programa. Essas datas se aplicam somente ao próprio programa.

   Você pode criar seu programa em um programa pai. Para fazer isso, selecione o programa pai a partir dos programas existentes.

1. Click on **[!UICONTROL Create]** to confirm the creation of the program.

O programa é criado e exibido. Use the **[!UICONTROL Create]** button to add sub-programs, campaigns, workflows or landing pages.

>[!NOTE]
>
>Você também pode criar um programa na lista de atividades de marketing.

## Creating a campaign {#creating-a-campaign}

Em programas e subprogramas, você pode adicionar campanhas. As campanhas podem conter atividades de marketing como emails, SMS, notificações por push, fluxos de trabalho e páginas de aterrissagem.

1. From the Adobe Campaign home page, select the **[!UICONTROL Programs & Campaigns]** card and access a program or sub-program.
1. Click on the **[!UICONTROL Create]** button and select **[!UICONTROL Campaign]**.
1. In the **[!UICONTROL Creation mode]** screen, select a campaign type.

   ![](assets/programs_and_campaigns_7.png)

   The campaign types available are based on templates defined in **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Campaign templates]**. For more on this, refer to the [Managing templates](../../start/using/about-templates.md) section.

1. In the **[!UICONTROL Properties]** screen, enter the name and ID of the campaign.
1. Selecione uma data de início e fim para a campanha. Essas datas se aplicam somente à campanha em si.

   ![](assets/programs_and_campaigns_8.png)

1. Click on **[!UICONTROL Create]** to confirm the creation of the campaign.

A campanha é criada e exibida. Use the **[!UICONTROL Create]** button to add marketing activities to your campaign.

>[!NOTE]
>
>Dependendo do contrato de licença, você pode acessar apenas algumas dessas atividades.

Você também pode criar uma campanha a partir da lista de atividades de marketing. É possível vincular a atividade de marketing a um programa principal ou subprogramas por meio da janela de propriedades da campanha.

## Programs and campaigns icons and statuses {#programs-and-campaigns-icons-and-statuses}

Cada programa e cada campanha na lista tem um símbolo visual e um ícone cuja cor indica o status da execução. Esse status depende do período de validade do programa ou da campanha.

* Gray: the program/campaign has not yet started - **[!UICONTROL Editing]** status.
* Blue: the program/campaign is in progress - **[!UICONTROL In progress]** status.
* Green: the program/campaign has finished - **[!UICONTROL Finished]** status. By default, the current date is automatically shown as the validity start date and the end date is calculated according to the start date (**D+186 days**). É possível alterar essas datas nas propriedades do programa ou da campanha.

![](assets/programs_and_campaigns.png)

