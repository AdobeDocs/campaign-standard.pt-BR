---
title: Configurar o Unifi para integração do Microsoft Dynamics 365
description: Saiba como configurar o Unifi para integração do Microsoft Dynamics 365
page-status-flag: never-activated
uuid: effa1028-66b2-4bef-b5e4-7319dbb23d5d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
discoiquuid: eb3639f5-7246-46c4-8ddb-da9413b40c32
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 37e86c6143c52841e69d610fa9db35dff70a3587

---



# Configurar o Unifi para integração do Microsoft Dynamics 365

Configure o Unifi para configurar e ativar a integração do Microsoft Dynamics 365 - Adobe Campaign.

## Pré-requisitos

Antes de executar as etapas de pós-provisionamento neste artigo, presume-se que você já concluiu com êxito as etapas de [pós-provisionamento para a Campanha](../../integrating/using/configure-adobe-io-for-ms-dynamic.md) e [para o Dynamics 365](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md).  Se isso não aconteceu, você precisará seguir essas etapas para concluir o Campaign Standard e o pós-provisionamento do Dynamics 365.

Pressupõe-se também que você tenha entrado em contato com a Unifi, que tenha uma conta Unifi criada para você e que tenha conseguido fazer logon com êxito.  Se isso não aconteceu, siga as etapas descritas [neste artigo](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md).

>[!CAUTION]
>
>É altamente recomendável trabalhar com a consultoria Unifi e/ou Adobe (entre em contato com seu Adobe CSM) ao configurar o Unifi.

## Configurar integração de Campanha

Na primeira conexão, clique em **[!UICONTROL Adobe Campaign Standard]** para inserir suas credenciais de Campanha.

A maioria dessas credenciais virá da integração criada no Console de E/S da Adobe durante as etapas [de configuração do](../../integrating/using/configure-adobe-io-for-ms-dynamic.md)Campaign Standard.

>[!NOTE]
>
>Para garantir segurança e privacidade, os campos de credenciais confidenciais aparecem em branco ao revisitar essas telas de configuração.

1. Para o URL de autenticação da Adobe, digite `https://ims-na1.adobelogin.com/ims/exchange/jwt`

1. Entre no seu **[!UICONTROL Adobe IO Organization ID]** e no seu **[!UICONTROL Adobe IO Integration ID]**.

Para obter as IDs de integração e organização de E/S da Adobe, navegue até a tela Integração de console de E/S da Adobe e observe o URL da Web.

Deve ser algo parecido com isto: `https://console.adobe.io/integrations/<Org ID>/<Int ID>/overview`, onde a ID de organização e a ID de entrada são números.

1. Insira sua **[!UICONTROL Tenant ID]**

Para obter a ID do locatário, siga as etapas abaixo:

