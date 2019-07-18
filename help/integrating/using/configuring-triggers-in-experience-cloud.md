---
title: Configuração de acionadores na Experience Cloud
seo-title: Configuração de acionadores na Experience Cloud
description: Configuração de acionadores na Experience Cloud
seo-description: 'Saiba como configurar a integração do Adobe Experience Cloud Triggers para começar a enviar entregas personalizadas a seus clientes com base em seus comportamentos anteriores. '
page-status-flag: nunca ativado
uuid: 8 fd 7 b 804-9528-46 a 5-a 060-bf 16 b-dc 555 d
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
discoiquuid: 4163 dc 0 c -8103-4425-b 8 bf -7 aa 45 c 4 d 3 a 06
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 698466596fdacd005dc4d72b8071208c8c39f77d

---


# Configuring Triggers in Experience Cloud{#configuring-triggers-in-experience-cloud}

## Activating the functionality {#activating-the-functionality}

A funcionalidade deve ser ativada no Adobe Campaign pela Adobe. Entre em contato com seu parceiro de serviços profissionais ou de serviços profissionais da Adobe.

A equipe da Adobe precisará das seguintes informações para ativar acionadores:

* Nome da empresa da Marketing Cloud
* ID ORG IMS
* Empresa de logon do Analytics (pode ser o mesmo que o Nome da empresa da Marketing Cloud)

## Configuring solutions and services {#configuring-solutions-and-services}

Para usar esse recurso, é necessário ter acesso às seguintes soluções/principais serviços:

* Adobe Campaign
* Adobe Analytics Ultimate, Premium, Foundation, OD, Select, Prime, Mobile Apps, Select ou Standard.
* Serviço principal do Experience Cloud Triggers

   ![](assets/trigger_uc_prereq_1.png)

* Serviço principal do DTM da Experience Cloud

   ![](assets/trigger_uc_prereq_2.png)

* ID de visitante da Experience Cloud e Experience Cloud People Core Service

   ![](assets/trigger_uc_prereq_3.png)

Você também precisa ter um site de trabalho.

![](assets/trigger_uc_prereq_4.png)

>[!CAUTION]
>
>A delegação do subdomínio é um elemento de chave de entrega. Certifique-se de que os emails do Adobe Campaign sejam enviados do mesmo domínio que aquele usado pelo site.

