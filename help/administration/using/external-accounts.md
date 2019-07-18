---
title: Contas externas
seo-title: Contas externas
description: Contas externas
seo-description: Configure contas externas para configurar conexões com sistemas externos, como servidores SFTP.
page-status-flag: nunca ativado
uuid: 5 d 2 e 2 e 3 d -5 d 1 f -4466-97 e 5-842 c 50390146
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: application-settings
discoiquuid: d 5 c 6 a 3 d 4-f 767-46 c 1-a 8 c 0-3 b 9 dc 52 dcea 8
internal: n
snippet: y
context-tags: Extaccount, main; Extaccount, visão geral
translation-type: tm+mt
source-git-commit: 0fcedd464ae2074e7eda793bbf20cc53ce04f324

---


# External accounts{#external-accounts}

Uma conta externa é uma configuração que permite configurar e testar o acesso a um servidor externo ao Adobe Campaign.

Essas contas externas podem ser usadas nos fluxos de trabalho da Campanha para acessar e gerenciar dados.

Você pode configurar os seguintes tipos de contas externas:

* SFTP. For more on this, refer to [this section](../../administration/using/external-accounts.md#sftp-external-account).
* Amazon Storage Service (S 3). For more on this, refer to [this section](../../administration/using/external-accounts.md#amazon-s3-external-account).
* Adobe Experience Manager. For more on this, refer to [this section](../../administration/using/external-accounts.md#adobe-experience-manager-external-account).
* Adobe Analytics. For more on this, refer to [this section](../../integrating/using/configure-campaign-analytics-integration.md).
* Google recaptcha. For more on this, refer to [this section](../../administration/using/external-accounts.md#google-recaptcha-external-account).

>[!NOTE]
>
>Outros tipos de contas externas são usados pela Adobe durante o processo de provisionamento de produto. Da versão Campaign Standard 17.9, as contas externas FTP ainda podem ser definidas, mas não podem mais ser usadas em novas atividades de fluxo de trabalho. Se você já tiver uma conexão de conexão, ela ainda estará habilitada.

External accounts can be configured by administrators under the **[!UICONTROL Administration > Application settings > External accounts]** menu.

## Creating an external account {#creating-an-external-account}

O Adobe Campaign vem com um conjunto de contas externas pré-definidas. Para configurar conexões com sistemas externos, como servidores FTP usados para transferências de arquivos, você pode criar suas próprias contas externas.

Contas externas são usadas por processos técnicos, como fluxos de trabalho técnicos ou fluxos de trabalho de campanha. Ao configurar uma transferência de arquivo em um fluxo de trabalho ou em um intercâmbio de dados com qualquer outro aplicativo (Adobe Target, Experience Manager etc.), você precisa selecionar uma conta externa.

1. Click the **[!UICONTROL Create]** button.
1. Insira um rótulo. O rótulo e a ID serão usados ao selecionar contas externas nos fluxos de trabalho.
1. Selecione o tipo de conta que deseja criar.
1. Configure o acesso à conta especificando credenciais, endereço do servidor, número da porta e teclas quando relevantes.

   As informações necessárias normalmente são fornecidas pelo provedor do servidor ao qual você está se conectando.

1. Salve sua conta.

A conta externa é criada e adicionada à lista de contas. Agora está disponível para suas transmissões de dados/arquivos ou configurações de roteamento em atividades de fluxo de trabalho e propriedades de entrega.

## SFTP external account {#sftp-external-account}

Tipos de conta externos diferentes exigem informações diferentes para serem especificadas.

Para uma conta externa SFTP, forneça os seguintes detalhes:

* Endereço do servidor. For example, **ftp.domain.com**.
* Número da porta. For example, **22**.
* Credenciais do servidor SFTP: nome da conta e senha usados para se conectar ao servidor.

### Adobe hosted SFTP server recommendations {#adobe-hosted-sftp-server-recommendations}

Ao gerenciar arquivos e dados para fins ETL, esses arquivos são armazenados em um servidor SFTP hospedado fornecido pela Adobe. Esse SFTP foi criado para ser um espaço temporário de armazenamento no qual você pode controlar a retenção e a exclusão de arquivos.

Quando não for usado ou monitorado corretamente, esse espaço pode preencher rapidamente o espaço físico disponível no servidor e causar problemas graves. Isso pode resultar em perda de dados ou corrupção na sua plataforma.

Para evitar esses problemas, a Adobe recomenda seguir as práticas recomendadas abaixo:

* Mantenha os dados mínimos possíveis.
* Use a autenticação com base em chave para evitar a expiração de senha. Supported formats are **OpenSSH** and **SSH2** only. Você precisará fornecer a chave pública para a equipe de suporte da Adobe para que ela carregue no servidor de campanha.
* Mantenha os dados por tempo necessário. 15 dias é o limite máximo de tempo.
* Use fluxos de trabalho para excluir adequadamente os dados (gerenciar a retenção dos fluxos de trabalho lida com os dados).
* Use o agrupamento em uploads SFTP e em fluxos de trabalho.
* Lidar com erros/exceções.
* Ocasionalmente, faça logon no SFTP para verificar diretamente o que está lá.
* Lembre-se de que o gerenciamento de disco SFTP é basicamente sua responsabilidade.

Além disso, observe que os IPs públicos dos quais você está tentando iniciar a conexão SFTP devem ser autorizados na instância Campanha. Whitelisting of IP addresses can be requested via a [support ticket](https://support.neolane.net), along with providing the public key to use for authentication.

Os servidores SFTP podem ser gerenciados pelo Painel de controle. For more information, refer to the [Control Panel documentation](https://helpx.adobe.com/campaign/kb/control-panel-sftp.html).

>[!NOTE]
>
>O Painel de controle está disponível somente para usuários Administradores de clientes hospedados no AWS.
Check if your instance is hosted on AWS [here](https://helpx.adobe.com/campaign/kb/control-panel-faq.html#IMSOrgID).

## Amazon S3 external account {#amazon-s3-external-account}

O campo do servidor Amazon S 3 deve ser preenchido da seguinte maneira:

```
<S3 bucket name>.s3.amazonaws.com/<s3 object path>
```

To store your file in S3 encrypted mode, check the **[!UICONTROL Keep files in S3 encrypted]** box.

![](assets/external_accounts_2.png)

As informações necessárias normalmente são fornecidas pelo provedor do servidor ao qual você está se conectando.

Specify the **[!UICONTROL AWS Region]** associated to your endpoint. You can check the supported regions and signature versions in the official [Amazon S3 documentation](https://docs.aws.amazon.com/general/latest/gr/rande.html#s3_region) .

### Amazon S3 account recommendations {#amazon-s3-account-recommendations}

Para ajudá-lo a configurar sua conta do Amazon S 3, recomendamos que você siga estas recomendações:

* Crie uma política de bucket estrita para restringir o acesso aos buckets S 3. A política de bucket pode ser configurada ao criar um bucket. For more information, refer to the [Amazon S3 documentation](http://docs.aws.amazon.com/AmazonS3/latest/dev//example-bucket-policies.html).
* While creating an external account, enable the encryption to store sensitive data in the S3 bucket by checking the **[!UICONTROL Keep files in S3 encrypted]** box.
* Conceder permissões de bucket para especificar quem pode acessar o objeto em um bucket. For more information on bucket permission, refer to the [Amazon S3 documentation](http://docs.aws.amazon.com/AmazonS3/latest/dev//access-control-overview.html)

## Adobe Experience Manager external account {#adobe-experience-manager-external-account}

As contas externas do Adobe Experience Manager são usadas na integração de Campanha com o Experience Manager.

Process and requirements related to this integration are available in [this document](../../integrating/using/about-campaign-integrations.md).

À medida que você está configurando essa nova conta externa, é necessário fornecer os seguintes detalhes:

* Servidor: digite o URL do servidor Adobe Experience Manager. For example, **http://aem.domain.com:4502**.
* Credenciais de conta AEM: use a conta que acessará a instância do Adobe Experience Manager. Deve ser uma parte da conta do grupo remoto da campanha no Experience Manager.

## Google reCAPTCHA external account {#google-recaptcha-external-account}

>[!NOTE]
>
>A configuração do Google recaptcha requer uma conta do Google.

O mecanismo do Google recaptcha permite proteger sua página inicial por spam e abuso causado por bots. Isso não é intrusivo para seus clientes, pois não exige interação deles e é baseado em interações com seu site. To register your site, refer to this [page](https://www.google.com/recaptcha/admin/create). É necessário escolher o tipo V 3 recaptcha.

Para adicionar a página do Google recaptcha V 3 à página de aterrissagem, primeiro você deve configurá-la em sua conta externa. For more information on how to add it to your landing page, refer to this [section](../../channels/using/designing-a-landing-page.md#setting-google-recaptcha).

Para uma conta externa do Google recaptcha V 3, forneça os seguintes detalhes:

* A **[!UICONTROL Label]** and **[!UICONTROL ID]** of your external account
* **[!UICONTROL Type]**: Google recaptcha
* Your **[!UICONTROL Site key]** and **[!UICONTROL Site secret]**
* A **[!UICONTROL Threshold]** between 0 and 1

   The 0.0 **[!UICONTROL Threshold]** value means that it is likely a bot and 1.0 likely a good interaction. Por padrão, você pode usar um limite de 0.5.

![](assets/external_accounts_3.png)