1. Navegue até o [Adobe Admin Console](https://adminconsole.adobe.com/) e selecione sua Organização IMS no menu suspenso superior direito.
1. Selecione seu produto Adobe Campaign Standard e, em seguida, selecione sua instância Campaign Standard (se você tiver mais de uma).  Isso vai trazer à tona uma lista de perfis de produtos.

   As descrições dos perfis do produto normalmente aparecem em um dos seguintes formatos, onde `<tenantID>` é a ID do locatário da sua instância.

`Campaign Standard – https://<tenantID> - <ROLE>`

`Campaign Standard – <tenantID> - <ROLE>`

>[!NOTE]
>
>Se tiver problemas para identificar sua ID do locatário, entre em contato com você > Contato técnico da Adobe ou Atendimento ao cliente da Adobe.
>
>As IDs de locatário da instância da caixa de proteção do parceiro normalmente seguem o padrão `https://<tenantId>`, onde `tenantId` está `tbd.campaign-sandbox.adobe.com`.

1. Entre no seu **[!UICONTROL Campaign Instance ID]**.

Para obter a ID da instância, siga as etapas abaixo:

    1. Digite &quot;https://&lt;acs-instance-url>/r/test&quot; em um navegador da Web, substituindo &quot;&lt;acs-instance-url>&quot; pelo URL da sua instância do Campaign Standard.
    1. A resposta conterá &quot;instance=&quot;, seguida pela ID da instância.

1. Selecione a região da sua instância de Campanha.

1. Você pode deixar **[!UICONTROL Base Directory]** em branco.

1. Selecione a **[!UICONTROL Allow as Output Destination]** opção.

Depois que os parâmetros forem definidos, clique **[!UICONTROL CONNECT]** e verifique se a conexão foi bem-sucedida.

Caso contrário, clique **[!UICONTROL CLOSE]** e verifique os parâmetros.

>[!NOTE]
>
>Se você não conseguir concluir esta etapa, entre em contato com o serviço [de atendimento ao cliente](mailto:support@unifisoftware.atlassian.net)Unifi.

## Configurar a integração do Dynamics 365

Clique em Microsoft Dynamics CRM para configurar credenciais do Dynamics 365. A maioria dessas credenciais será proveniente da integração criada no Microsoft Dynamics 365 durante as etapas de configuração do Microsoft Dynamics 365.

>[!NOTE]
>
>Para garantir segurança e privacidade, os campos de credenciais confidenciais aparecem em branco ao revisitar essas telas de configuração.

1. Por exemplo, **[!UICONTROL URL]** insira o URL da sua instância do Dynamics 365, tendo cuidado para inserir &quot;.api&quot; antes de &quot;.crm&quot; (por exemplo, `https://mydynamicsinstance.api.crm.dynamics.com`)

1. Por **[!UICONTROL clientid]** exemplo, você usará o ID da aplicação gerado quando criou o registro do aplicativo como [configurando o Dynamics 365](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md).

1. Por **[!UICONTROL clientsecret]** exemplo, você usará o segredo do cliente que foi gerado quando adicionou um segredo do cliente ao registro do aplicativo como [configurando o Dynamics 365](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md).

1. Para **[!UICONTROL callbackurl]**, adicione `http://localhost:33333`.

1. Por **[!UICONTROL refresh token]** favor, deixe em branco.

1. Para a ID **[!UICONTROLdo]** locatário, use a ID do locatário obtida do portal.azure.com como [configurar o Dynamics 365](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md).

1. Por fim, marque a caixa para **[!UICONTROL Allow as Output Destination]**.

Depois que os parâmetros forem inseridos, clique **[!UICONTROL CONNECT]** e verifique se a conexão foi bem-sucedida.

Caso contrário, clique **[!UICONTROL CLOSE]** e verifique os parâmetros.

>[!NOTE]
>
>Se você não conseguir concluir esta etapa, entre em contato com o serviço [de atendimento ao cliente](mailto:support@unifisoftware.atlassian.net)Unifi.

## Conclusão da configuração Unifi

Depois que suas credenciais forem configuradas, você precisará notificar o Unifi, pois algumas etapas adicionais precisam ser executadas antes de concluir a configuração da integração.  Entre em contato com as informações de contato Unifi fornecidas para indicar que você configurou suas credenciais.

É necessário selecionar uma opção de recusa e notificar Unifi quando concluído (indicando ao Unifi qual opção de recusa está sendo selecionada).  Uma explicação das opções de não participação pode ser encontrada no Guia [do Usuário](https://drive.google.com/drive/folders/16seHF45e6bFxHX15zWLqFLEXymCuA_wn)Unifi.

Quando o Unifi concluir o trabalho, ele o notificará e fornecerá mais informações para ajudá-lo a configurar sua instância Unifi, executar a entrada de dados uma vez e, depois de concluída com êxito, você poderá ativar os agendamentos.

A frequência a seguir é recomendada para vários casos de uso:

* Ingresso: A cada 15 minutos
* Fresco: A cada 15 minutos
* Exclui: Todos os dias
* Opções: Todos os dias

>[!NOTE]
>
>Por padrão, os eventos de marketing ENVIAR são filtrados do trabalho de saída.  Se você quiser enviar eventos de marketing no Dynamics 365, é necessário modificar o filtro (etapa 5) do trabalho de saída no Unifi.

Há duas funções separadas no Unifi, um usuário proprietário e um usuário analista somente leitura. Um usuário proprietário tem a capacidade de modificar ordens de produção e programações, enquanto o analista somente leitura não.  Só pode haver um usuário proprietário para uma determinada instância do cliente.  Se o cliente precisar alterar o indivíduo atribuído como o usuário proprietário, ele poderá enviar um email para [adobe-support@unifisoftware.com](mailto:adobe-support@unifisoftware.com) com a alteração solicitada.

A configuração unificada, os detalhes da tarefa, a configuração e o monitoramento são apresentados nos vídeos abaixo.

## Trabalhos Unifi

### Visão geral dos trabalhos Unifi

>[!VIDEO](https://video.tv.adobe.com/v/27392)

Este vídeo explica os diferentes trabalhos Unifi necessários para a integração do Adobe Campaign Standard com o Microsoft Dynamics 365 (02:10 min)

### Detalhes da Tarefa Unifi: Ingresso e saída

>[!VIDEO](https://video.tv.adobe.com/v/27396)

Este vídeo explica os trabalhos de entrada e saída no Unifi (04:27 min)

### Operacionalização e monitoramento

>[!VIDEO](https://video.tv.adobe.com/v/27391)

Este vídeo explica os workflows e horários (03:03 min)

Veja mais aqui
* [Trabalhar com o Adobe Campaign Standard - Microsoft Dynamics 365](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md)
* [Configurar o Microsoft Dynamics 365 para integração com Campanhas](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)
* [Configurar o Adobe IO para Microsoft Dynamics 365 - integração com o Campaign Standard](../../integrating/using/configure-adobe-io-for-ms-dynamic.md)
* [Página de recursos de integração do Microsoft Dynamics 365](https://helpx.adobe.com/campaign/kt/acs/using/acs-ms-dynamics-crm-connector-tutorial.html)