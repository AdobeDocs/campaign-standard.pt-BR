---
title: Criação e atualização de informações de perfil com base em dados de aplicativos móveis
seo-title: Criação e atualização de informações de perfil com base em dados de aplicativos móveis
description: Criação e atualização de informações de perfil com base em dados de aplicativos móveis
seo-description: Saiba como criar e atualizar informações de perfil com base nos dados do aplicativo móvel.
page-status-flag: nunca ativado
uuid: 8 cf 74 cad-b 1 ba -4 aad -83 bd -7289 cb 22 d 5 f 4
contentOwner: lemaitre
products: SG_ CAMPAIGN/STANDARD
audience: canais
content-type: reference
topic-tags: notificações por push
discoiquuid: dc 944 c 85-2059-46 df-b 396-676 fe 3617 dd 1
context-tags: entrega, mobileappcontent, back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 64c7de127285ca56b6af398b0a0c3f1470756fe4

---


# Criação e atualização de informações de perfil com base em dados de aplicativos móveis

## Visão geral

Esta página descreve as etapas para desenvolver um fluxo de trabalho que cria/atualiza dados de perfil depois que um Aplicativo móvel envia dados de PII, com base em programação.

* **As PII** correspondem a «Informações de identificação pessoal». Pode ser qualquer dado, incluindo informações que não aparecem na tabela Perfil do banco de dados da Campanha como, por exemplo, Analytics para [Pontos de interesse móveis](../../integrating/using/about-campaign-points-of-interest-data-integration.md). O PII é definido pelo desenvolvedor de aplicativos móveis, geralmente com um profissional de marketing.
* **Coletar PII** é uma operação HTTP-POST a uma Rest API no Adobe Campaign Standard a partir de um aplicativo móvel.

O objetivo deste caso de uso é criar ou atualizar um perfil da Campanha Standard, se os dados PII retornados por um Aplicativo móvel contiverem dados relacionados ao perfil.

## Pré-requisitos

Há várias etapas de configuração a seguir para ativar notificações por push no Campaign Standard, antes que Perfis possam ser criados ou atualizados com base em dados de Assinatura de aplicativo móvel:

