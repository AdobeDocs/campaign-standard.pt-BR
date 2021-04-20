---
solution: Campaign Standard
product: campaign
title: Salvar público-alvo
description: A atividade Save audience permite atualizar um público-alvo ou criar um novo público-alvo a partir da população computada upstream em um fluxo de trabalho.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: saveAudience,main
feature: Workflows
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '807'
ht-degree: 99%

---


# Salvar público-alvo{#save-audience}

## Descrição {#description}

![](assets/save_audience.png)

A atividade **[!UICONTROL Save audience]** permite atualizar um público-alvo ou criar um novo público-alvo a partir da população computada upstream em um fluxo de trabalho. Os públicos-alvo criados ou atualizados dessa atividade são **Lista** ou **Arquivo**. Eles são adicionadas à lista de públicos-alvo do aplicativo e disponibilizadas pelo menu **[!UICONTROL Audiences]**.

>[!NOTE]
>
>Se o público-alvo criado com a atividade **[!UICONTROL Save audience]** tiver sido enriquecido com dados adicionais, você não poderá usar esses dados para personalizar um delivery independente. Eles só poderão ser usados de um delivery executado em um fluxo de trabalho.

Essa atividade também permite exportar perfis como públicos-alvo/segmentos da Adobe Experience Cloud. Você pode explorar esses públicos-alvo em outras soluções da Adobe Experience Cloud. Para saber mais sobre públicos-alvo compartilhados, consulte [Trabalho com o Campaign e o serviço principal People](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md).

## Contexto de uso {#context-of-use}

A atividade **[!UICONTROL Save audience]** é usada essencialmente para manter os grupos de populações computados no mesmo fluxo de trabalho, convertendo-os em públicos-alvo reutilizáveis.

## Configuração {#configuration}

1. Solte uma atividade **[!UICONTROL Save audience]** no seu fluxo de trabalho.
1. Conecte-a depois das outras atividades de direcionamento, como um query, uma intersecção, uma união ou uma exclusão.
1. Selecione e abra a atividade usando o botão ![](assets/edit_darkgrey-24px.png) das ações rápidas exibidas.
1. Selecione a ação que deseja executar:

   * **[!UICONTROL Update an existing audience]**: selecione um público-alvo e escolha o tipo de atualização:

      * **[!UICONTROL Replace audience content with new data]**: todo o conteúdo do público-alvo é substituído. Os dados antigos são perdidos. Somente os dados da transição de entrada da atividade Save audience são mantidos.
      * **[!UICONTROL Complete audience with new data]**: os dados antigos do público-alvo são mantidos e os dados da transição de entrada da atividade Save audience são adicionados a eles.
   * **[!UICONTROL Create then update an audience]**: insira o nome do público-alvo e selecione o tipo de atualização. Se o público-alvo ainda não existir, ele será criado. Se já existir, será atualizado de acordo com o modo selecionado:

      * **[!UICONTROL Replace audience content with new data]**: todo o conteúdo do público-alvo é substituído. Os dados antigos são perdidos. Somente os dados da transição de entrada da atividade Save audience são mantidos.

         Aviso: essa opção apaga o tipo de público-alvo e o targeting dimension do público-alvo atualizado.

      * **[!UICONTROL Complete audience with new data]**: os dados antigos do público-alvo são mantidos e os dados da transição de entrada da atividade Save audience são adicionados a eles.

         Aviso: essa opção causará um erro se o tipo de público-alvo ou o targeting dimension do público-alvo atualizado não for compatível com a configuração atual do fluxo de trabalho. Por exemplo, não é possível preencher um público-alvo do tipo File com os perfis de um query.
   * **[!UICONTROL Create a new audience]**: insira o nome do público-alvo que será criado. A hora e a data em que o público-alvo é criado serão automaticamente adicionadas ao nome do público-alvo. Isso torna o público-alvo exclusivo toda vez que o fluxo de trabalho é executado.
   * **[!UICONTROL Share in Adobe Experience Cloud]**: se você tiver direcionado perfis e quiser exportar o público-alvo para a Adobe Experience Cloud, selecione essa opção e, em seguida, escolha um público-alvo compartilhado ou crie um novo público-alvo.

      Selecione também uma **[!UICONTROL Shared Data source]** que corresponda ao recurso dos dados contidos no público-alvo para que os dados sejam reconciliados corretamente na Adobe Experience Cloud.

      Com essa opção, o público-alvo compartilhado não é adicionada à lista de públicos-alvo do Adobe Campaign disponíveis no menu **[!UICONTROL Audiences]**.

      >[!NOTE]
      >
      >Essa opção só estará disponível se a funcionalidade de públicos-alvo compartilhadas com a Adobe Experience Cloud tiver sido configurada pelo administrador. Para saber mais, consulte [Trabalho com o Campaign e o serviço principal People](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md).
   O tipo de público-alvo salvo ou disponível durante uma atualização depende das atividades colocadas upstream no fluxo de trabalho.

   Se o targeting dimension do público-alvo for desconhecido quando for salvo (por exemplo, se for de um arquivo importado), o público-alvo será criado ou atualizado como sendo do tipo **[!UICONTROL File]**.

   Se o targeting dimension do público-alvo salvo já estiver definido quando for salvo (por exemplo, se for de um direcionamento, após um query etc.), o público-alvo será salvo ou atualizado como sendo do tipo **[!UICONTROL List]**.

   O conteúdo do público-alvo salvo ficará disponível na visualização detalhada do público-alvo, que pode ser acessada no menu **[!UICONTROL Audiences]**. As colunas disponíveis nessa visualização correspondem às da transição de entrada da atividade Save audience do fluxo de trabalho. Por exemplo, as colunas do arquivo importado, os dados adicionais incluídos de um query.

1. Confirme a configuração da sua atividade e salve o fluxo de trabalho.

## Exemplo {#example}

O fluxo de trabalho definido neste exemplo mostra uma atualização de público-alvo regular do direcionamento:

* Ele é executado automaticamente uma vez por mês usando um **[!UICONTROL Scheduler]**.
* Você pode usar um **[!UICONTROL Query]** para recuperar todos os perfis que fizeram assinatura nos diferentes serviços de aplicativo disponíveis.
* A atividade **[!UICONTROL Save audience]** atualiza o público-alvo excluindo os perfis que cancelaram a assinatura do serviço desde a última execução do fluxo de trabalho e adicionando os perfis que fizeram assinatura recentemente.

![](assets/save_audience_example_1.png)

A atividade **[!UICONTROL Save audience]** é configurada da seguinte maneira:

![](assets/save_audience_example_2.png)

