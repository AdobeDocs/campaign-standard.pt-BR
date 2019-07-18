---
title: Tipos de usuários
seo-title: Tipos de usuários
description: Tipos de usuários
seo-description: 'Os usuários do Adobe Campaign detêm funções específicas. Descubra o tipo de usuário principal. '
page-status-flag: nunca ativado
uuid: 8 c 4 cc 74 a -815 f -4815-af 66-a 7 c 21 bc 754 f 1
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: usuários e segurança
discoiquuid: 08 c 8712 a -0066-4 b 8 b -8471-2656 b 8 fb 23 ed
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 866567d63dd2798eb56d42d4e163e5484c9b4d68

---


# Types of users{#types-of-users}

Os administradores podem gerenciar usuários do Admin Console. Os usuários são sincronizados automaticamente com o Adobe Campaign.

For more on this, refer to the [Admin console](https://helpx.adobe.com/enterprise/using/users.html) documentation.

To view the users in Adobe Campaign, click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner, then select **[!UICONTROL Administration > Users & Security > Users]**.

To access the user management interface from Adobe Campaign, click **[!UICONTROL User administration]**.

![](assets/user_management_5.png)

O Adobe Campaign permite atribuir um conjunto de funções aos usuários para definir qual parte da interface que eles podem acessar.

The specific roles and the corresponding authorizations are detailed in the following sections: [understanding roles](../../administration/using/list-of-roles.md) and [authorizations](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf).

Essa segmentação de usuário não é obrigatória, é apenas uma representação do uso mais comum do Adobe Campaign.

Esta seção ajudará você a entender os principais tipos de usuários do Adobe Campaign. Aqui, não entraremos em todas as funções específicas que um usuário pode segurar (iniciar entregas, exportar, preparar entregas etc.). For more information on roles, refer to [List of roles](../../administration/using/list-of-roles.md) and [Managing groups and users](../../administration/using/managing-groups-and-users.md) pages.

Vamos focar em como as diferentes tarefas do Adobe Campaign são divididas entre três tipos principais de usuário:

* [Administradores funcionais](../../administration/using/types-of-users.md#functional-administrators): entre todos os usuários de sua organização, eles são os mais técnicos.
* [Usuários avançados](../../administration/using/types-of-users.md#advanced-users): definem todos os elementos que os profissionais de marketing precisam enviar e monitorar suas entregas.
* [Usuários básicos](../../administration/using/types-of-users.md#basic-users): são profissionais de marketing que personalizam, entregam e monitoram suas campanhas.

>[!NOTE]
>
>Administradores funcionais são diferentes dos administradores técnicos da Adobe. Os administradores técnicos da Adobe detêm uma função interna da Adobe que nenhum cliente pode usar. Gerencie o provisionamento da instância, a hospedagem, o monitoramento de infraestrutura e a supervisão, a solução de problemas técnica.

**Tópicos relacionados:**

* [Vídeo sobre como gerenciar permissões](https://helpx.adobe.com/campaign/kt/acs/using/acs-user-access-rights-feature-video-use.html) de usuário
* [Lista de funções](../../administration/using/list-of-roles.md)
* [Lista de autorizações](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf)

## Functional administrators {#functional-administrators}

Os administradores funcionais são usuários que podem acessar as partes mais técnicas da interface. They hold the **[!UICONTROL Administration]** role and make sure that the platform is all set up so that marketers only have to focus on delivering their campaigns.

Functional administrators are the only users who can access the **[!UICONTROL Administration]** menu, in the Adobe Campaign interface. Since these users need to access technical resources, more advanced roles should be assigned to them, such as the **[!UICONTROL Administration]** and **[!UICONTROL Datamodel]** out-of-the-box roles. These roles are combined in the **[!UICONTROL Administrators]** out-of-the-box security group. For more on this, refer to this [section](../../administration/using/list-of-roles.md).

Estas são as principais tarefas que podem ser realizadas:

* [Gerenciar usuários e permissões](../../administration/using/about-access-management.md): gerenciar o acesso à plataforma (usuários, funções, grupos de segurança, unidades).
* [Configure os diferentes canais](../../administration/using/about-channel-configuration.md): configurar canais de plataforma diferentes, bem como tipologia e gerenciamento de quarentena.
* [Configure as configurações gerais do aplicativo](../../administration/using/external-accounts.md): configurar os diferentes elementos do aplicativo (contas externas, opções, fluxos de trabalho técnicos).
* [Desenvolva novos recursos para aprimorar as funcionalidades inovadoras](../../developing/using/data-model-concepts.md): gerenciar seus recursos personalizados e acessar ferramentas de diagnóstico.
* [Configure os parâmetros de instância](../../administration/using/branding.md): defina suas marcas diferentes e configure suas configurações (logotipo, gerenciamento do rastreamento, domínio do URL para acessar as páginas de aterrissagem etc.).
* [Exportar e importar pacotes de dados](../../automating/using/managing-packages.md): recursos de troca entre diferentes instâncias do Adobe Campaign por meio de arquivos XML estruturados.
* [Exportar logs](../../automating/using/exporting-logs.md) e [definir modelos de importação](../../automating/using/defining-import-templates.md).

## Advanced users {#advanced-users}

Usuários avançados são usuários de marketing que executam os casos de uso mais técnicos no Adobe Campaign. Eles pré-configura todos os elementos que os profissionais de marketing usam para enviar e monitorar suas entregas.

Esse tipo de usuário requer funções mais gerais do que os administradores funcionais, mas ainda deve ser capaz de realizar algumas operações técnicas. To do so, they should be assigned, for example, the **[!UICONTROL Export]**, **[!UICONTROL Generic import]** or **[!UICONTROL Workflow]** out-of-the-box roles. For more on this, refer to this [section](../../administration/using/list-of-roles.md).

Estas são as principais tarefas que podem ser realizadas:

* [Crie e execute fluxos de trabalho complexos de gerenciamento de dados](../../automating/using/about-data-management-activities.md): importar, enriquecer e transformar dados para feed de seu banco de dados ou exportar os dados necessários em arquivos externos para processá-lo em suas próprias ferramentas.
* [Gerenciar modelos](../../start/using/about-templates.md): gerenciar seus modelos para pré-configurar determinados parâmetros de suas atividades de marketing de acordo com suas necessidades.
* [Crie consultas](../../automating/using/editing-queries.md#about-query-editor) e [gerencie seus públicos-alvo](../../audiences/using/about-audiences.md): criar seus públicos-alvo manualmente usando consultas ou usando automaticamente fluxos de trabalho dedicados.
* [Executar edição de expressão avançada](../../automating/using/editing-queries.md#about-query-editor): usar funções avançadas para manipular os valores usados para realizar consultas específicas, como datas, sequências, campos numéricos, classificação etc.
* [Exportar listas](../../automating/using/exporting-lists.md) e [importar dados usando modelos de importação existentes](../../automating/using/importing-data-with-import-templates.md).

## Basic users {#basic-users}

Graças ao administrador funcional e usuários avançados, os profissionais de marketing podem personalizar, entregar e monitorar suas campanhas sem se preocupar com a configuração técnica. To do so, they should be assigned, for example, the **[!UICONTROL Prepare deliveries]**, **[!UICONTROL Workflow]** and **[!UICONTROL Start deliveries]** out-of-the-box roles. These roles are combined in the **[!UICONTROL Standard Users]** out-of-the-box security group. For more on this, refer to this [section](../../administration/using/list-of-roles.md).

Estas são as principais tarefas que podem ser realizadas:

* [Gerenciar programas e campanhas](../../start/using/programs-and-campaigns.md): criar campanhas de marketing, incluindo diferentes tipos de atividade (emails, mensagens SMS, notificações por push, fluxos de trabalho, páginas de aterrissagem).
* Manage [profiles](../../audiences/using/about-profiles.md) and [test profiles](../../sending/using/managing-test-profiles-and-sending-proofs.md): manage the identified and test recipients that will be targeted by your deliveries. Adicione informações, como nome, sobrenome, informações de contato, assinaturas, e-mails etc.
* [Criar e enviar mensagens](../../sending/using/confirming-the-send.md): crie sua mensagem, selecione o público, defina o conteúdo da mensagem e seus elementos de personalização, envie provas e envie a mensagem final para seu público-alvo.
* [Criar e publicar páginas de aterrissagem](../../channels/using/about-landing-pages.md): criar e gerenciar um conjunto de serviços que você deseja oferecer aos clientes, por exemplo, formulários de assinatura ou cancelamento de assinatura.
* [Crie e execute fluxos de trabalho de campanha](../../automating/using/building-a-workflow.md): automatize os processos de campanha usando fluxos de trabalho.
* Monitor your marketing activities through the [available reports](../../reporting/using/defining-the-report-period.md).