1. [Criar um aplicativo móvel](../../administration/using/configuring-a-mobile-application.md)
1. [Integre o SDK do Adobe Mobile ao seu aplicativo móvel](https://helpx.adobe.com/campaign/kb/integrate-mobile-sdk.html).
1. [Configure o Adobe Campaign para enviar notificações por push](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html).

## Etapa 1 - Estender o recurso de perfil para notificações/assinaturas por push

Para ser capaz de criar ou atualizar o recurso de Perfil com dados PII, é necessário estender o recurso de Perfil com os campos desejados. Para fazer isso:

* Identifique os campos PII enviados pelo Aplicativo móvel.
* Identifique o campo a ser usado na reconciliação para associar os dados PII com os Dados de perfil.

![](assets/update_profile1.png)

Neste exemplo, **[!UICONTROL Fields]** a seção reflete os dados PII enviados pelo Aplicativo móvel. **[!UICONTROL Link to profiles]** A seção indica o campo usado para associar as PII com os Dados de perfil, onde **cusemail** mapeia **para @ email**.

O mapeamento de Dados de perfil ao estender **[!UICONTROL Subscriptions to an Application]** o recurso é SOMENTE LEITURA. É usado para reconciliação. O perfil deve ser inserido no sistema com os dados necessários para reconciliar o perfil com os dados PII. Em nosso caso, um endereço de email para o perfil deve corresponder a um email da coleção de PII para que a reconciliação ocorra:

* Coletar PII é recebido de um aplicativo móvel para um usuário onde seu Nome é «Jane, Sobrenome é «Doe» e o endereço de email é janedoe@doe.com.
* Separadamente, os Dados de perfil devem existir (por exemplo, os dados devem ser inseridos manualmente ou provenientes de algum outro recurso), onde o endereço de email do perfil é janedoe@doe.com.

**Tópicos relacionados:**

* [Estender as assinaturas para um recurso de aplicativo](../../developing/using/extending-the-subscriptions-to-an-application-resource.md).
* [Criação ou extensão de um recurso existente](../../developing/using/key-steps-to-add-a-resource.md).

## Etapa 2 - Criar o fluxo de trabalho

Usar um Fluxo de trabalho no Campaign Standard permite que um administrador identifique e sincronize de forma exclusiva os dados entre os dados de appsubscription (Assinante) e os dados do Perfil ou do Destinatário. Embora uma atualização com base em fluxos de trabalho não sincronize dados de perfil em tempo real, não deve resultar em blocos de banco de dados nem sobrecarga.

As principais etapas para criar o fluxo de trabalho são:

1. Use a **[!UICONTROL Query]** atividade ou **[!UICONTROL Incremental query]** a atividade para obter uma lista das assinaturas mais recentes.
1. Use **[!UICONTROL Reconciliation]** uma atividade para mapear os dados PII com o perfil.
1. Adicione um processo de verificação.
1. Use um **[!UICONTROL Update data]** para atualizar ou criar o perfil com os dados PII.

Os seguintes requisitos são assumidos neste fluxo de trabalho:

* Todos os campos que foram estendidos devem estar disponíveis para criar/atualizar a Tabela de perfil.
* A tabela Perfil pode ser estendida para suportar campos que não são suportados nativamente (por exemplo, Tamanho T-Shirt).
* Qualquer campo da tabela appsubscription em branco não deve ser atualizado na Tabela de perfil.
* Qualquer registro que foi atualizado na tabela appsubscription deve ser incluído na próxima execução do Fluxo de trabalho.

Para criar o fluxo de trabalho, siga as etapas abaixo:

1. Arraste e solte as seguintes atividades na área de trabalho e vincule-as em conjunto:
   1. **[!UICONTROL Start]**
   1. **[!UICONTROL Scheduler]**
   1. **[!UICONTROL Incremental query]**
   1. **[!UICONTROL Update data]**
   ![](assets/update_profile0.png)

1. Configure a **[!UICONTROL Scheduler]** atividade. Na **[!UICONTROL General]** guia, defina o **[!UICONTROL Execution frequency]** (por exemplo, "Diário"), o **[!UICONTROL Time]** (por exemplo, "1:00:00 AM") e o **[!UICONTROL Start]** (por exemplo, a data de hoje).

   ![](assets/update_profile2.png)

1. Configure a **[!UICONTROL Incremental query]** atividade.
   1. Na **[!UICONTROL Properties]** guia, clique no **[!UICONTROL Select an element]** ícone do **[!UICONTROL Resource]** campo e selecione o **[!UICONTROL Subscriptions to an application (nms:appSubscriptionRcp:appSubscriptionRcpDetail)]** elemento.

      ![](assets/update_profile3.png)

   1. Na **[!UICONTROL Target]** guia, arraste o **[!UICONTROL Mobile application]** filtro e selecione um nome de aplicativo móvel.

      ![](assets/update_profile4.png)

   1. Na **[!UICONTROL Processed data]** guia, selecione **[!UICONTROL Use a date field]** e, em seguida, adicione o **[!UICONTROL Last modified (lastModified)]** campo como **[!UICONTROL Path to the date field]**.

      ![](assets/update_profile5.png)

1. Configure a **[!UICONTROL Update data]** atividade.
   1. Na **[!UICONTROL Identification]** guia, verifique se **[!UICONTROL Dimension to update]** o campo está definido como "Perfis (perfil)" e clique no **[!UICONTROL Create element]** botão para adicionar um campo como critério de reconciliação.

      ![](assets/update_profile_createelement.png)

   1. No **[!UICONTROL Source]** campo, selecione um campo da tabela appsubscrsiptionrcp como um campo de reconciliação. Pode ser o email do perfil, crmid, marketingcloudid etc. Neste caso, usaremos o campo "Email (cusemail)".
   1. No **[!UICONTROL Destination]** campo, selecione um campo na tabela de perfil para reconciliar os dados da tabela appsubscriptionrcp. Pode ser o e-mail do perfil ou qualquer campo estendido como crmid, marketingcloudid etc. Neste exemplo, é necessário selecionar o campo "Email (email)" para mapeá-lo com o campo "Email (cusemail)" da tabela appsubscriptionrcp.

      ![](assets/update_profile7.png)

   1. Na **[!UICONTROL Fields to update]** guia, clique no **[!UICONTROL Create element]** botão e mapeie os campos provenientes da tabela appsubscriptionrcp (**[!UICONTROL Source]** campo) com os campos que você deseja atualizar na tabela Perfil (**[!UICONTROL Destination]** campo).
   1. No **[!UICONTROL Enabled if]** campo, adicione uma expressão para garantir que o campo correspondente na tabela Perfil seja atualizado apenas se o campo de origem contiver um valor. Para fazer isso, selecione o campo na lista e adicione o campo "!= "expression (se o campo Origem estiver `[target/@cusEmail]` no Editor de expressão certifique-se de digitar `[target/@cusEmail] != ''"`).

      ![](assets/update_profile8.png)

      >[!NOTE]
      >
      >Nesse caso, o Workflow realiza um UPSERT mas, como se baseia em um dado de Consulta incremental, é inserido apenas. A alteração da consulta pode afetar quais dados são inseridos ou atualizados.
      >Além disso, as configurações na guia Campos para atualizar a guia determinam quais campos são inseridos ou atualizados em condições específicas. Essas configurações podem ser exclusivas para cada aplicativo ou cliente. Tome cuidado ao definir essas configurações como podem haver consequências não intencionais, pois atualizar registros no Perfil com base nos dados do appsubscriptionrcp pode alterar as informações pessoais dos usuários sem validação.

   1. Quando todos os campos para inserir/atualizar no Perfil tiverem sido adicionados, clique **[!UICONTROL Confirm]** em.

      ![](assets/update_profile9.png)

1. Salve o fluxo de trabalho e clique em Iniciar para iniciar o processo de Fluxo de trabalho.

   ![](assets/update_profile10.png)
