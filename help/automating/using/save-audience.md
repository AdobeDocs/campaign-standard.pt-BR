---
title: Salvar público-alvo
description: A atividade Salvar público-alvo permite que você atualize um público existente ou crie um novo público-alvo a partir da população computada upstream em um fluxo de trabalho.
page-status-flag: nunca ativado
uuid: 8babb173-fa59-44a7-a2a5-49f45ba6bf99
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: automatização
content-type: referência
topic-tags: atividades de definição de metas
discoiquuid: 1f6bb048-7abd-499b-a4b0-187f9492dc47
context-tags: saveAudience,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Salvar público-alvo{#save-audience}

## Descrição {#description}

![](assets/save_audience.png)

A **[!UICONTROL Save audience]** atividade permite que você atualize um público existente ou crie um novo público-alvo a partir da população computada upstream em um fluxo de trabalho. Os públicos-alvo criados ou atualizados a partir desta atividade são públicos-alvo da **Lista** ou **Arquivo** . Eles são adicionados à lista de públicos do aplicativo e disponibilizados pelo **[!UICONTROL Audiences]** menu.

>[!NOTE]
>
>Se o público-alvo criado pela **[!UICONTROL Save audience]** atividade tiver sido enriquecido com dados adicionais, você não poderá usar esses dados para personalizar uma entrega independente. Eles só podem ser usados a partir de uma entrega executada em um fluxo de trabalho.

Essa atividade também permite exportar perfis como públicos/segmentos da Adobe Experience Cloud. Isso permite que você explore esses públicos-alvo em outras soluções da Adobe Experience Cloud. Para obter mais informações sobre públicos compartilhados, consulte [Trabalhar com o Campaign e o serviço](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md)principal de pessoas.

## Contexto de utilização {#context-of-use}

A **[!UICONTROL Save audience]** atividade é usada essencialmente para manter os grupos de população computados no mesmo fluxo de trabalho, convertendo-os em públicos-alvo reutilizáveis.

## Configuração {#configuration}

1. Solte uma **[!UICONTROL Save audience]** atividade em seu fluxo de trabalho.
1. Conecte-o depois de outras atividades de definição de metas, como uma consulta, uma interseção, uma união ou uma exclusão.
1. Selecione a atividade e abra-a usando o ![](assets/edit_darkgrey-24px.png) botão das ações rápidas que aparecem.
1. Selecione a ação que deseja executar:

   * **[!UICONTROL Update an existing audience]**: Selecione um público-alvo existente e escolha o tipo de atualização:

      * **[!UICONTROL Replace audience content with new data]**: Todo o conteúdo do público-alvo é substituído. Os dados antigos são perdidos. Somente os dados da transição de entrada da atividade salvar público-alvo são mantidos.
      * **[!UICONTROL Complete audience with new data]**: Os dados antigos do público-alvo são mantidos e os dados da transição de entrada da atividade salvar o público-alvo são adicionados a ele.
   * **[!UICONTROL Create then update an audience]**: Insira o nome do público-alvo e selecione o tipo de atualização. Se o público-alvo ainda não existir, ele será criado. Se já existir, será atualizado de acordo com o modo selecionado:

      * **[!UICONTROL Replace audience content with new data]**: Todo o conteúdo do público-alvo é substituído. Os dados antigos são perdidos. Somente os dados da transição de entrada da atividade salvar público-alvo são mantidos.

         Aviso, essa opção apaga o tipo de público-alvo e a dimensão de definição de metas do público-alvo atualizado.

      * **[!UICONTROL Complete audience with new data]**: Os dados antigos do público-alvo são mantidos e os dados da transição de entrada da atividade salvar o público-alvo são adicionados a ele.

         Aviso, essa opção causará um erro se o tipo de público-alvo ou a dimensão de direcionamento do público-alvo atualizado não forem compatíveis com a configuração atual do fluxo de trabalho. Por exemplo, não é possível concluir um público-alvo de tipo de arquivo com perfis que vêm de uma consulta.
   * **[!UICONTROL Create a new audience]**: Insira o nome do público-alvo a ser criado. A hora e a data em que o público-alvo é criado serão automaticamente adicionadas ao nome do público-alvo. Isso torna o público-alvo único toda vez que o fluxo de trabalho é executado.
   * **[!UICONTROL Share in Adobe Experience Cloud]**: Se você tiver perfis direcionados e desejar exportar seu público-alvo para a Adobe Experience Cloud, selecione essa opção e, em seguida, selecione um público-alvo compartilhado existente ou crie um novo público-alvo.

      Selecione também um recurso **[!UICONTROL Shared Data source]** que corresponda ao recurso dos dados contidos no público-alvo para que os dados sejam reconciliados corretamente na Adobe Experience Cloud.

      Usando essa opção, o público-alvo compartilhado não é adicionado à lista de públicos-alvo do Adobe Campaign disponíveis pelo **[!UICONTROL Audiences]** menu.

      >[!NOTE]
      >
      >Essa opção só estará disponível se a funcionalidade de públicos-alvo compartilhados com a Adobe Experience Cloud tiver sido configurada pelo administrador. Para obter mais informações, consulte [Trabalhar com o Campaign e o serviço](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md)principal de pessoas.
   O tipo de público-alvo salvo ou disponível durante uma atualização depende das atividades colocadas em upstream no fluxo de trabalho.

   Se a dimensão de definição de metas do público-alvo for desconhecida quando for salva (por exemplo, se for de um arquivo importado), o público-alvo será criado ou atualizado como um público-alvo **[!UICONTROL File]** tipo.

   Se a dimensão de definição de metas do público-alvo salvo já estiver definida quando for salva (por exemplo, se for proveniente de uma definição de metas, após uma consulta etc.), o público-alvo será salvo ou atualizado como um público-alvo **[!UICONTROL List]** tipo.

   O conteúdo do público-alvo salvo fica disponível na exibição detalhada do público-alvo, que pode ser acessado no **[!UICONTROL Audiences]** menu. As colunas disponíveis nesta exibição correspondem às colunas da transição de entrada da atividade de salvar público-alvo do fluxo de trabalho.  Por exemplo: as colunas do arquivo importado, os dados adicionais adicionados de uma consulta.

1. Confirme a configuração da atividade e salve o fluxo de trabalho.

## Exemplo {#example}

O fluxo de trabalho definido neste exemplo mostra uma atualização regular do público-alvo da definição de metas:

* É executado automaticamente uma vez por mês usando um **[!UICONTROL Scheduler]**.
* Você pode usar um formulário **[!UICONTROL Query]** para recuperar todos os perfis inscritos nos diferentes serviços de aplicativos disponíveis.
* A **[!UICONTROL Save audience]** atividade atualiza o público-alvo excluindo perfis que se cancelaram do serviço desde a última execução do fluxo de trabalho e adicionando os perfis recém-inscritos.

![](assets/save_audience_example_1.png)

A **[!UICONTROL Save audience]** atividade é configurada da seguinte maneira:

![](assets/save_audience_example_2.png)

