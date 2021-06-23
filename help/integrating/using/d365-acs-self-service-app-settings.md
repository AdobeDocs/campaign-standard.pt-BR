---
title: Configurar o aplicativo de integração Campaign-Dynamics
description: Saiba como configurar o aplicativo de integração Campaign-Dynamics
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Integração do Microsoft CRM
role: Data Architect
level: Intermediate
exl-id: 184bc656-2107-4380-9b35-148cb4380547
source-git-commit: f75df49e7957437df72c814aa9055d34770f22d6
workflow-type: tm+mt
source-wordcount: '795'
ht-degree: 4%

---

# Conectar sistemas com o aplicativo de integração

## Adicionar credenciais ao aplicativo de integração

A tela **[!UICONTROL Settings]** permite especificar as credenciais do Microsoft Dynamics 365 e do Adobe API. Você também pode definir configurações relacionadas à instância SFTP da Adobe Campaign.

### Credenciais do Microsoft Dynamics 365

As credenciais do Microsoft Dynamics 365 dão ao aplicativo de integração permissão para extrair seus dados do Microsoft Dynamics 365.  Primeiro, siga as etapas na tela [Configure Microsoft Dynamics 365 for Campaign integration](../../integrating/using/d365-acs-configure-d365.md) para gerar os valores que serão colados nessa tela. As entradas descritas abaixo farão referência a esta tela.

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-d365.png)

* **[!UICONTROL Client ID]**: Saiba como fazer referência à ID do cliente  [nesta seção](../../integrating/using/d365-acs-configure-d365.md#register-a-new-app)

* **[!UICONTROL Client Secret]**: Saiba como gerar seu Segredo do cliente  [nesta seção](../../integrating/using/d365-acs-configure-d365.md#generate-a-client-secret)

* **[!UICONTROL Tenant]**: Saiba como encontrar sua ID do locatário  [nesta seção](../../integrating/using/d365-acs-configure-d365.md#get-the-tenant-id)

* **[!UICONTROL URL]**: O url terá o formato  `https://&lt;servername&gt;.api.crm.dynamics.com/`

### Credenciais da API do Adobe

As credenciais do Adobe Campaign são geradas usando [Adobe I/O](https://www.adobe.io/). Você precisará visitar a tela [Configure Adobe I/O](../../integrating/using/d365-acs-configure-adobe-io.md) e seguir as instruções antes de preencher as entradas nesta seção.

A imagem a seguir explicará detalhadamente o mapeamento entre o Adobe I/O e as entradas da tela de configurações.

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-adobeio.png)

* *Chave* privada: o processo para definir isso começa clicando no botão &quot;Gerar par chave pública/privada&quot;. Isso criará um arquivo zip que deve ser baixado. Depois de baixá-lo, descompacte o arquivo, o que resultará em dois arquivos chamados certificate_pub.crt e private.key. Coloque a chave privada em um local seguro e não a compartilhe. Abra o arquivo private.key em um editor de texto. Copie o valor inteiro no editor de texto (ctrl-A e ctrl-C em um PC ou cmd-A e cmd-C em um Mac). Isso deve incluir as linhas com &quot;BEGIN PRIVATE KEY&quot; e &quot;END PRIVATE KEY&quot; em sua totalidade. Cole todo este texto de várias linhas na entrada &quot;Chave privada&quot; na tela Configurações.

* *URL*: Esse valor se ajustará ao padrão https\://mc.adobe.io/&lt;campaign-instance-name>. O cabeçalho do aplicativo de integração inclui &quot;Org&quot; e &quot;Instance&quot;. A parte &quot;campaign-instance-name&quot; do url seria simplesmente o nome encontrado neste valor de instância.

## Configurações SFTP da Adobe Campaign {#ac-smtp-settings}

Essas configurações são opcionais. Você precisa defini-los se planeja usar sua instância SFTP da Adobe Campaign para logs de saída do conector. Isso será útil se você tiver problemas quando a integração estiver em execução e precisar depurar por que a saída não atende às suas expectativas.

O outro motivo para configurar o servidor SFTP seria se você planeja executar o fluxo de trabalho de aceitação/rejeição e há um fluxo de dados do Adobe Campaign para o Microsoft Dynamics 365, **[!UICONTROL Unidirectional (Campaign to Microsoft Dynamics 365)]** ou **[!UICONTROL Bidirectional]**.

>[!IMPORTANT]
>
>Você é responsável pelas informações que acessa e baixa das pastas SFTP. Se as informações contiverem dados pessoais, você será responsável por seguir todas as leis e regulamentos de privacidade aplicáveis. [Saiba mais](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-privacy).


Para definir configurações do SFTP do Campaign para a integração com o Microsoft Dynamics 365, acesse a seguinte seção:

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-sftp.png)

Você precisa especificar:

* **Host** SFTP: este campo conterá  &lt;campaign-instance-name>.campaign.adobe.com. O cabeçalho do aplicativo de integração inclui **Org** e **Instance**. A parte &quot;campaign-instance-name&quot; do url seria simplesmente o nome encontrado neste valor de instância.

* **Usuário** SFTP: Se você tiver o usuário SFTP, adicione-o aqui. Caso contrário, consulte [esta seção](#ac-control-panel-settings). Como parte do processo, você receberá o nome de usuário.

* **Chave** SFTP: Se você tiver uma chave SSH, adicione-a aqui. Caso contrário, consulte [esta seção](#ac-control-panel-settings).

* Os **Intervalos IP** serão necessários para serem incluídos na configuração SFTP da Adobe Campaign. Eles precisarão ser incluir na lista de permissões para que a integração use o ponto de extremidade SFTP.

* O **Deseja exportar logs para o SFTP da Adobe Campaign?** O permite determinar se a integração gerará informações de log para o ponto de extremidade SFTP. Isso pode ser usado para ajudar na depuração se o Adobe Campaign ou o Microsoft Dynamics 365 não estiver mostrando as informações que você está esperando.

## Configuração do SFTP no Adobe Campaign {#ac-control-panel-settings}

Descubra o gerenciamento SFTP com [Painel de controle do Campaign](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=pt-BR) nestas seções:

* [Sobre o gerenciamento de SFTP](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/about-sftp-management.html?lang=pt-BR#sftp-management)

* [Gerenciamento de armazenamentos SFTP](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html?lang=en#installing-ssh-key)

* [Adicionar intervalos IP](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/ip-range-allow-listing.html?lang=en#sftp-management)

* [Gerenciar chaves](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html?lang=en#sftp-management)

* [Faça logon no servidor SFTP](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/logging-into-sftp-server.html?lang=en#sftp-management)

Quando a configuração for concluída, faça logon no servidor SFTP com a chave privada e crie o diretório &quot;d365_loads/exports&quot;.

[Visite esta ](https://experienceleague.adobe.com/docs/campaign-standard-learn/control-panel/sftp-management/monitoring-server-capacity.html?lang=en#sftp-management) página para obter informações sobre o servidor SFTP da Adobe Campaign Standard.
