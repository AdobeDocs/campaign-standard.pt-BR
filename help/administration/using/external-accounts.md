---
title: Contas externas
description: Configure contas externas para definir conexões com sistemas externos, como servidores SFTP.
page-status-flag: never-activated
uuid: 5d2e2e3d-5d1f-4466-97e5-842c50390146
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: application-settings
discoiquuid: d5c6a3d4-f767-46c1-a8c0-3b9dc52dcea8
internal: n
snippet: y
context-tags: extAccount,main;extAccount,overview
translation-type: tm+mt
source-git-commit: 1f15e28bed22e3defb29f16875fcf4c07f4af5a3
workflow-type: tm+mt
source-wordcount: '1557'
ht-degree: 96%

---


# Contas externas{#external-accounts}

Uma conta externa é uma configuração que permite configurar e testar o acesso a um servidor externo ao Adobe Campaign.

Essas contas externas podem ser usadas em workflows da campanha para acessar e gerenciar dados.

Você pode configurar os seguintes tipos de contas externas:

* SFTP. Para obter mais informações, consulte [esta seção](#sftp-external-account).
* Amazon Storage Service (S3). Para obter mais informações, consulte [esta seção](#amazon-s3-external-account).
* Adobe Experience Manager. Para obter mais informações, consulte [esta seção](#adobe-experience-manager-external-account).
* Adobe Analytics. Para obter mais informações, consulte [esta seção](../../integrating/using/configure-campaign-analytics-integration.md).
* Google reCAPTCHA. Para obter mais informações, consulte [esta seção](#google-recaptcha-external-account).
* Armazenamento do Microsoft Azure Blob. Para obter mais informações, consulte [esta seção](#microsoft-azure-external-account).

>[!NOTE]
>
>Outros tipos de contas externas são usados pela Adobe durante o processo de provisionamento do produto. A partir da versão Campaign Standard 17.9, contas externas FTP ainda podem ser definidas, mas não podem mais ser usadas em novas atividades de workflow. Se você já tiver uma conexão configurada, ela ainda estará ativada.

Contas externas podem ser configuradas pelos administradores no menu **[!UICONTROL Administration > Application settings > External accounts]**.

## Criação de uma conta externa {#creating-an-external-account}

O Adobe Campaign vem com um conjunto de contas externas predefinidas. Para configurar conexões com sistemas externos, como servidores FTP usados para transferir arquivos, você pode criar suas próprias contas externas.

As contas externas são usadas por processos técnicos, como workflows técnicos ou workflows da campanha. Ao configurar uma transferência de arquivos em um workflow ou uma troca de dados com qualquer outro aplicativo (Adobe Target, Experience Manager etc.), você precisa selecionar uma conta externa.

1. Clique no botão **[!UICONTROL Create]**.
1. Insira um rótulo. O rótulo e a ID serão usadas ao selecionar contas externas em workflows.
1. Selecione o tipo de configuração que você deseja criar.
1. Configure o acesso à conta especificando credenciais, o endereço do servidor, o número da porta e ou chaves, quando relevante.

   As informações necessárias geralmente são fornecidas pelo provedor do servidor ao qual você está se conectando.

1. Salve sua conta.

A conta externa é criada e adicionada à lista de contas. Agora está disponível para suas transferências de dados/arquivos ou configurações de roteamento em atividades de workflow e propriedades de entregas.

## Conta externa SFTP {#sftp-external-account}

Tipos de contas externas diferentes exigem que informações diferentes sejam especificadas.

Para uma conta externa SFTP, forneça os seguintes detalhes:

* Endereço do servidor. Por exemplo, **ftp.domain.com**.
* Número da porta. Por exemplo, **22**.
* Credenciais do servidor SFTP: nome da conta e senha usados para a conexão com o servidor.

### Recomendações para servidores SFTP hospedados pela Adobe {#adobe-hosted-sftp-server-recommendations}

Ao gerenciar arquivos e dados para fins de ETL, esses arquivos são armazenados em um servidor SFTP hospedado fornecido pela Adobe. Este SFTP foi projetado para ser um espaço de armazenamento temporário no qual você pode controlar a retenção e exclusão de arquivos.

Quando não for usado ou monitorado corretamente, esse espaço poderá preencher rapidamente o espaço físico disponível no servidor e causar problemas graves. Isso pode resultar na perda ou corrupção de dados na sua plataforma.

Para evitar esses problemas, a Adobe recomenda seguir as práticas recomendadas abaixo:

* Mantenha o mínimo de dados possível.
* Use a autenticação baseada em chave para evitar a expiração da senha. Os formatos compatíveis são apenas **OpenSSH** e **SSH2**. Será necessário fornecer a chave pública para que a equipe de suporte da Adobe possa carregá-la no servidor do Campaign.
* Mantenha os dados apenas pelo tempo necessário. 15 dias é o limite máximo de tempo.
* Use workflows para excluir corretamente os dados (gerencie a retenção de workflows consumindo os dados).
* Use em lotes em uploads de SFTP e em workflows.
* Manipule erros/exceções.
* Ocasionalmente, conecte-se no SFTP para verificar diretamente o que encontra-se lá.
* Lembre-se de que o gerenciamento de disco SFTP é predominantemente sua responsabilidade.

Além disso, observe que os IPs públicos dos quais você está tentando iniciar a conexão SFTP devem ser adicionados à lista de permissões na instância da Campanha. Adding IP addresses to the allowlist can be requested via a [support ticket](https://helpx.adobe.com/br/enterprise/using/support-for-experience-cloud.html), along with providing the public key to use for authentication.

Servidores SFTP podem ser gerenciados no Painel de controle do Campaign. Para obter mais informações, consulte a [documentação do Painel de controle do Campaign](https://docs.adobe.com/content/help/pt-BR/control-panel/using/sftp-management/about-sftp-management.html).

>[!NOTE]
>
>O Painel de controle do Campaign está disponível somente para usuários Administradores de clientes hospedados na AWS.
Verifique [aqui](https://docs.adobe.com/content/help/pt-BR/control-panel/using/faq.html#ims-org-id) se a sua instância está hospedada na AWS.

## Conta externa do Amazon S3 {#amazon-s3-external-account}

O campo de servidor do Amazon S3 deve ser preenchido da seguinte forma:

```
<S3 bucket name>.s3.amazonaws.com/<s3 object path>
```

Para armazenar o arquivo no modo criptografado do S3, marque a caixa **[!UICONTROL Keep files in S3 encrypted]**.

![](assets/external_accounts_2.png)

As informações necessárias geralmente são fornecidas pelo provedor do servidor ao qual você está se conectando.

Especifique o **[!UICONTROL AWS Region]** associado ao seu ponto de extremidade. Você pode verificar as regiões compatíveis e as versões de assinatura na [documentação oficial do Amazon S3](https://docs.aws.amazon.com/general/latest/gr/rande.html#s3_region).

>[!NOTE]
>
>O **[!UICONTROL Receiver server]** deve ser inserido sem a Região da AWS e, posteriormente, ele será adicionado automaticamente ao URL.

### Recomendações para a conta do Amazon S3 {#amazon-s3-account-recommendations}

Para ajudar você a configurar a conta do Amazon S3, siga estas recomendações:

* Crie uma política de bucket estrita para restringir o acesso a buckets do S3. A política de bucket pode ser configurada durante a criação de um bucket. Para obter mais informações, consulte a [documentação do Amazon S3](https://docs.aws.amazon.com/AmazonS3/latest/dev//example-bucket-policies.html).
* Ao criar uma conta externa, ative a criptografia para armazenar dados confidenciais no bucket do S3, marcando a caixa **[!UICONTROL Keep files in S3 encrypted]**.
* Conceda permissões de bucket para especificar quem pode acessar o objeto em um bucket. Para obter mais informações sobre permissão de buckets, consulte a [documentação do Amazon S3](https://docs.aws.amazon.com/AmazonS3/latest/dev//access-control-overview.html).

## Conta externa do Adobe Experience Manager.{#adobe-experience-manager-external-account}

Contas externas do Adobe Experience Manager são usadas ao integrar o Campaign ao Experience Manager.

O processo e os requisitos relacionados a essa integração estão disponíveis [neste documento](../../integrating/using/get-started-campaign-integrations.md).

Como você está configurando essa nova conta externa, é necessário fornecer os seguintes detalhes:

* Servidor: insira o URL do servidor Adobe Experience Manager. Por exemplo:

   ```
   http://aem.domain.com:4502
   ```

* Credenciais da conta do AEM: use a conta que acessará a instância do Adobe Experience Manager. Ela deve ser uma parte da conta do grupo remoto de campanhas no Experience Manager.

## Conta externa do Google reCAPTCHA {#google-recaptcha-external-account}

>[!NOTE]
>
>A configuração do Google reCAPTCHA requer uma conta do Google.

O mecanismo Google reCAPTCHA permite proteger sua landing page contra spam e abuso causado por bots. Esse mecanismo não é intrusivo para os clientes, pois não requer nenhuma interação deles e se baseia em interações com seu site. Para registrar seu site, consulte esta [página](https://www.google.com/recaptcha/admin/create). É necessário escolher o tipo V3 reCAPTCHA.

Para adicionar o Google reCAPTCHA V3 à sua landing page, primeiro é necessário configurá-lo na sua conta externa. Para obter mais informações sobre como adicioná-lo à sua landing page, consulte esta [seção](../../channels/using/configuring-landing-page.md#setting-google-recaptcha).

Para uma conta externa do Google reCAPTCHA V3, forneça os seguintes detalhes:

* Um **[!UICONTROL Label]** e **[!UICONTROL ID]** da sua conta externa
* **[!UICONTROL Type]**: Google reCAPTCHA
* Seu **[!UICONTROL Site key]** e **[!UICONTROL Site secret]**
* Um **[!UICONTROL Threshold]** entre 0 e 1

   O valor **[!UICONTROL Threshold]** 0,0 significa que provavelmente é um bot e 1,0 é provavelmente uma boa interação. Por padrão, você pode usar um limite de 0,5.

![](assets/external_accounts_3.png)

## Conta externa de armazenamento do Microsoft Azure Blob {#microsoft-azure-external-account}

>[!NOTE]
>
>As informações necessárias para configurar sua conta externa no Adobe Campaign Standard podem ser encontradas no Portal do Azure, selecionando **[!UICONTROL Settings]** > **[!UICONTROL Access keys]**.

O conector de armazenamento Azure Blob pode ser usado para importar ou exportar dados para o Adobe Campaign usando uma atividade de workflow **[!UICONTROL Transfer file]**. Para obter mais informações, consulte esta [seção](../../automating/using/transfer-file.md#azure-blob-configuration-wf).

Para uma conta externa de armazenamento do Microsoft Azure Blob, forneça os seguintes detalhes:

* Um **[!UICONTROL Label]** e **[!UICONTROL ID]** da sua conta externa
* **[!UICONTROL Type]**: armazenamento do Microsoft Azure Blob
* Seu **[!UICONTROL Account name]** e **[!UICONTROL Account key]**. Para saber onde encontrar o nome e a chave da sua conta, consulte esta [página](https://docs.microsoft.com/pt-BR/azure/storage/common/storage-account-keys-manage).
* Seu **[!UICONTROL Endpoint suffix]**. Ele pode ser encontrado no **[!UICONTROL Connection string]** do menu **[!UICONTROL Access keys]** no Portal do Azure. Para obter mais informações, consulte esta [página](https://docs.microsoft.com/pt-BR/azure/storage/common/storage-account-keys-manage).
* Seu nome **[!UICONTROL Container]**. Se você estiver planejando usar mais de um container, será necessário criar o mesmo número de contas externas e containers.
* A opção **[!UICONTROL Concurrency]** permite ajustar a velocidade das transferências de arquivos.

![](assets/external_accounts_4.png)

Após a configuração, clique em **[!UICONTROL Test connection]** para vincular o Adobe Campaign ao armazenamento do Microsoft Azure Blob.

### Recomendações para o armazenamento do Microsoft Azure Blob {#azure-blob-recommendations}

**Criptografia**

O Adobe Campaign usa uma conexão segura (HTTPS) para acessar sua conta de armazenamento do Microsoft Azure Blob.

**Chave da conta**

Ao configurar sua conta externa, você deve usar um dos **[!UICONTROL Account key]** disponíveis no Portal do Azure. Para obter mais informações sobre onde encontrar suas chaves de conta, consulte esta [página](https://docs.microsoft.com/pt-BR/azure/storage/common/storage-account-keys-manage#view-access-keys-and-connection-string).

**Otimizar a velocidade de transferência de arquivos**

A opção **[!UICONTROL Concurrency]** permite ajustar a velocidade das transferências de arquivos.
Ela representa o número de threads que serão usados para executar a transferência de arquivos. Cada um desses threads baixará uma parte de aproximadamente 1 MB do blob. Em seguida, eles serão enfileirados para serem gravados em disco. Observe que, ao aumentar o número de threads, você também aumentará a carga dos recursos usados pelo aplicativo durante a transferência de arquivos.

Após a conclusão da transferência de arquivos, você poderá encontrar métricas de desempenho nos logs de Workflow.

**Tentativas**

Por padrão, a transferência de arquivos para o Blob do Azure terá até quatro tentativas.  Se o serviço do Armazenamento do Azure retornar um código de erro, como 503 (servidor ocupado) ou 500 (tempo limite da operação), ele pode indicar que você está se aproximando ou excedendo a escalabilidade da sua conta de armazenamento. Isso pode ocorrer ao usar uma nova conta ou ao executar testes.

Se o erro persistir, será possível aumentar o número de tentativas criando uma opção no menu avançado **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Options]**.

Se implementada, a opção deverá ser criada da seguinte maneira:

```
ID:        AzureBlob_Max_Retries
Date type: Integer
Default:   <the number of retries needed>
```
