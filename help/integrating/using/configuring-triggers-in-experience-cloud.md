---
title: Configuração de acionadores na Experience Cloud
description: 'Saiba como configurar a integração dos Acionadores da Adobe Experience Cloud para enviar delivery personalizados aos seus clientes com base em seus comportamentos anteriores. '
page-status-flag: never-activated
uuid: 8fd7b804-9528-46a5-a060-bf16b8dc555d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
discoiquuid: 4163dc0c-8103-4425-b8bf-7aa45c4d3a06
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: bd74905985734412b4fb11ad11d70faf9fcc9ca6
workflow-type: tm+mt
source-wordcount: '860'
ht-degree: 2%

---


# Configuração de acionadores na Experience Cloud{#configuring-triggers-in-experience-cloud}

## Ativando a funcionalidade {#activating-the-functionality}

A funcionalidade deve ser ativada no Adobe Campaign pela Adobe. Entre em contato com seu parceiro de serviços profissional ou executivo de conta da Adobe.

A equipe da Adobe precisará das seguintes informações para ativar acionadores:

* Nome da Empresa da Marketing Cloud
* ID da organização IMS
* Empresa de logon da Analytics (pode ser igual ao Nome da Empresa da Marketing Cloud)

## Configuração de soluções e serviços {#configuring-solutions-and-services}

Para usar esse recurso, é necessário ter acesso às seguintes soluções/principais serviços:

* Adobe Campaign
* Adobe Analytics Ultimate, Premium, Foundation, OD, Select, Prime, Mobile Apps, Select ou Standard.
* Experience Cloud aciona o serviço principal

   ![](assets/trigger_uc_prereq_1.png)

* Experience Cloud DTM Core Service

   ![](assets/trigger_uc_prereq_2.png)

* ID do Visitante e serviço principal para pessoas Experience Cloud

   ![](assets/trigger_uc_prereq_3.png)

Você também precisa ter um site de trabalho.

![](assets/trigger_uc_prereq_4.png)

>[!CAUTION]
>
>A delegação de subdomínio é um elemento-chave de entrega. Certifique-se de que os emails do Adobe Campaign sejam enviados do mesmo domínio que o usado pelo site.

