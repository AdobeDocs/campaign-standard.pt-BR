---
solution: Campaign Standard
product: campaign
title: Configuração de acionadores na Experience Cloud
description: 'Saiba como configurar a integração do Adobe Experience Cloud Triggers para começar a enviar deliveries personalizados para seus clientes com base em seus comportamentos anteriores. '
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
feature: Triggers
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '864'
ht-degree: 8%

---


# Configuração de acionadores na Experience Cloud{#configuring-triggers-in-experience-cloud}

## Ativar a funcionalidade {#activating-the-functionality}

A funcionalidade deve ser ativada no Adobe Campaign pelo Adobe. Entre em contato com o executivo da sua conta Adobe ou com o parceiro de serviços profissionais.

A equipe do Adobe precisará das seguintes informações para ativar acionadores:

* Nome da empresa do Marketing Cloud
* IMS Organization ID
* Empresa de logon do Analytics (pode ser igual ao Nome da empresa do Marketing Cloud)

## Configuração de soluções e serviços {#configuring-solutions-and-services}

Para usar esse recurso, você precisa ter acesso às seguintes soluções/principais serviços:

* Adobe Campaign
* Adobe Analytics Select, Prime, Ultimate, Premium, Foundation, OD, Aplicativos para dispositivos móveis ou Standard.
* Serviço principal de acionadores da Experience Cloud

   ![](assets/trigger_uc_prereq_1.png)

* Serviço principal de DTM da Experience Cloud

   ![](assets/trigger_uc_prereq_2.png)

* ID de visitante da Experience Cloud e Serviço principal de Pessoas da Experience Cloud

   ![](assets/trigger_uc_prereq_3.png)

Também é necessário ter um site de trabalho.

![](assets/trigger_uc_prereq_4.png)

>[!CAUTION]
>
>A configuração de subdomínio é um elemento chave de deliverability. Certifique-se de que os emails do Adobe Campaign sejam enviados do mesmo domínio usado pelo site.

Você precisa configurar o [Experience Cloud DTM Core Service](#configuring-experience-cloud-dtm-core-service), [Experience Cloud People Core Service](#configuring-experience-cloud-people-core-service) e [Campaign](#configuring-triggers-and-aliases-in-campaign) para executar esses casos de uso.

### Configuração do serviço principal Experience Cloud DTM {#configuring-experience-cloud-dtm-core-service}

1. No Experience Cloud DTM Core Service (Dynamic Tag Management), ative a Experience Cloud ID e o Adobe Analytics para as páginas do site.

   ![](assets/trigger_uc_conf_1.png)

1. A reconciliação de ID entre o site, o Adobe Analytics e o Adobe Campaign requer o uso de aliasing. Crie um alias, &quot;visitorid&quot; por exemplo.

   ![](assets/trigger_uc_conf_2.png)

### Configurando o Serviço Principal de Pessoas do Experience Cloud {#configuring-experience-cloud-people-core-service}

O alias mencionado anteriormente no DTM precisa ser criado no Serviço principal de pessoas do Experience Cloud por meio de um Atributo do cliente. Crie um novo e faça referência ao mesmo alias do DTM no código de integração (por exemplo, &quot;visitorid&quot;).

![](assets/trigger_uc_conf_3.png)

>[!NOTE]
>
>Usaremos esse Atributo do cliente na Fonte de dados no Adobe Campaign (próxima etapa).

### Configuração de acionadores e aliases no Campaign {#configuring-triggers-and-aliases-in-campaign}

1. Certifique-se de ter **[!UICONTROL Experience Cloud triggers]** visível na instância do Adobe Campaign Standard. Caso contrário, entre em contato com os administradores do Adobe Campaign.

   ![](assets/remarketing_1.png)

1. Os alias permitem que um contato no Analytics seja reconciliado com um perfil no Campaign. Você precisa corresponder os aliases definidos no serviço Experience Cloud ID a uma Fonte de dados compartilhada no Campaign. Você precisa configurar a resolução de aliases no Adobe Campaign por meio de uma fonte de dados ( **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Shared Data Sources]** ). Escolha a fonte de dados correta no menu suspenso **[!UICONTROL Data Source/Alias]**, que é mapeada com a mesma fonte de dados do Atributo do cliente criada na etapa anterior.

   ![](assets/trigger_uc_conf_5.png)

   >[!NOTE]
   >
   >É possível reconciliar os acionadores para usuários anônimos e conectados. Para usuários anônimos, o perfil deve existir no Adobe Campaign e um email foi enviado ao usuário antes. Para isso, a configuração da ID de visitante é suficiente. No entanto, se quiser reconciliar acionadores para usuários conectados, é necessário configurar a Fonte de Dados de ID declarada. Para obter mais informações, consulte [Configuração da fonte de dados](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md#step-2--configure-the-data-sources).

## Criação de um acionador na interface do Experience Cloud {#creating-a-trigger-in-the-experience-cloud-interface}

Um acionador da Adobe Experience Cloud precisa ser criado para que você possa usá-lo no Campaign.

Crie um novo acionador no Experience Cloud e verifique se você selecionou o conjunto de relatórios usado em seu site. Certifique-se de escolher a dimensão correta para que o acionador seja acionado.

Consulte a [documentação do Adobe Experience Cloud](https://docs.adobe.com/content/help/pt-BR/core-services/interface/activation/triggers.html) e assista a este [vídeo](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two).

## Aciona práticas recomendadas e limitações {#triggers-best-practices-and-limitations}

Esta é uma lista de práticas recomendadas e limitações para o uso da integração Campaign - Triggers:

* Se você tiver várias instâncias do Campaign Standard, os acionadores poderão ser recebidos por todas as instâncias, desde que estejam na mesma IMS Organization ID. O Analytics também precisa estar na mesma IMS Organization ID.
* Não é possível criar um acionador no serviço principal do acionador usando eventos de dois conjuntos de relatórios diferentes.
* Os acionadores são baseados em mensagens transacionais. As mensagens transacionais são usadas sempre que é necessário enviar uma mensagem muito rapidamente. Não é possível enfileirar mensagens transacionais e, em seguida, repeti-las em lote.
* Os acionadores não são de natureza determinista. Quando um acionador é gerado, ele envia todos os aliases associados ao cookie. Portanto, no caso de navegadores compartilhados, como em quiosques de varejo, bibliotecas, cyber cafés ou dispositivos compartilhados em casa (marido e esposa fazendo logon pelo mesmo dispositivo), não é possível mapear para a ID correta. Todas as IDs usadas para fazer logon com o navegador são enviadas para o Campaign, que envia uma mensagem com base na primeira reconciliação. Se houver várias &quot;IDs de email&quot; qualificadas para reconciliação, o Campaign não enviará um email. Não há como o Campaign saber qual é a ID de email correta, a menos que seja capturada e enviada pelo Analytics.
* Não é possível armazenar conteúdo do payload no Campaign. Os Acionadores não podem ser usados para atualizar os dados de um perfil.
* Os Atributos do cliente não são suportados em Triggers (ou seja, somente os dados do conjunto de relatórios podem ser usados para definir regras comerciais de Triggers).
* A coleta de coleções não é compatível com o Campaign.

>[!CAUTION]
>
>Seu site deve estar em execução no mesmo domínio que o servidor do Adobe Campaign. Caso contrário, você não poderá usar a id de visitante para reconciliar e entrar em contato com usuários que visitam o site anonimamente.

