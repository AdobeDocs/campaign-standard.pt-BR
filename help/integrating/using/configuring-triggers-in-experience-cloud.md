---
title: Configuração do Triggers na Experience Cloud
description: Saiba como configurar a integração do Adobe Experience Cloud Triggers para começar a enviar entregas personalizadas aos seus clientes com base em seus comportamentos anteriores.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 50e9fb7a-b28a-40b0-9f2c-3673c792529a
source-git-commit: cf2ded703e53d6db27e62712734f7ea846da9a21
workflow-type: tm+mt
source-wordcount: '837'
ht-degree: 6%

---

# Configuração do Triggers na Experience Cloud{#configuring-triggers-in-experience-cloud}

## Ativação da funcionalidade {#activating-the-functionality}

A funcionalidade deve ser ativada no Adobe Campaign pelo Adobe. Entre em contato com o executivo da sua conta Adobe ou com o parceiro de serviços profissionais.

A equipe do Adobe precisará das seguintes informações para ativar os acionadores:

* Nome da empresa do Marketing Cloud
* ID da organização
* Empresa de logon do Analytics (pode ser o mesmo que o Nome da empresa do Marketing Cloud)

## Configuração de soluções e serviços {#configuring-solutions-and-services}

Para usar esse recurso, é necessário ter acesso às seguintes soluções/principais serviços:

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
>A configuração do subdomínio é um elemento principal da capacidade de entrega. Verifique se os emails do Adobe Campaign são enviados do mesmo domínio que o usado pelo site.

Você precisa configurar [Serviço principal do Experience Cloud DTM](#configuring-experience-cloud-dtm-core-service), [Serviço principal de pessoas do Experience Cloud](#configuring-experience-cloud-people-core-service) e [Campaign](#configuring-triggers-and-aliases-in-campaign) para executar esses casos de uso.

### Configuração do serviço principal Experience Cloud DTM {#configuring-experience-cloud-dtm-core-service}

1. No Experience Cloud DTM Core Service (Dynamic Tag Management), ative o Experience Cloud ID e o Adobe Analytics para as páginas do seu site.

   ![](assets/trigger_uc_conf_1.png)

1. A reconciliação de ID entre o site, o Adobe Analytics e o Adobe Campaign exige o uso de alias. Crie um alias, &quot;visitorid&quot; por exemplo.

   ![](assets/trigger_uc_conf_2.png)

### Configuração do Serviço Principal de Pessoas do Experience Cloud {#configuring-experience-cloud-people-core-service}

O alias anteriormente referenciado no DTM precisa ser criado no Experience Cloud People Core Service por meio de um atributo do cliente. Crie um novo e faça referência ao mesmo alias do DTM no código de integração (por exemplo, &quot;visitorid&quot;).

![](assets/trigger_uc_conf_3.png)

>[!NOTE]
>
>Usaremos esse atributo do cliente na fonte de dados na Adobe Campaign (próxima etapa).

### Configuração de acionadores e aliases no Campaign {#configuring-triggers-and-aliases-in-campaign}

1. Verifique se você tem **[!UICONTROL Experience Cloud triggers]** visível na sua instância do Adobe Campaign Standard. Caso não tenha, entre em contato com os administradores do Adobe Campaign.

   ![](assets/remarketing_1.png)

1. Os aliases permitem que um contato no Analytics seja reconciliado com um perfil no Campaign. É necessário corresponder os aliases definidos no serviço de ID de Experience Cloud a uma Fonte de dados compartilhada no Campaign. É necessário configurar a resolução de aliases no Adobe Campaign por meio de uma Fonte de dados ( **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Shared Data Sources]** ). Certifique-se de escolher a fonte de dados correta no **[!UICONTROL Data Source/Alias]** menu suspenso, que é mapeado com a mesma fonte de dados de Atributo do cliente criada na etapa anterior.

   ![](assets/trigger_uc_conf_5.png)

   >[!NOTE]
   >
   >É possível reconciliar acionadores para usuários anônimos e conectados. Para usuários anônimos, o perfil deve existir no Adobe Campaign e um email foi enviado ao usuário antes. Para isso, a configuração da ID de visitante é suficiente. No entanto, se você quiser reconciliar acionadores para usuários conectados, será necessário configurar a Fonte de dados da ID declarada. Para obter mais informações, consulte [Configuração da fonte de dados](../../integrating/using/integration-with-audience-manager-or-people-core-service.md#step-2--configure-the-data-sources).

## Criação de um acionador na interface do Experience Cloud {#creating-a-trigger-in-the-experience-cloud-interface}

Um acionador do Adobe Experience Cloud precisa ser criado para que você possa usá-lo no Campaign.

Crie um novo acionador no Experience Cloud e certifique-se de selecionar o conjunto de relatórios usado em seu site. Escolha a dimensão correta para que o acionador seja acionado.

Consulte a [Documentação do Adobe Experience Cloud](https://experienceleague.adobe.com/docs/experience-cloud/triggers/create.html?lang=pt-BR).

## Práticas recomendadas e limitações dos acionadores {#triggers-best-practices-and-limitations}

Esta é uma lista de práticas recomendadas e limitações para o uso da integração do Campaign com os acionadores:

* Se você tiver várias instâncias do Campaign Standard, os acionadores poderão ser recebidos por todas as instâncias, desde que elas estejam na mesma Organização. O Analytics também precisa estar na mesma organização.
* Não é possível criar um acionador no Serviço principal de acionador usando eventos de dois conjuntos de relatórios diferentes.
* Os acionadores são baseados em mensagens transacionais. As mensagens transacionais são usadas sempre que você precisa enviar uma mensagem muito rapidamente. Não é possível enfileirar mensagens transacionais e depois executá-las em loop em lote.
* Os fatores desencadeantes não são determinísticos por natureza. Quando um acionador é gerado, ele envia todos os aliases associados ao cookie, de modo que, no caso de navegadores compartilhados, como em quiosques de varejo, bibliotecas, cyber cafés ou dispositivos compartilhados em casa (marido e esposa fazendo logon no mesmo dispositivo), não é possível mapear para a ID correta. Todas as IDs usadas para fazer logon com o navegador são enviadas para o Campaign, que envia uma mensagem com base na primeira reconciliação. Se houver várias &quot;IDs de email&quot; qualificadas para reconciliação, o Campaign não enviará um email. Não há como o Campaign saber qual é a ID de email correta, a menos que seja capturada e enviada pelo Analytics.
* Não é possível armazenar o conteúdo da carga no Campaign. Os acionadores não podem ser usados para atualizar os dados de um perfil.
* Os Atributos do cliente não são compatíveis com Acionadores (ou seja, somente os dados do conjunto de relatórios podem ser usados para definir as regras de negócios dos acionadores).
* A coleção de coleções não é compatível com o Campaign.

>[!CAUTION]
>
>Seu site deve estar sendo executado no mesmo domínio que o servidor do Adobe Campaign. Caso contrário, não será possível usar a ID de visitante para reconciliar e entrar em contato com os usuários que visitam o site anonimamente.