É necessário configurar o serviço [principal do](#configuring-experience-cloud-dtm-core-service)Experience Cloud DTM, o serviço [principal do](#configuring-experience-cloud-people-core-service) Experience Cloud People e a [Campanha](#configuring-triggers-and-aliases-in-campaign) para executar esses casos de uso.

### Configurando o serviço principal Experience Cloud DTM {#configuring-experience-cloud-dtm-core-service}

1. No Experience Cloud DTM Core Service (Gerenciamento dinâmico de tags), ative a Experience Cloud ID e o Adobe Analytics para as páginas do site.

   ![](assets/trigger_uc_conf_1.png)

1. A reconciliação de ID entre o site, o Adobe Analytics e o Adobe Campaign exige o uso de alias. Crie um alias, &quot;visitorid&quot;, por exemplo.

   ![](assets/trigger_uc_conf_2.png)

### Configurando o serviço principal do Experience Cloud People {#configuring-experience-cloud-people-core-service}

O alias mencionado anteriormente no DTM precisa ser criado no Experience Cloud People Core Service por meio de um Atributo do cliente. Certifique-se de criar um novo e referenciar o mesmo alias do DTM no código de integração (por exemplo, &quot;visitorid&quot;).

![](assets/trigger_uc_conf_3.png)

>[!NOTE]
>
>Usaremos esse Atributo do cliente na fonte de dados no Adobe Campaign (próxima etapa).

### Configuração de acionadores e aliases na Campanha {#configuring-triggers-and-aliases-in-campaign}

1. Verifique se você está **[!UICONTROL Experience Cloud triggers]** visível na sua ocorrência de Adobe Campaign Standard. Caso contrário, entre em contato com os administradores de Adobe Campaign.

   ![](assets/remarketing_1.png)

1. Os alias permitem que um contato no Analytics seja reconciliado com um perfil na Campanha. É necessário corresponder os aliases definidos no serviço de Experience Cloud ID com uma Fonte de dados compartilhada na Campanha. É necessário configurar a resolução de aliases no Adobe Campaign por meio de uma fonte de dados ( **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Shared Data Sources]** ). Certifique-se de escolher a fonte de dados correta no menu **[!UICONTROL Data Source/Alias]** suspenso, que é mapeada com a mesma fonte de dados Atributo do cliente criada na etapa anterior.

   ![](assets/trigger_uc_conf_5.png)

   >[!NOTE]
   >
   >Você pode reconciliar seus acionadores para usuários anônimos e conectados. Para usuários anônimos, o perfil deve existir no Adobe Campaign e um email foi enviado ao usuário antes. Para isso, a configuração da ID do Visitante é suficiente. No entanto, se você deseja reconciliar acionadores para usuários conectados, é necessário configurar a Fonte de Dados de ID declarada. For more on this, refer to [Data Source configuration](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md#step-2--configure-the-data-sources).

## Criação de um acionador na interface do Experience Cloud {#creating-a-trigger-in-the-experience-cloud-interface}

É necessário criar um acionador da Adobe Experience Cloud para que você possa usá-lo na Campanha.

Crie um novo acionador no Experience Cloud e certifique-se de selecionar o conjunto de relatórios usado em seu site. Certifique-se de escolher a dimensão correta para que o acionador seja acionado.

Consulte a documentação [da](https://docs.adobe.com/content/help/en/core-services/interface/activation/triggers.html) Adobe Experience Cloud e assista a este [vídeo](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two).

## Aciona práticas recomendadas e limitações {#triggers-best-practices-and-limitations}

Esta é uma lista de práticas recomendadas e limitações para o uso da Campanha - Acionadores de integração:

* Se você tiver várias instâncias de Campaign Standard, os acionadores poderão ser recebidos por todas as instâncias, contanto que estejam na mesma ID de empresa do IMS. A Analytics também precisa estar na mesma ID de empresa IMS.
* Não é possível criar um acionador no serviço principal do acionador usando eventos de dois conjuntos de relatórios diferentes.
* Os acionadores são baseados em mensagens transacionais. Os Mensagens transacionais são usados sempre que você tem que enviar uma mensagem muito rapidamente. Não é possível colocar mensagens transacionais em fila e, em seguida, colocá-los em loop em lote.
* Os acionadores não são de natureza determinista. Quando um acionador é gerado, ele envia todos os aliases associados ao cookie, de modo que, no caso de navegadores compartilhados, como em quiosques de varejo, bibliotecas, cyber cafés ou dispositivos compartilhados em casa (marido e mulher fazendo login a partir do mesmo dispositivo), não é possível mapear para a ID correta. Todas as IDs usadas para fazer logon com o navegador são enviadas para a Campanha, que envia uma mensagem com base na primeira reconciliação. Se houver várias &quot;IDs de e-mail&quot; elegíveis para reconciliação, a Campanha não enviará um e-mail. Não há como a Campanhas saber qual é a ID de e-mail correta a menos que ela seja capturada e enviada pela Analytics.
* Não é possível armazenar o conteúdo da carga na Campanha. Os acionadores não podem ser usados para atualizar dados de um perfil.
* Atributos do cliente não são suportados em Acionadores (ou seja, somente os dados do conjunto de relatórios podem ser usados para definir regras de negócios de Acionadores).
* A coleção de coleções não é suportada na Campanha.

>[!CAUTION]
>
>Seu site deve estar em execução no mesmo domínio que o servidor Adobe Campaign. Caso contrário, você não poderá usar a ID do visitante para reconciliar e acessar os usuários que visitam o site anonimamente.

