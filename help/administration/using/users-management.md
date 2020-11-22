---
solution: Campaign Standard
product: campaign
title: Gerenciamento de usuários
description: 'Os usuários do Adobe Campaign têm funções específicas. Descubra os principais tipos de usuários. '
audience: administration
content-type: reference
topic-tags: users-and-security
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '1183'
ht-degree: 96%

---


# Gerenciamento de usuários{#users-management}

## Sobre usuários {#about-users}

O Adobe Campaign permite atribuir um conjunto de funções aos usuários para definir qual parte da interface eles podem acessar.

As funções específicas e as autorizações correspondentes são descritas nas seções [Compreensão das funções](../../administration/using/list-of-roles.md) e [Autorizações](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf).

Os administradores podem gerenciar os usuários no Admin Console. Os usuários são sincronizados automaticamente com o Adobe Campaign. Para saber mais, consulte a [documentação do Admin Console](https://helpx.adobe.com/br/enterprise/using/users.html).

Para exibir os usuários no Adobe Campaign, clique no logotipo **[!UICONTROL Adobe Campaign]**, no canto superior esquerdo, e selecione **[!UICONTROL Administration > Users & Security > Users]**.

Para acessar a interface de gerenciamento de usuários no Adobe Campaign, clique em **[!UICONTROL User administration]**.

![](assets/user_management_5.png)

**Tópicos relacionados:**

* Vídeo [Managing user permissions](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/getting-started/access-management.html)
* [Lista de funções](../../administration/using/list-of-roles.md)
* [Lista de autorizações](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf)

## Tipos de usuários {#type-of-users}

Essa segmentação de usuário não é obrigatória. Ela é apenas uma representação do uso mais comum do Adobe Campaign.

Esta seção ajudará você a entender os principais tipos de usuários do Adobe Campaign. Não abordaremos todas as funções específicas de um usuário (iniciar deliveries, exportar, preparar deliveries etc.). Para saber mais sobre funções, consulte as páginas [Lista de funções](../../administration/using/list-of-roles.md) e [Gerenciamento de grupos e usuários](../../administration/using/managing-groups-and-users.md).

Vamos nos concentrar em como as diferentes tarefas no Adobe Campaign são divididas entre três tipos de usuários principais:

* [Administradores funcionais](#functional-administrators): de todos os usuários da organização, eles são os mais técnicos.
* [Usuários avançados](#advanced-users): eles configuram todos os elementos necessários para os profissionais de marketing enviarem e monitorarem os deliveries.
* [Usuários básicos](#basic-users): são os profissionais de marketing que personalizam, entregam e monitoram as campanhas.

>[!NOTE]
>
>Os administradores funcionais são diferentes dos administradores técnicos da Adobe. Os administradores técnicos da Adobe têm uma função interna na Adobe que nenhum cliente pode usar. Eles gerenciam o provisionamento da instância, a hospedagem, o monitoramento e a supervisão da infraestrutura e a solução de problemas técnicos.

### Administradores funcionais {#functional-administrators}

Os administradores funcionais são usuários que podem acessar as partes mais técnicas da interface. Eles assumem a função **[!UICONTROL Administration]** e garantem que a plataforma esteja configurada para que os profissionais de marketing se concentrem apenas no delivery das campanhas.

>[!CAUTION]
>
>Somente administradores funcionais, com **[!UICONTROL Administration]** função e acesso a **Todas** as unidades podem acessar registros de envio, registros de mensagens, logs de rastreamento, registros de exclusão, registros de proposição e registros de subscrições. Um usuário não administrativo pode público alvo desses registros, mas iniciando em uma tabela vinculada (perfis, delivery).

Os administradores funcionais são os únicos usuários que podem acessar o menu **[!UICONTROL Administration]** na interface do Adobe Campaign. Como esses usuários precisam acessar recursos técnicos, as funções mais avançadas devem ser atribuídas a eles, como as funções **[!UICONTROL Administration]** e **[!UICONTROL Datamodel]** prontas para uso. Essas funções são combinadas no grupo de segurança **[!UICONTROL Administrators]** pronto para uso. Para obter mais informações, consulte esta [seção](../../administration/using/list-of-roles.md).

Estas são as principais tarefas que eles podem executar:

* [Gerenciar usuários e permissões](../../administration/using/about-access-management.md): eles gerenciam o acesso à plataforma (usuários, funções, grupos de segurança, unidades).
* [Configurar os diferentes canais](../../administration/using/about-channel-configuration.md): eles configuram os diferentes canais da plataforma, bem como a tipologia e o gerenciamento de quarentenas.
* [Definir as configurações gerais do aplicativo](../../administration/using/external-accounts.md): eles configuram os diferentes elementos do aplicativo (contas externas, opções, fluxos de trabalho técnicos).
* [Desenvolver novos recursos para aprimorar as funcionalidades prontas para uso](../../developing/using/data-model-concepts.md): eles gerenciam seus recursos personalizados e acessam as ferramentas de diagnóstico.
* [Configurar os parâmetros de instância](../../administration/using/branding.md): eles definem suas diferentes marcas e as configurações (logotipo, gerenciamento do rastreamento, domínio de URL para acessar landing pages etc.).
* [Exportar e importar pacotes de dados](../../automating/using/managing-packages.md): eles trocam recursos entre as diferentes instâncias do Adobe Campaign usando arquivos XML estruturados.
* [Exportar logs](../../automating/using/exporting-logs.md) e [definir templates de importação](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates).

### Usuários avançados {#advanced-users}

Os usuários avançados são usuários de marketing que executam os casos de uso mais técnicos no Adobe Campaign. Eles pré-configuram todos os elementos usados pelos profissionais de marketing para enviar e monitorar os deliveries.

Esse tipo de usuário requer funções mais gerais do que os administradores funcionais, mas ainda deve ser capaz de executar algumas operações técnicas. Para isso, eles devem receber, por exemplo, a função **[!UICONTROL Export]**, **[!UICONTROL Generic import]** ou **[!UICONTROL Workflow]** pronta para uso. Para obter mais informações, consulte esta [seção](../../administration/using/list-of-roles.md).

Estas são as principais tarefas que eles podem executar:

* [Criar e executar fluxos de trabalho de gestão de dados complexos](../../automating/using/about-data-management-activities.md): eles importam, enriquecem e transformam dados para alimentar seu banco de dados ou exportam os dados necessários em arquivos externos para processá-los nas próprias ferramentas.
* [Gerenciar templates](../../start/using/marketing-activity-templates.md): eles gerenciam seus templates para pré-configurar parâmetros específicos de atividades de marketing de acordo com suas necessidades.
* [Criar consultas](../../automating/using/editing-queries.md#about-query-editor) e [gerenciar públicos-alvo](../../audiences/using/about-audiences.md): eles criam públicos-alvo manualmente usando consultas ou automaticamente usando fluxos de trabalho dedicados.
* [Executar edição de expressão avançada](../../automating/using/editing-queries.md#about-query-editor): eles usam funções avançadas para manipular os valores aplicados para realizar consultas específicas, como datas, sequências de caracteres, campos numéricos, classificação etc.
* [Exportar listas](../../automating/using/exporting-lists.md) e [importar dados usando templates de importação](../../automating/using/importing-data-with-import-templates.md).

### Usuários básicos {#basic-users}

Graças ao administrador funcional e aos usuários avançados, os profissionais de marketing podem personalizar, entregar e monitorar as campanhas sem se preocupar com a configuração técnica. Para isso, eles devem receber, por exemplo, a função **[!UICONTROL Prepare deliveries]**, **[!UICONTROL Workflow]** e **[!UICONTROL Start deliveries]** pronta para uso. Essas funções são combinadas no grupo de segurança **[!UICONTROL Standard Users]** pronto para uso. Para obter mais informações, consulte esta [seção](../../administration/using/list-of-roles.md).

Estas são as principais tarefas que eles podem executar:

* [Gerenciar programas e campanhas](../../start/using/programs-and-campaigns.md): eles criam campanhas de marketing, inclusive diferentes tipos de atividades (emails, mensagens SMS, notificações por push, fluxos de trabalho, landing pages).
* Gerenciar [perfis](../../audiences/using/about-profiles.md) e [perfis de teste](../../audiences/using/managing-test-profiles.md): eles gerenciam os recipients identificados e de teste que serão direcionados pelos seus deliveries. Eles adicionam informações, como nome, sobrenome, informações de contato, assinaturas, emails etc.
* [Criar e enviar mensagens](../../sending/using/confirming-the-send.md): eles criam a mensagem, selecionam o público-alvo, definem o conteúdo da mensagem e os elementos de personalização e enviam provas e a mensagem final para o público-alvo.
* [Criar e publicar landings pages](../../channels/using/getting-started-with-landing-pages.md): eles criam e gerenciam um conjunto de serviços que você quer oferecer aos clientes, por exemplo, formulários de assinatura ou de unsubscription.
* [Criar e executar workflows da campanha](../../automating/using/building-a-workflow.md): eles automatizam seus processos de campanha usando fluxos de trabalho.
* Monitorar suas atividades de marketing usando os [relatórios disponíveis](../../reporting/using/defining-the-report-period.md).

## Criação de um usuário {#creating-a-user}

Para adicionar um usuário à sua instância, você deve primeiro criá-lo no Admin Console antes de gerenciá-lo no Adobe Campaign Standard.

1. No menu avançado, selecione **[!UICONTROL Administration > Users & Security > Users]** e clique **[!UICONTROL User administration]** para acessar o Admin Console.

   ![](assets/user_management_5.png)

1. Na guia **[!UICONTROL Admin Console]**, clique na guia **[!UICONTROL Users]**.

1. Clique em **[!UICONTROL Add User]**.

   ![](assets/create_user_2.png)

1. Na guia **[!UICONTROL User details]**, preencha os detalhes do usuário, como endereço de email, nome e sobrenome.

   ![](assets/create_user_3.png)

1. Na guia **[!UICONTROL Assign products]**, atribua um ou vários grupos de segurança ao usuário. Para saber mais sobre grupos de segurança, consulte esta [página](../../administration/using/managing-groups-and-users.md).

   Clique em **[!UICONTROL Save]** ao concluir a configuração.

   ![](assets/create_user_4.png)

Seu usuário foi criado e deve receber um redirecionamento por email para a janela a seguir, na qual o usuário precisará definir uma senha e, em seguida, aceitar o termo do contrato de uso. Assim, o usuário poderá se conectar à instância do Adobe Campaign Standard.

![](assets/create_user_5.png)

O usuário será sincronizado com o Adobe Campaign Standard assim que fizer logon na sua instância.

Você pode verificar se o usuário foi sincronizado corretamente com o Adobe Campaign:

1. No menu avançado **[!UICONTROL Administration > Users & Security > Users]**, selecione o usuário criado anteriormente.

1. Atualize as **[!UICONTROL Mobile]**, **[!UICONTROL Time zone]** ou **[!UICONTROL Regional settings]**, se necessário.

1. Verifique o grupo de segurança do usuário. Aqui você pode ver que o usuário recebeu o grupo de segurança **[!UICONTROL Administrators]**.

   >[!NOTE]
   >
   >Os grupos de segurança só podem ser removidos ou adicionados a um usuário no Admin Console.

   ![](assets/create_user_6.png)

1. Verifique **[!UICONTROL Account disabled]** se quiser desativar o usuário.

1. No campo **[!UICONTROL Authorized connection zone]**, selecione como o usuário se conectará a essa instância, por exemplo, pela rede interna ou VPN.

1. Clique em **[!UICONTROL Save]**.

Seu usuário está pronto para usar o Adobe Campaign Standard.
