---
solution: Campaign Standard
product: campaign
title: Solicitações de privacidade
description: Saiba como gerenciar solicitações de privacidade no Adobe Campaign Standard
audience: start
content-type: reference
topic-tags: discovering-the-interface
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '1711'
ht-degree: 31%

---


# Gerenciar solicitações de privacidade {#privacy-requests}

For a general presentation on Privacy Management, refer to [this section](../../start/using/privacy-management.md).

Essa informação se aplica a GDPR, CCPA, PDPA e LGPD. Para obter mais informações sobre esses requisitos, consulte [esta seção](../../start/using/privacy-management.md#privacy-management-regulations).

The opt-out for the Sale of Personal Information, which is specific to CCPA, is explained in [this section](#sale-of-personal-information-ccpa).

>[!IMPORTANT]
>
>A utilização da API e da interface do Campaign para solicitações de acesso e exclusão se tornará obsoleta a partir da versão 19.4. Para qualquer solicitação de acesso e exclusão de RGPD, CCPA, PDPA ou LGPD, é necessário usar o método de integração do Privacy Core Service [](#create-privacy-request) .

## Sobre solicitações de privacidade {#about-privacy-requests}

Para ajudá-lo a facilitar sua prontidão para Privacidade, a Adobe Campaign permite que você manipule solicitações de Acesso e Exclusão. O **direito de acesso** e o **direito de ser esquecido** (excluir solicitação) estão descritos [nesta seção](../../start/using/privacy-management.md#right-access-forgotten).

Para executar essas solicitações, é necessário usar a integração do Privacy Core Service **** . As solicitações de privacidade transmitidas a partir do Serviço principal de privacidade para todas as soluções da Experience Cloud são tratadas automaticamente pelo Campaign, por meio de um fluxo de trabalho específico.

### Pré-requisitos {#prerequesites}

Adobe Campaign oferta Data Controllers ferramentas para criar e processar solicitações de Privacidade para dados armazenados no Adobe Campaign. No entanto, é responsabilidade do Controlador de dados gerenciar o relacionamento com o Titular de dados (email, atendimento ao cliente ou um portal da web).

É sua responsabilidade como Controlador de dados confirmar a identidade do Titular de dados que faz a solicitação e pede a confirmação de que os dados retornados ao solicitante pertençam ao Titular de dados.

>[!NOTE]
>
>Para obter mais informações sobre dados pessoais e as diferentes entidades que gerenciam os dados (Controlador de dados, Operador de dados e Titular de dados), consulte [Dados pessoais e Personalidades](../../start/using/privacy.md#personal-data).

### Namespaces {#namesspaces}

Antes de criar solicitações de Privacidade, é necessário definir a namespace que será usada. O namespace é a chave que será usada para identificar o Titular de dados no banco de dados do Adobe Campaign. Dois namespaces estão disponíveis e prontos para a utilização: email e celular. Se precisar de um namespace diferente, como por exemplo um campo de perfil personalizado, siga as etapas a seguir.

Also refer to this [tutorial](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/privacy/namespaces-for-privacy-requests.html?lang=en#privacy) on how to create a namespace.

>[!NOTE]
>
>Se você usar várias namespaces, será necessário criar uma solicitação de Privacidade por namespace.

1. Click the Adobe Campaign logo in the top left corner, then select **[!UICONTROL Administration]** > **[!UICONTROL Namespaces]**.

   ![](assets/privacy-namespaces.png)

1. Na lista do namespace, clique em **[!UICONTROL Create]**.

   ![](assets/privacy-namespace-create.png)

1. Insira um **[!UICONTROL Label]**.

   ![](assets/privacy-namespace-label.png)

1. Se quiser usar uma namespace de serviço de identidade existente, escolha **[!UICONTROL Map from Identity Namespace Service]** e selecione uma namespace na **[!UICONTROL Identity Service Namespaces]** lista.

   ![](assets/privacy-map-from-namespace.png)

   Se quiser criar uma nova namespace no **[!UICONTROL Identity Service]** e mapeá-la na Campanha, selecione **[!UICONTROL Create new]** e insira um nome no **[!UICONTROL Identity namespace name]** campo.

   ![](assets/privacy-create-new-namespace.png)

   Para saber mais sobre namespaces de identidade, consulte a documentação do [Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html?lang=en) .

1. Um namespace do serviço de identidade está mapeado a um namespace no Campaign. É necessário especificar como o namespace será reconciliado no Campaign.

   Selecione um target mapping (**[!UICONTROL Recipients]**, **[!UICONTROL Real-time event]** ou **[!UICONTROL Subscriptions to an application]**). Se quiser usar vários target mapping, é necessário criar uma namespace por target mapping.

   ![](assets/privacy-namespace-target-mapping.png)

1. Escolha o **[!UICONTROL Reconciliation key]**. Este é o campo que será usado para identificar o Titular de Dados no banco de dados do Adobe Campaign.

   ![](assets/privacy-namespace-reconciliation-key.png)

1. Clique em **[!UICONTROL Create]**. Agora você pode criar solicitações de Privacidade com base na sua nova namespace. Se você usar várias namespaces, será necessário criar uma solicitação de Privacidade por namespace.

### Creating a Privacy request {#create-privacy-request}

>[!IMPORTANT]
>
>The **Privacy Core Service** integration is the method you should use for all Access and Delete requests.
>
>A utilização da API e da interface do Campaign para solicitações de acesso e exclusão se tornará obsoleta a partir da versão 19.4. Use o Core Privacy Service para qualquer solicitação de acesso e exclusão do GDPR, CCPA, PDPA ou LGPD.

A Integração do Privacy Core Service permite automatizar suas solicitações de Privacidade em um contexto de várias soluções por meio de uma única chamada JSON API. As solicitações de privacidade transmitidas a partir do Serviço principal de privacidade para todas as soluções da Experience Cloud são tratadas automaticamente pelo Campaign, por meio de um fluxo de trabalho específico.

Refer to the [Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=en) documentation to learn how to create Privacy requests from the Privacy Core Service.

Cada tarefa do serviço principal de privacidade é dividida em várias solicitações de Privacidade na Campanha com base em quantas namespaces estão sendo usadas, uma solicitação correspondente a uma namespace. Além disso, um trabalho pode ser executado em múltiplas instâncias. Portanto, vários arquivos são criados para um trabalho. Por exemplo, se uma solicitação tiver dois namespaces e estiver em execução em três instâncias, então será enviado um total de seis arquivos. Um arquivo por namespace e instância.

O padrão para um nome de arquivo é: `<InstanceName>-<NamespaceId>-<ReconciliationKey>.xml`

* **InstanceName**: nome da instância do Campaign
* **NamespaceId**: ID de Namespace do serviço de identidade da namespace usada
* **Reconciliation key**: chave de reconciliação criptografada

### Lista de recursos {#list-of-resources}

Ao executar uma solicitação de Exclusão ou Privacidade de acesso, a Adobe Campaign pesquisa todos os dados da pessoa de dados com base no valor de **Reconciliação** em todos os recursos que têm um link para o recurso de perfis (tipo próprio).

Aqui está a lista de recursos prontos para utilização que são considerados ao executar solicitações de Privacidade:

* Perfis (recipient)
* Logs do delivery de perfil (wideLogRcp)
* Logs de rastreamento de perfil (trackingLogRcp)
* Logs do delivery (Subscrições para um aplicativo) (wideLogAppSubRcp)
* Registros de rastreamento (assinaturas de um aplicativo) (trackingLogAppSubRcp)
* Subscrições para um aplicativo (appSubscriptionRcp)
* Histórico de subscrições de perfis (subHistoRcp)
* Subscrições Perfil (subscriptionRcp)
* Visitantes (visitante)

Se você criou recursos personalizados que têm um link para o recurso de perfis (tipo próprio), eles também serão considerados. Por exemplo, se você tiver um recurso de transação vinculado ao recurso de perfis e um recurso de detalhes de transação vinculado ao recurso de transação, ambos serão considerados.

Consulte este [tutorial](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/privacy/custom-resources-for-privacy-requests.html?lang=en#privacy) sobre modificação de recursos personalizados.

Para que isso funcione, é necessário selecionar a **[!UICONTROL Deleting the target record implies deleting records referenced by the link]** opção no recurso personalizado:

1. Click the Adobe Campaign logo in the top left corner, then select **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]**.

1. Selecione um recurso personalizado que tenha um link para o recurso de perfis (tipo próprio).

1. Clique na **[!UICONTROL Links]** seção.

1. Para cada link, clique no ícone de lápis (**[!UICONTROL Edit properties]**).

1. Na seção **[!UICONTROL Behavior if deleted/duplicated]** selecione a opção **[!UICONTROL Deleting the target record implies deleting records referenced by the link]**.

   ![](assets/privacy-cus-resource-option.png)

### Status de solicitação de privacidade {#privacy-request-statuses}

Estes são os diferentes status das solicitações de Privacidade:

* **[!UICONTROL New]** / **[!UICONTROL Retry pending]**: em andamento, o fluxo de trabalho ainda não processou a solicitação.
* **[!UICONTROL Processing]** / **[!UICONTROL Retry in progress]**: o fluxo de trabalho está processando a solicitação.
* **[!UICONTROL Delete pending]**: o fluxo de trabalho identificou todos os dados do recipient a serem excluídos.
* **[!UICONTROL Delete in progress]**: o fluxo de trabalho está processando a exclusão.
   <!--**[!UICONTROL Delete Confirmation Pending]** (Delete request in 2-steps process mode): the workflow has processed the Access request. Manual confirmation is requested to perform the deletion. The button is available for 15 days.-->
* **[!UICONTROL Complete]**: o processamento da solicitação foi concluído sem um erro.
* **[!UICONTROL Error]**: o fluxo de trabalho encontrou um erro. O motivo é exibido na lista de solicitações de Privacidade na **[!UICONTROL Request status]** coluna. Por exemplo, **[!UICONTROL Error data not found]** significa que nenhum dado de recipient correspondente aos dados da pessoa de dados **[!UICONTROL Reconciliation value]** foi encontrado no banco de dados.

### Desabilitar o processo de 2 etapas {#disabling-two-step-process}

O Core Privacy Service não é compatível com o processo de duas etapas.

>[!IMPORTANT]
>
>Antes de usar a integração do Core Privacy Service para gerenciar suas solicitações de privacidade, você deve desativar o processo de duas etapas para Excluir solicitações da interface do Campaign Standard.

Se essa opção não estiver desativada, todas as solicitações de exclusão gerenciadas com o Privacy Core Service permanecerão pendentes e não serão concluídas.

Por padrão, o processo de 2 etapas é ativado.

Para alterar esse modo, clique em **[!UICONTROL Edit properties]**, no canto superior direito da **[!UICONTROL Privacy Requests]** tela, em seguida, desmarque a **[!UICONTROL Activate the 2-step process]** opção.

![](assets/privacy-disable-2-step-process.png)

## Recusar a venda de informações pessoais (CCPA) {#sale-of-personal-information-ccpa}

The **California Consumer Privacy Act** (CCPA) provides California residents new rights in regards to their personal information and imposes data protection responsibilities on certain entities whom conduct business in California.

A configuração e utilização dos pedidos de acesso e exclusão são comuns. a GDPR e CCPA. Esta seção apresenta a opção de não participação na venda de dados pessoais, que é específica da CCPA.

In addition to the [Consent management](../../start/using/privacy-management.md#consent-management) tools provided by Adobe Campaign, you have the possibility to track whether a consumer has opted-out for the Sale of Personal Information.

Um cliente decide, por meio do sistema, que não permite que suas informações pessoais sejam vendidas para terceiros. No Adobe Campaign, você poderá armazenar e rastrear essas informações.

>[!NOTE]
>
>Você pode aproveitar a opção de não participação para a venda de informações pessoais por meio da interface de Campanha e da API. Não é possível usá-lo por meio do Privacy Core Service.

>[!IMPORTANT]
>
>É sua responsabilidade como o Controlador de dados receber a solicitação da pessoa de dados e rastrear as datas da solicitação para CCPA. Como provedor de tecnologia, só oferecemos uma maneira de optar por não participar. Para obter mais informações sobre sua função como Controlador de dados, consulte Dados [pessoais e Personas](../../start/using/privacy.md#personal-data).

### Pré-requisito para tabelas personalizadas {#ccpa-prerequisite}

Starting 19.4, the **[!UICONTROL CCPA Opt-Out]** field is provided out-of-the-box in the Campaign interface and API. By default, the field is available for the standard **[!UICONTROL Profile]** resource.

Se você usar um recurso de perfil personalizado, precisará estender o recurso e adicionar o campo. We recommend that you use a different name than the out-of-the-box field, for example:  **[!UICONTROL Opt-Out for CCPA]** (optoutccpa). Quando um campo é criado, ele se torna automaticamente compatível com a API do Campaign.

For more detailed information on how to extend the profile resource, see [this section](../../developing/using/extending-the-profile-resource-with-a-new-field.md).

>[!NOTE]
>
>Modificar recursos é uma operação sensível que deve ser executada somente por usuários especialistas.

1. Vá para **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom Resources]**. Clique no recurso de perfil personalizado. For more on extending a resource, see [this section](../../developing/using/creating-or-extending-the-resource.md).

   ![](assets/privacy-ccpa-extend-cus.png)

1. Clique **[!UICONTROL Add field]** ou **[!UICONTROL Create Element]**, adicione o rótulo, a ID e escolha o **[!UICONTROL Boolean]** tipo. Para o nome, use **Recusar para CCPA**. Na identificação, use:**optOutCcpa**.

   ![](assets/privacy-ccpa-extend-field.png)

1. Na **[!UICONTROL Screen definition]** guia, em **[!UICONTROL Detail screen configuration]**, adicione o campo e selecione **[!UICONTROL Input field]**. O campo ficará disponível na lista e detalhes de perfil.  For more on configuring the screen definition, see [this section](../../developing/using/configuring-the-screen-definition.md).

   ![](assets/privacy-ccpa-extend-screen.png)

1. Vá até **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publishing]**, prepare a publicação e publique as modificações. For more on publishing a resource, see [this section](../../developing/using/updating-the-database-structure.md).

   ![](assets/privacy-ccpa-extend-pub.png)

1. Verifique se o campo está disponível nos detalhes de um perfil. Para obter mais informações, consulte [esta seção](#usage).

### Uso {#usage}

É responsabilidade do Controlador de dados preencher o valor do campo e seguir as diretrizes e regras da CCPA relativas à venda de dados.

Para preencher os valores, vários métodos podem ser utilizados:

* Usando a interface da Campanha editando os detalhes do recipient (veja abaixo)
* Using the Campaign Privacy API (see the [API documentation](../../api/using/managing-ccpa-opt-out.md))
* Através de um fluxo de trabalho de importação

Você deve então garantir que nunca vende a terceiros as informações pessoais de perfis que recusaram a adesão.

1. Na interface do Campaign, edite um perfil para alterar o status de não participação.

   ![](assets/privacy-ccpa-profile-opt-out.png)

1. When the value of the field is **[!UICONTROL True]**, the information is displayed on the profile&#39;s details.

   ![](assets/privacy-ccpa-profile-opt-out-true.png)

1. Você pode configurar a lista de perfis para exibir a coluna de saída. Para saber como configurar o lista, consulte [esta seção](../../start/using/customizing-lists.md).

   ![](assets/privacy-ccpa-profile-configure-list.png)

1. Você pode clicar na coluna para classificar recipient de acordo com as informações de não participação.

   ![](assets/privacy-ccpa-profile-sorting.png)
