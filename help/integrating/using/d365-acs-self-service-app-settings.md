---
title: Configurar o aplicativo de integração Campaign-Dynamics
description: Saiba como configurar o aplicativo de integração Campaign-Dynamics
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
translation-type: tm+mt
source-git-commit: 6be7a20cde8fcaee73972b8919765ea631f2f1ee
workflow-type: tm+mt
source-wordcount: '795'
ht-degree: 2%

---


# Conecte sistemas com o aplicativo de integração

## Adicionar credenciais ao aplicativo de integração

A tela **[!UICONTROL Settings]** permite que você especifique as credenciais da API do Microsoft Dynamics 365 e do Adobe. Você também pode definir as configurações relacionadas à instância Adobe Campaign SFTP.

### Credenciais do Microsoft Dynamics 365

As credenciais do Microsoft Dynamics 365 concedem ao aplicativo de integração permissão para extrair seus dados do Microsoft Dynamics 365.  Primeiro, siga as etapas na tela [Configure o Microsoft Dynamics 365 para integração de Campanha](../../integrating/using/d365-acs-configure-d365.md) para gerar os valores que serão colados nesta tela. As entradas descritas abaixo farão referência a esta tela.

![](assets/d365-to-acs-ui-page-workflows-settings-d365.png)

* **[!UICONTROL Client ID]**: Saiba como fazer referência à ID do cliente  [nesta seção](../../integrating/using/d365-acs-configure-d365.md#register-a-new-app)

* **[!UICONTROL Client Secret]**: Saiba como gerar o segredo do cliente  [nesta seção](../../integrating/using/d365-acs-configure-d365.md#generate-a-client-secret)

* **[!UICONTROL Tenant]**: Saiba como localizar sua ID do locatário  [nesta seção](../../integrating/using/d365-acs-configure-d365.md#get-the-tenant-id)

* **[!UICONTROL URL]**: O url terá o formato https://&lt;servername>.api.crm.dynamics.com/

### Credenciais da API Adobe

As credenciais do Adobe Campaign são geradas usando [Adobe I/O](https://www.adobe.io/). Você precisará visitar a tela [Configurar o Adobe I/O](../../integrating/using/d365-acs-configure-adobe-io.md) e seguir as instruções para poder preencher as entradas nesta seção.

A imagem a seguir explicará detalhadamente o mapeamento entre o Adobe I/O e as entradas da tela de configurações.

![](assets/d365-to-acs-ui-page-workflows-settings-adobeio.png)

* *Chave* privada: o processo para definir esses start clicando no botão &quot;Gerar um par de chaves público/privado&quot;. Isso criará um arquivo zip que precisa ser baixado. Depois de baixá-lo, descompacte o arquivo, o que resultará em dois arquivos chamados certificate_pub.crt e private.key. Certifique-se de colocar a chave privada em um local seguro e não compartilhá-la. Abra o arquivo private.key em um editor de texto. Copie o valor inteiro no editor de texto (ctrl-A em seguida, ctrl-C em um PC, ou cmd-A em seguida cmd-C em um Mac). Isto deve incluir as linhas com &quot;BEGIN PRIVATE KEY&quot; e &quot;END PRIVATE KEY&quot; na sua totalidade. Cole todo este texto de várias linhas na entrada &quot;Chave privada&quot; na tela Configurações.

* *URL*: Esse valor se ajusta ao padrão https\://mc.adobe.io/&lt;campaign-instance-name>. O cabeçalho do aplicativo de integração inclui &quot;Org&quot; e &quot;Instance&quot;. A parte &quot;campanha-instance-name&quot; do url seria simplesmente o nome encontrado neste valor de instância.

## Configurações SFTP do Adobe Campaign {#ac-smtp-settings}

Essas configurações são opcionais. É necessário defini-los se você planeja usar sua instância Adobe Campaign SFTP para produzir registros do conector. Isso será útil se você tiver problemas quando a integração estiver em execução e precisar depurar por que a saída não atende às suas expectativas.

O outro motivo para configurar o servidor SFTP seria se você planeja executar o fluxo de trabalho de aceitação/não participação e houver um fluxo de dados da Adobe Campaign para o Microsoft Dynamics 365, seja **[!UICONTROL Unidirectional (Campaign to Microsoft Dynamics 365)]** ou **[!UICONTROL Bidirectional]**.

>[!IMPORTANT]
>
>Você é responsável pelas informações que acessa e baixa das pastas SFTP. Se as informações contiverem dados pessoais, você será responsável por seguir as leis e regulamentos de privacidade aplicáveis. [Saiba mais](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-privacy).


Para definir configurações de SFTP de Campanha para a integração com o Microsoft Dynamics 365, acesse a seguinte seção:

![](assets/d365-to-acs-ui-page-workflows-settings-sftp.png)

É necessário especificar:

* **Host** SFTP: este campo conterá  &lt;campaign-instance-name>.campanha.adobe.com. O cabeçalho do aplicativo de integração inclui **Org** e **Instance**. A parte &quot;campanha-instance-name&quot; do url seria simplesmente o nome encontrado neste valor de instância.

* **Usuário** SFTP: Se você tiver o usuário SFTP, adicione-o aqui. Caso contrário, consulte [esta seção](#ac-control-panel-settings). Como parte do processo, você receberá o nome de usuário.

* **Chave** SFTP: Se você tiver uma chave SSH, adicione-a aqui. Caso contrário, consulte [esta seção](#ac-control-panel-settings).

* Os **Intervalos de IP** serão necessários para serem incluídos na configuração SFTP da Adobe Campaign. Eles precisarão ser incluir na lista de permissões para que a integração possa usar o terminal SFTP.

* O **Pretende exportar registros para o seu Adobe Campaign SFTP?** permite que você determine se a integração produzirá informações de registro para o terminal SFTP. Isso pode ser usado para ajudar na depuração se o Adobe Campaign ou o Microsoft Dynamics 365 não estiver mostrando as informações que você está esperando.

## Configuração SFTP no Adobe Campaign {#ac-control-panel-settings}

Descubra o gerenciamento SFTP com [Painel de controle do Campaign de Campanha](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=pt-BR) nestas seções:

* [Sobre o gerenciamento de SFTP](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/about-sftp-management.html?lang=en#sftp-management)

* [Gerenciamento de armazenamentos SFTP](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html?lang=en#installing-ssh-key)

* [Adicionar intervalos IP](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/ip-range-allow-listing.html?lang=en#sftp-management)

* [Gerenciar chaves](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html?lang=en#sftp-management)

* [Faça logon no servidor SFTP](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/logging-into-sftp-server.html?lang=en#sftp-management)

Quando a configuração for concluída, faça logon no servidor SFTP com a chave privada e crie o diretório &quot;d365_loads/export&quot;.

[Visite esta ](https://experienceleague.adobe.com/docs/campaign-standard-learn/control-panel/sftp-management/monitoring-server-capacity.html?lang=en#sftp-management) página para obter informações sobre o servidor Adobe Campaign Standard SFTP.
