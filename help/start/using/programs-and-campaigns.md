---
title: Programas e campanhas
description: No Adobe Campaign, os programas e campanhas permitem agrupar e orquestrar as diferentes atividades de marketing vinculadas a elas. Relatórios sobre programas e campanhas permitem analisar o impacto deles.
page-status-flag: never-activated
uuid: fe2812a8-196f-4aba-a739-fbbfffd754cb
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: marketing-plans
discoiquuid: 21b84028-d1a7-4ad6-891a-862a94565514
context-tags: campaign,overview;campaignExplorer,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c26f98c8edd832beeedfedafb8ad27730cc30d25

---


# Programas e campanhas{#programs-and-campaigns}

## Sobre planos, programas e campanhas {#about-plans--programs-and-campaigns}

O Adobe Campaign permite planejar campanhas de marketing nas quais você pode criar e gerenciar diferentes tipos de atividades: emails, mensagens SMS, notificações por push, fluxos de trabalho, páginas iniciais. Essas campanhas e seus conteúdos podem ser reunidos em programas.

Os programas e campanhas permitem que você se reagrupe e visualize as diferentes atividades de marketing vinculadas a eles.

* Um **programa** pode conter outros programas, bem como campanhas, fluxos de trabalho e páginas de aterrissagem. Ela é exibida na linha do tempo e ajuda a organizar suas atividades de marketing: você pode separá-los por país, por marca, por unidade, etc.
* Uma **campanha** permite que você reúna todas as atividades de marketing de sua escolha em uma única entidade. Uma campanha pode conter emails, SMS, notificações por push, emails diretos, fluxos de trabalho e páginas de aterrissagem.

Para melhor organizar seus planos de marketing, a Adobe recomenda a seguinte hierarquia: Programa > Subprogramas > Campanhas > Fluxos de trabalho > Entregas.

Relatórios sobre programas e campanhas permitem analisar o impacto deles. Por exemplo, você pode criar relatórios no nível da campanha para agregar dados em todas as entregas contidas nessa campanha.

**Tópicos relacionados:**

* [Linha do tempo](../../start/using/timeline.md)
* [Sobre os relatórios dinâmicos](../../reporting/using/about-dynamic-reports.md)

## Criação de um programa {#creating-a-program}

O programa é o primeiro nível de organização. Ele pode conter subprogramas, campanhas, fluxos de trabalho ou páginas iniciais.

1. Na página inicial do Adobe Campaign, selecione o **[!UICONTROL Programs & Campaigns]**cartão.
1. Click on the **[!UICONTROL Create]**button.
1. Na **[!UICONTROL Creation mode]**tela, selecione um tipo de programa.

   ![](assets/programs_and_campaigns_2.png)

   Os tipos de programa disponíveis são baseados em modelos definidos na seção **[!UICONTROL Resources]**>**[!UICONTROL Templates]** > **[!UICONTROL Program templates]**. For more on this, refer to the[Managing templates](../../start/using/marketing-activity-templates.md)section.

1. Na **[!UICONTROL Properties]**tela, digite o nome e a ID do programa.

   ![](assets/programs_and_campaigns_3.png)

1. Selecione uma data de início e término para o seu programa. Estas datas só se aplicam ao próprio programa.

   Você pode criar seu programa dentro de um programa pai. Para fazer isso, selecione o programa pai dos programas existentes.

1. Clique em **[!UICONTROL Create]**para confirmar a criação do programa.

O programa é criado e exibido. Use o **[!UICONTROL Create]**botão para adicionar subprogramas, campanhas, fluxos de trabalho ou páginas iniciais.

>[!NOTE]
>
>Você também pode criar um programa a partir da lista de atividades de marketing.

## Criação de uma campanha {#creating-a-campaign}

Em programas e subprogramas, você pode adicionar campanhas. As campanhas podem conter atividades de marketing, como emails, SMS, notificações por push, fluxos de trabalho e páginas de aterrissagem.

1. Na página inicial do Adobe Campaign, selecione o **[!UICONTROL Programs & Campaigns]**cartão e acesse um programa ou subprograma.
1. Clique no **[!UICONTROL Create]**botão e selecione**[!UICONTROL Campaign]**.
1. Na **[!UICONTROL Creation mode]**tela, selecione um tipo de campanha.

   ![](assets/programs_and_campaigns_7.png)

   Os tipos de campanha disponíveis são baseados em modelos definidos em **[!UICONTROL Resources]**>**[!UICONTROL Templates]** > **[!UICONTROL Campaign templates]**. For more on this, refer to the[Managing templates](../../start/using/marketing-activity-templates.md)section.

1. Na **[!UICONTROL Properties]**tela, digite o nome e a ID da campanha.
1. Selecione uma data de início e término para sua campanha. Essas datas só se aplicam à própria campanha.

   ![](assets/programs_and_campaigns_8.png)

1. Clique em **[!UICONTROL Create]**para confirmar a criação da campanha.

A campanha é criada e exibida. Use o **[!UICONTROL Create]**botão para adicionar atividades de marketing à sua campanha.

>[!NOTE]
>
>Dependendo do seu contrato de licença, você pode acessar apenas algumas dessas atividades.

Você também pode criar uma campanha na lista de atividades de marketing. Você pode escolher vincular a atividade de marketing a um programa ou subprograma pai pela janela de propriedades da campanha.

## Ícones e status de programas e campanhas {#programs-and-campaigns-icons-and-statuses}

Cada programa e cada campanha na lista tem um símbolo visual e um ícone cuja cor indica o status da execução. Esse status depende do período de validade do programa ou da campanha.

* Cinza: o programa/campanha ainda não começou - **[!UICONTROL Editing]**status.
* Azul: o programa/campanha está em andamento - **[!UICONTROL In progress]**status.
* Verde: o programa/campanha foi concluído - **[!UICONTROL Finished]**status. Por padrão, a data atual é exibida automaticamente como a data de início da validade e a data de término é calculada de acordo com a data de início (** D+186 dias **). É possível alterar essas datas nas propriedades do programa ou da campanha.

![](assets/programs_and_campaigns.png)