You need to configure [Experience Cloud DTM Core Service](../../integrating/using/configuring-triggers-in-experience-cloud.md#configuring-experience-cloud-dtm-core-service), [Experience Cloud People Core Service](../../integrating/using/configuring-triggers-in-experience-cloud.md#configuring-experience-cloud-people-core-service) and [Campaign](../../integrating/using/configuring-triggers-in-experience-cloud.md#configuring-triggers-and-aliases-in-campaign) to run these use cases.

### Configuring Experience Cloud DTM Core Service {#configuring-experience-cloud-dtm-core-service}

1. No serviço principal do DTM da Experience Cloud (Gerenciamento dinâmico de tags), ative a Experience Cloud ID e o Adobe Analytics para as páginas do site.

   ![](assets/trigger_uc_conf_1.png)

1. A reconciliação de ID entre o site, o Adobe Analytics e o Adobe Campaign requer a utilização de alias. Crie um alias, "visitorid", por exemplo.

   ![](assets/trigger_uc_conf_2.png)

### Configuring Experience Cloud People Core Service {#configuring-experience-cloud-people-core-service}

O alias referenciado anteriormente no DTM precisa ser criado no Experience Cloud Popular Core Service por meio de um atributo do cliente. Certifique-se de criar uma nova e fazer referência ao mesmo alias do DTM no código de integração (por exemplo, "visitorid").

![](assets/trigger_uc_conf_3.png)

>[!NOTE]
>
>Usaremos esse atributo do cliente na fonte de dados no Adobe Campaign (próxima etapa).

### Configuring triggers and aliases in Campaign {#configuring-triggers-and-aliases-in-campaign}

1. **[!UICONTROL Experience Cloud triggers]** Verifique se você está visível na sua instância do Adobe Campaign Standard. Caso não queira, entre em contato com os administradores do Adobe Campaign.

   ![](assets/remarketing_1.png)

1. Aliases permitem que um contato no Analytics seja reconciliado com um perfil no Campaign. É necessário corresponder aos aliases definidos no serviço da Experience Cloud ID com uma Fonte de dados compartilhados no Campaign. You need to configure the aliases resolution in Adobe Campaign via a Data source ( **[!UICONTROL Administration]** &gt; **[!UICONTROL Application Settings]** &gt; **[!UICONTROL Shared Data Sources]** ). Make sure you choose the correct data source in the **[!UICONTROL Data Source/Alias]** drop-down menu, which is mapped with the same Customer Attribute data source created in previous step.

   ![](assets/trigger_uc_conf_5.png)

   >[!NOTE]
   >
   >Você pode conciliar seus acionadores para usuários anônimos e conectados. Para usuários anônimos, o perfil deve existir no Adobe Campaign e um e-mail já foi enviado para o usuário. Para isso, a configuração da ID do visitante é suficiente. No entanto, se você quiser reconciliar acionadores para usuários conectados, precisará configurar a Fonte de Dados ID declarada. For more on this, refer to [Data Source configuration](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md#step-2--configure-the-data-sources).

## Creating a trigger in the Experience Cloud interface {#creating-a-trigger-in-the-experience-cloud-interface}

É necessário criar um acionador da Adobe Experience Cloud para que você possa usá-lo no Campaign.

Crie um novo disparador na Experience Cloud e certifique-se de selecionar o conjunto de relatórios usado em seu site. Certifique-se de escolher a dimensão certa para que o acionador seja acionado.

Refer to the [Adobe Experience Cloud documentation](https://marketing.adobe.com/resources/help/en_US/mcloud/triggers.html) and watch this [video](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two).

## Triggers best practices and limitations {#triggers-best-practices-and-limitations}

Esta é uma lista das práticas recomendadas e limitações para o uso da campanha - Integração com Acionadores:

* Se você tiver várias instâncias do Campaign Standard, poderá ser recebido por todas as instâncias, desde que estejam na mesma ID organizacional IMS. O Analytics também precisa estar na mesma ID organizacional IMS.
* Não é possível criar um acionador no Acionador do serviço principal usando eventos de dois conjuntos de relatórios diferentes.
* Os Acionadores têm por base mensagens transacionais. As mensagens transacionais são usadas sempre que você precisa enviar uma mensagem muito rapidamente. Não é possível colocar mensagens transacionais em fila e, em seguida, agrupá-las em lote.
* Os acionadores não são determinísticos na natureza. Quando um acionador é gerado, ele envia todos os aliases associados ao cookie, portanto, no caso de navegadores compartilhados, como quiosques de varejo, bibliotecas, cafés ciber ou dispositivos compartilhados na casa (logon do mesmo dispositivo), não é possível mapear para a ID correta. Todas as IDs usadas para fazer login com o navegador são enviadas para a Campanha que envia uma mensagem com base na primeira reconciliação. Se houver várias "IDs de email" elegíveis para a reconciliação, então a Campanha não enviará um e-mail. Não há forma da Campanha saber o que é a ID de email correta, a menos que seja capturada e enviada pelo Analytics.
* Não é possível armazenar conteúdo da carga no Campaign. Os acionadores não podem ser usados para atualizar os dados de um perfil.
* Atributos do cliente não são suportados em Acionadores (ou seja, somente os dados do conjunto de relatórios podem ser usados para definir regras de negócios acionadores).
* A coleção de coleções não é suportada no Campaign.

>[!CAUTION]
>
>Seu site deve estar em execução no mesmo domínio do servidor do Adobe Campaign. Caso contrário, não será possível usar a ID do visitante para reconciliar e entrar em contato com os usuários que visitam o site anonimamente.

