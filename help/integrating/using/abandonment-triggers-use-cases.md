---
title: Casos de uso de abandono dos acionadores
description: Saiba como usar a integração Experience Cloud Triggers com esses diferentes casos de uso.
page-status-flag: nunca ativado
uuid: 9e236165-afd5-4155-9151-c1941dc0af99
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: integrando
content-type: referência
topic-tags: trabalhar com campanha e acionadores
discoiquuid: 1b9aeec5-70bb-4d72-a3e9-12342abf08f7
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Casos de uso de abandono dos acionadores{#abandonment-triggers-use-cases}

Esta seção apresenta casos de uso diferentes que podem ser implementados usando a integração entre os Acionadores do Adobe Campaign e da Experience Cloud. Você encontrará dois exemplos de casos de uso:

* [Acionador](#browse-abandonment-trigger)de abandono de navegação: envie uma comunicação aos clientes que abandonaram sua visita em seu site.
* [Acionador](#search-abandonment-trigger)de abandono de pesquisa: envolver-se novamente com visitantes que fizeram uma pesquisa em seu site, mas não fizeram uma compra.

>[!NOTE]
>
>Os casos de uso descritos nesta seção dependem da ID de visitante da Experience Cloud. Também é possível implementá-los com a Experience Cloud Declarated ID. IDs declaradas com hash e criptografadas também são suportadas. Você pode enviar emails/SMS para um perfil que não existe no Campaign descriptografando diretamente o endereço de email/número de celular criptografado. Mas nesse caso, a personalização usando dados de perfil não pode ser usada.

## Pré-requisitos {#pre-requisites}

Para que esses casos de uso sejam implementados, é necessário ter acesso às seguintes soluções/principais serviços:

* Adobe Campaign
* Adobe Analytics Ultimate, Premium, Foundation, OD, Select, Prime, Mobile Apps, Select ou Standard.
* Serviço principal acionadores da Experience Cloud
* Serviço principal da Experience Cloud DTM
* Serviço principal de ID de visitante da Experience Cloud e da Experience Cloud People

Você também precisa ter um site de trabalho.

Para obter mais informações, consulte [Configuração de soluções e serviços](../../integrating/using/configuring-triggers-in-experience-cloud.md#configuring-solutions-and-services).

## Acionador de abandono de navegação {#browse-abandonment-trigger}

Nesse caso de uso, criaremos um acionador simples que será acionado sempre que um cliente abandonar uma visita no site. Este exemplo supõe que você já tenha o DTM coletando e enviando dados para o Adobe Analytics e que todos os eventos sejam criados.

### Criar um acionador da Experience Cloud {#creating-an-experience-cloud-trigger}

1. Selecione **[!UICONTROL Manage Triggers]** no menu Serviço principal de ativação da Experience Cloud.

   ![](assets/trigger_uc_browse_1.png)

1. Escolha um tipo de acionador ( **[!UICONTROL Abandonment]** no caso de uso).

   ![](assets/trigger_uc_browse_2.png)

1. Para este caso de utilização, precisamos de um simples acionador de abandono. O objetivo comercial é identificar os visitantes que navegam pelo nosso site de reservas de viagem, olham para a página "Negociações", mas não reservam nenhuma viagem. Assim que identificarmos esse público, queremos voltar a ele dentro de um curto período de tempo. Neste exemplo, optamos por enviar o acionador após um período de 10 minutos.

   ![](assets/trigger_uc_browse_3.png)

### Uso do acionador no Adobe Campaign {#using-the-trigger-in-adobe-campaign}

Agora que criamos um Acionador da Experience Cloud, vamos usá-lo no Adobe Campaign.

No Adobe Campaign, é necessário criar um Acionador vinculado ao que você criou na Experience Cloud.

1. Para criar o Acionador no Adobe Campaign, clique no **[!UICONTROL Adobe Campaign]** logotipo, no canto superior esquerdo, e selecione **[!UICONTROL Marketing plans]** &gt; **[!UICONTROL Transactional messages]** &gt; **[!UICONTROL Experience Cloud triggers]**.

   ![](assets/remarketing_1.png)

1. Click **[!UICONTROL Create]**.
1. Selecione o Acionador criado anteriormente e clique em **[!UICONTROL Next]**.

   ![](assets/trigger_uc_browse_5.png)

1. Selecione o **[!UICONTROL Email]** canal e a dimensão de **[!UICONTROL Real-time event]** definição de metas e clique em **[!UICONTROL Create]**.

   ![](assets/trigger_uc_browse_6bis.png)

1. Publique o acionador no Adobe Campaign. Esse processo criará automaticamente um modelo de mensagem transacional.

   ![](assets/trigger_uc_browse_6.png)

1. Para exibir o modelo de mensagem, clique no **[!UICONTROL More]** botão, na parte superior direita, e clique em **[!UICONTROL Trigger Transactional Template]**.

1. Personalize o conteúdo e os detalhes do remetente.

   ![](assets/trigger_uc_browse_8.png)

1. Publique o modelo de mensagem. O gatilho agora está ativo e funcional.

   ![](assets/trigger_uc_browse_0.png)

### Executar o cenário {#running-the-scenario}

1. Esse caso de uso começa com um email inicial enviado para seu público-alvo com o Adobe Campaign.

   ![](assets/trigger_uc_browse_9.png)

1. O destinatário abre o email.

   ![](assets/trigger_uc_browse_10.png)

1. Ele clica em um link que o traz ao seu site. Neste exemplo, o banner traz o destinatário para a página inicial do site de reservas de viagem.

   ![](assets/trigger_uc_browse_11.png)

1. O destinatário vai para a página "Negociações", mas de repente interrompe sua visita. Após um período de 10 minutos, o Adobe Campaign aciona o envio da mensagem transacional.

   ![](assets/trigger_uc_browse_12.png)

1. A qualquer momento, você pode verificar os registros da Experience Cloud para ver quantas vezes o acionador foi acionado.

   ![](assets/trigger_uc_browse_13.png)

1. Você também pode exibir o relatório do acionador do Adobe Campaign.

   ![](assets/trigger_uc_browse_14.png)

## Acionador de abandono de pesquisa {#search-abandonment-trigger}

Neste caso de uso, nós vamos criar um acionador para nos relacionar novamente com visitantes que foram ao nosso site de reservas de viagem, pesquisaram por um destino, não encontraram resultados bem-sucedidos e não reservaram nada depois disso. O processo geral é o mesmo do caso de uso anterior (consulte Acionador [de abandono de](#browse-abandonment-trigger)navegação). Vamos focar aqui em como personalizar a mensagem de email de remarketing.

### Criar um acionador da Experience Cloud {#creating-an-experience-cloud-trigger-1}

Siga as etapas descritas no caso de uso anterior para criar o Acionador da Experience Cloud. Consulte [Criar um acionador](#creating-an-experience-cloud-trigger)da Experience Cloud. A principal diferença é a definição da margem de variação.

![](assets/trigger_uc_search_1.png)

A **[!UICONTROL Include Meta Data]** seção permite que você passe todos os dados coletados do Analytics para a carga do acionador. Neste exemplo, criamos uma eVar personalizada (por exemplo, eVar 3) para coletar o termo de pesquisa digitado pelo visitante. Esse termo será usado na mensagem de email transacional enviada ao mesmo visitante.

### Uso do acionador no Adobe Campaign {#using-the-trigger-in-adobe-campaign-1}

1. Siga as etapas descritas no caso de uso anterior para criar o acionador no Adobe Campaign. Consulte [Usar o acionador no Adobe Campaign](#using-the-trigger-in-adobe-campaign). A principal diferença é como acessamos e usamos, no Adobe Campaign, os metadados enviados na carga do Acionador.
1. No acionador de abandono de pesquisa criado no Adobe Campaign, clique no **[!UICONTROL Event content and enrichment]** ícone para exibir a carga enviada para o Adobe Campaign.

   ![](assets/trigger_uc_search_2.png)

1. Como você pode ver, a eVar personalizada é transmitida na carga do Acionador e mapeada para a tabela Contexto **do** evento (ctx). Agora podemos acessá-la para personalizar a mensagem transacional.

   ![](assets/trigger_uc_search_3.png)

1. Neste exemplo, optamos por incluir o termo de pesquisa de destino na linha de assunto, bem como no corpo do email.

   ![](assets/trigger_uc_search_4.png)

1. Ao selecionar um campo personalizado, procure seus metadados de carga na tabela de eventos **** transacionais (rtEvent) e, em seguida, na subtabela de contexto **de** evento (ctx).

   ![](assets/trigger_uc_search_5.png)

### Executar o cenário {#running-the-scenario-1}

1. O visitante acessa o site de reservas de viagem e pesquisa um destino. Neste exemplo, o visitante está procurando uma viagem ao Japão, mas não encontra nenhum resultado. Esta é uma oportunidade para retornarmos a este visitante e recomendarmos um plano de viagem alternativo.

   ![](assets/trigger_uc_search_6.png)

   >[!NOTE]
   >
   >Nesse caso de uso, presumimos que o visitante/destinatário já abriu e clicou em um email originário do mesmo site. Isso nos permite usar e coletar a VisitorID e mapeá-la para o destinatário. Só precisamos fazer isso uma vez.

1. Alguns momentos depois, o mesmo visitante/destinatário recebe uma mensagem de remarketing. A mensagem inclui o destino pesquisado recentemente.

   ![](assets/trigger_uc_search_7.png)

