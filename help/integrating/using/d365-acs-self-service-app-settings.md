---
title: Configurar o aplicativo de integração Campaign-Dynamics
description: Saiba como configurar o aplicativo de integração Campaign-Dynamics
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
exl-id: 184bc656-2107-4380-9b35-148cb4380547
source-git-commit: c701043cbba22711de1ea7ddc5266e193d771e14
workflow-type: tm+mt
source-wordcount: '629'
ht-degree: 2%

---

# Conectar sistemas com o aplicativo de integração

## Adicionar credenciais ao aplicativo de integração

A tela **[!UICONTROL Settings]** permite especificar credenciais de API do Microsoft Dynamics 365 e Adobe. Você também pode definir configurações relacionadas à instância do SFTP da Adobe Campaign.

### Credenciais do Microsoft Dynamics 365

As Credenciais do Microsoft Dynamics 365 dão ao aplicativo de integração permissão para extrair seus dados do Microsoft Dynamics 365.  Primeiro, siga as etapas na tela [Configurar o Microsoft Dynamics 365 para integração com o Campaign](../../integrating/using/d365-acs-configure-d365.md) para gerar os valores que serão colados nessa tela. As entradas descritas abaixo referenciarão esta tela.

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-d365.png)

* **[!UICONTROL Client ID]**: Saiba como referenciar sua ID de Cliente em [esta seção](../../integrating/using/d365-acs-configure-d365.md#register-a-new-app)

* **[!UICONTROL Client Secret]**: Saiba como gerar seu Segredo do Cliente em [esta seção](../../integrating/using/d365-acs-configure-d365.md#generate-a-client-secret)

* **[!UICONTROL Tenant]**: Saiba como encontrar sua ID de Locatário em [esta seção](../../integrating/using/d365-acs-configure-d365.md#get-the-tenant-id)

* **[!UICONTROL URL]**: a url terá o formato `https://&lt;servername&gt;.api.crm.dynamics.com/`

### Credenciais da API Adobe

As credenciais do Adobe Campaign são geradas usando [Adobe I/O](https://www.adobe.io/). Você precisará visitar a tela [Configurar Adobe I/O](../../integrating/using/d365-acs-configure-adobe-io.md) e seguir as instruções lá antes de poder preencher as entradas nesta seção.

* Selecione o Tipo de autenticação como Oauth já que a autenticação baseada em JWT está obsoleta.
* A imagem a seguir explicará em detalhes o mapeamento entre o Adobe I/O e as entradas da tela de configurações.

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-adobeio.png)

* *URL*: este valor se ajustará ao padrão https\://mc.adobe.io/&lt;campaign-instance-name>. O cabeçalho do aplicativo de integração inclui &quot;Org&quot; e &quot;Instance&quot;. A parte &quot;campaign-instance-name&quot; do url seria simplesmente o nome encontrado nesse valor de instância.

## Configurações SFTP do Adobe Campaign {#ac-smtp-settings}

Essas configurações são opcionais. É necessário defini-los se você planeja usar sua instância do Adobe Campaign SFTP para logs de saída do conector. Isso será útil se tiver problemas quando a integração estiver em execução e precisar depurar por que a saída não atende às suas expectativas.

O outro motivo para configurar o servidor SFTP seria se você planejasse executar o fluxo de trabalho de aceitação/recusa e houver um fluxo de dados do Adobe Campaign para o Microsoft Dynamics 365, **[!UICONTROL Unidirectional (Campaign to Microsoft Dynamics 365)]** ou **[!UICONTROL Bidirectional]**.

>[!IMPORTANT]
>
>Você é responsável pelas informações que acessar e baixar das pastas SFTP. Se as informações contiverem dados pessoais, você será responsável por cumprir as leis e regulamentos de privacidade aplicáveis. [Saiba mais](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-privacy).
>

Para definir as configurações de SFTP do Campaign para a integração com o Microsoft Dynamics 365, acesse a seguinte seção:

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-sftp.png)

É necessário especificar:

* **Host SFTP**: este campo conterá &lt;campaign-instance-name>.campaign.adobe.com. O cabeçalho do aplicativo de integração inclui a **Org** e a **Instance**. A parte &quot;campaign-instance-name&quot; do url seria simplesmente o nome encontrado nesse valor de instância.

* **Usuário SFTP**: se você tiver o usuário SFTP, adicione-o aqui. Senão, consulte [esta seção](#ac-control-panel-settings). Como parte do processo, você receberá o nome de usuário.

* **Chave SFTP**: se você tiver uma Chave SSH, adicione-a aqui. Senão, consulte [esta seção](#ac-control-panel-settings).

* Será necessário incluir os **Intervalos IP** na configuração SFTP da Adobe Campaign. Incluir na lista de permissões Eles precisarão ser resolvidos para que a integração use o terminal SFTP.

* O **Deseja exportar os logs para o SFTP da Adobe Campaign?** permite determinar se a integração exibirá informações de log para o ponto de extremidade SFTP. Isso pode ser usado para ajudar na depuração se o Adobe Campaign ou o Microsoft Dynamics 365 não estiver mostrando as informações que você espera.

## Configuração do SFTP no Adobe Campaign {#ac-control-panel-settings}

Descubra o gerenciamento SFTP com o [Painel de Controle do Campaign](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=pt-BR) nestas seções:

* [Sobre o gerenciamento de SFTP](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/about-sftp-management.html?lang=pt-BR#sftp-management)

* [Gerenciamento de armazenamentos SFTP](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html#installing-ssh-key)

* [Adicionar intervalos IP](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/ip-range-allow-listing.html#sftp-management)

* [Gerenciar chaves](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html#sftp-management)

* [Fazer logon no servidor SFTP](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/logging-into-sftp-server.html#sftp-management)

Depois que a configuração for concluída, faça logon no servidor SFTP com a chave privada e crie o diretório &quot;d365_loads/exports&quot;.

[Visite esta página](https://experienceleague.adobe.com/docs/campaign-standard-learn/control-panel/sftp-management/monitoring-server-capacity.html?lang=pt-BR#sftp-management) para obter informações sobre o servidor SFTP da Adobe Campaign Standard.
