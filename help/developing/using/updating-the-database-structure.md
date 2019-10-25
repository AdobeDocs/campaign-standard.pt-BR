---
title: Atualização da estrutura do banco de dados
seo-title: Atualização da estrutura do banco de dados
description: Atualização da estrutura do banco de dados
seo-description: Saiba como atualizar o banco de dados do Adobe Campaign.
page-status-flag: nunca ativado
uuid: 6c802f4f-d298-4ca4-acdb-09f2ad3865b9
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: desenvolvimento
content-type: referência
topic-tags: adição ou extensão de um recurso
discoiquuid: 2448b126-66b8-4608-aa6c-8028fb1902a4
context-tags: implantação,main;eventCusResource,visão geral
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 51d80fc9c683e39b9d08ba7d36b76b71a9dd1e8c

---


# Atualização da estrutura do banco de dados{#updating-the-database-structure}

Para tornar suas modificações no modelo de dados efetivas e capazes de usá-las, a estrutura do banco de dados precisa ser atualizada.

>[!NOTE]
>
>Os recursos personalizados são atualizados automaticamente durante atualizações automáticas executadas pela Adobe.

## Publicar um recurso personalizado {#publishing-a-custom-resource}

Para aplicar as alterações realizadas nos recursos, é necessário executar uma atualização do banco de dados.

>[!NOTE]
>
>Se um campo de um recurso personalizado usado em um evento for modificado ou excluído, o evento correspondente será automaticamente despublicado. Consulte [Configuração de mensagens](../../administration/using/configuring-transactional-messaging.md)transacionais.

1. No menu avançado, por meio do logotipo do Adobe Campaign, selecione **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** e, em seguida, **[!UICONTROL Publishing]**.
1. Por padrão, a opção **[!UICONTROL Determine modifications since the last publication]** está marcada, o que significa que somente as alterações realizadas desde a última atualização serão aplicadas.

   >[!NOTE]
   >
   >O **[!UICONTROL Repair database structure]** restabelecerá uma configuração correta se a publicação falhar antes de concluir. Qualquer modificação que tenha sido feita diretamente no banco de dados e que não use recursos personalizados será excluída.

   ![](assets/schema_extension_12.png)

1. Clique no **[!UICONTROL Prepare publication]** botão para iniciar a análise. Observe que as grandes atualizações de tabela devem ser feitas quando a instância não estiver intensamente ocupada por fluxos de trabalho.

   Para saber mais sobre a ação a ser executada na API Perfis e serviços, consulte [Publicação de um recurso com extensão](#publishing-a-resource-with-api-extension)da API.

   ![](assets/schema_extension_13.png)

1. Depois que a publicação for realizada, clique no **[!UICONTROL Publish]** botão para aplicar suas novas configurações.
1. Depois de publicado, o **[!UICONTROL Summary]** painel de cada recurso indica que o status está agora **[!UICONTROL Published]** e especifica a data da última publicação.

   >[!NOTE]
   >
   >Se você fizer novas alterações em um recurso, deverá repetir essa operação para que as alterações sejam aplicadas.

   Se os recursos tiverem o **[!UICONTROL Pending re-draft]** status antes da publicação, será exibida uma mensagem adicional convidando você a verificar suas ações, pois a publicação resultará em alterações definitivas (excluindo colunas, tabelas...). Para ajudá-lo a realizar essa última alteração, uma **[!UICONTROL SQL Script]** guia está disponível. Ele fornece o comando SQL que será executado durante a publicação.

   ![](assets/schema_extension_scriptsql.png)

   >[!NOTE]
   >
   >Você pode interromper o processo de Rerascunho clicando no **[!UICONTROL Cancel re-draft]** botão. Esta ação reverterá o status do recurso para o status original.

1. Se sua publicação falhou, você sempre pode voltar para a publicação anterior clicando em **[!UICONTROL Back to latest successful publication]**.

   Observe que, se você deixar sua publicação em um status de falha, uma janela pop-up será aberta assim que você fizer logon em sua instância para lembrá-lo de corrigir essa publicação. Sua instância não será atualizada com novas versões de produtos até que sua publicação seja corrigida.

   ![](assets/schema_extension_31.png)

## Publicar um recurso com extensão de API {#publishing-a-resource-with-api-extension}

Você pode criar a API de perfil e serviços nos seguintes casos:

* Ao estender os recursos personalizados **[!UICONTROL Profiles]** ou **[!UICONTROL Services]**, você pode executar uma atualização da API Perfis e serviços para integrar os campos declarados na extensão de recursos personalizados.
* Ao definir um recurso personalizado e criar um link entre os recursos **[!UICONTROL Profiles]** ou **[!UICONTROL Services]** e o recurso personalizado, você pode fazer uma atualização para incluir o novo recurso na API.

Você pode selecionar essa opção na tela da publicação.

* Se a API ainda não tiver sido publicada (ou seja, se você nunca tiver estendido o recurso ou se ainda não tiver verificado essa opção para esse recurso ou outro recurso), você terá a opção de criá-lo ou não.

   ![](assets/create-profile-and-services-api.png)

* Se a API já tiver sido publicada (ou seja, se você já tiver estendido o recurso e verificado essa opção uma vez), a atualização da API será forçada.

   Na verdade, uma vez criada, a API é atualizada automaticamente sempre que você a publica novamente. Isso evita quebrar o perfil ou o recurso de serviço dessa API e prejudicar sua instância.

Observe que, por padrão, o recurso personalizado é integrado, mas, para um comportamento específico, se você não quiser publicar esse recurso, poderá selecionar a opção **[!UICONTROL Hide this resource from APIs]** disponível no **[!UICONTROL Resource Properties]**.

![](assets/removefromextoption.png)

Após a **[!UICONTROL Prepare Publication]** etapa, o Adobe Campaign exibe o delta entre a versão atual da API e a versão futura após a publicação na guia **[!UICONTROL Profiles & Services API Preview]**. Se você estender a API pela primeira vez, o delta compara a definição de recurso personalizado predefinida com sua extensão.

As informações exibidas na guia são divididas em três seções: elementos adicionados, excluídos e modificados.

![](assets/extendpandsapi_diff.png)

A análise do delta é uma etapa obrigatória, já que a etapa de publicação modificará o comportamento da API e provavelmente afetará o desenvolvimento ao redor em um efeito dominó.

>[!NOTE]
>
>Esta publicação atualiza a **[!UICONTROL profilesAndServicesExt]** API. A **[!UICONTROL profilesAndServices]** API não foi atualizada.

Para obter mais informações sobre a API do Adobe Campaign, consulte a documentação dedicada do Adobe Campaign no E/S [da Adobe](https://docs.campaign.adobe.com/doc/standard/en/adobeio.html).
