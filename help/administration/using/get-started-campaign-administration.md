---
title: Introdução à administração do Campaign Standard
description: Descubra os usuários e o gerenciamento de permissões, as diretrizes de monitoramento, as configurações específicas do canal e as diretrizes de configuração do aplicativo.
page-status-flag: never-activated
uuid: 64c34729-5c98-4db0-9131-af6dd0e78fb4
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: about-administrating-adobe-campaign
discoiquuid: 5587530a-2308-4be1-9f56-19eeb7a924d5
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '650'
ht-degree: 14%

---


# Introdução à administração do Campaign Standard {#about-administrating-adobe-campaign}

<table>
<tr><td><img src="assets/do-not-localize/icon_menu.svg" width="60px"><p><a href="#administration-menu">Menu Administração</a></p></td>
<td><img src="assets/do-not-localize/icon_users.svg" width="60px"><p><a href="#users-security">Usuários e segurança</a></p></td>
<td><img src="assets/do-not-localize/icon_channels.svg" width="60px"><p><a href="#channels-configuration">Configuração de canais</a></p></td>
<td><img src="assets/do-not-localize/icon_settings.svg" width="60px"><p><a href="#application-settings">Configurações do aplicativo</a></p></td></tr>
</table>

Como uma solução baseada em nuvem, os administradores do Adobe Campaign oferta têm diferentes maneiras de configurar o aplicativo. Embora a configuração da infraestrutura seja executada pelo Adobe, os administradores funcionais podem executar várias operações de configuração detalhadas abaixo.

>[!NOTE]
>
>Em caso de dúvidas ou solicitações sobre questões de implementação e configuração, entre em contato com o executivo de sua conta Adobe.

## Menu Administração {#administration-menu}

<img src="assets/do-not-localize/icon_menu.svg" width="60px">

As diferentes operações de administração do Adobe Campaign são executadas por meio do **[!UICONTROL Administration]** menu acessível ao clicar no logotipo do Adobe Campaign no canto superior esquerdo. Essa parte da interface só pode ser acessada por administradores funcionais da plataforma.

Os diferentes menus disponíveis são:

* [Usuários e segurança](../../administration/using/about-access-management.md): Esse menu permite gerenciar o acesso à plataforma (usuários, funções, grupos de segurança, unidades).
* [Canais](../../administration/using/about-channel-configuration.md): Esse menu reúne os parâmetros técnicos vinculados aos diferentes canais da plataforma (email, dispositivos móveis), bem como o gerenciamento de tipologia e quarentenas.
* [Configurações](../../administration/using/external-accounts.md)do aplicativo: Esse menu permite que você configure diferentes elementos do aplicativo (contas externas, opções, workflows técnicos).
* [Desenvolvimento](../../developing/using/data-model-concepts.md): Esse menu permite que você gerencie seus recursos personalizados e acesse as ferramentas de diagnóstico.
* [Configurações](../../administration/using/branding.md)de instância: Este menu é onde você define suas diferentes marcas e define suas configurações (logotipo, gerenciamento de rastreamento, domínio de URL para acessar o landing page etc.).
* [Implantação](../../automating/using/managing-packages.md): Esse menu agrupa as opções de importação e exportação do pacote.
* [Métricas](../../audiences/using/active-profiles.md)do cliente: A Adobe Campaign fornece um relatório que exibe o número de perfis ativos. Este relatório é apenas informativo, não tem impacto direto na cobrança.
* [Ferramentas](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GDPR.html)de privacidade: Este menu permite que você crie acesso ao RGPD e exclua solicitações e rastreie sua evolução.

## Usuários e segurança {#users-security}

<img src="assets/do-not-localize/icon_users.svg"  width="60px">

Convide usuários para acessar o aplicativo e gerenciar grupos **de** segurança, que são conjuntos de usuários que compartilham as mesmas funções e direitos em sua organização. By default, Adobe Campaign offers a set of **roles** which allows you to define unitary authorizations assigned to users and user groups. Combined with **organizational units**, roles give users a filtered view of the interface and define their access to the different features.

O padrão de campanha também permite monitorar informações relacionadas à segurança. Você pode recuperar informações relacionadas às exportações de dados realizadas pelos usuários por meio da **[!UICONTROL Export audits]** tela e aproveitar a **[!UICONTROL Licenses]** tela para monitorar todas as licenças de Campanha instaladas em sua organização, bem como informações diferentes, como o número da compilação, a versão da versão e os termos do contrato.

Leia mais:

* [Gerenciamento de usuários](../../administration/using/users-management.md)
* [Unidades organizacionais](../../administration/using/organizational-units.md)
* [Lista de funções](../../administration/using/list-of-roles.md)
* [Gerenciamento de grupos e usuários](../../administration/using/managing-groups-and-users.md)
* [Auditoria de logs de exportação](../../administration/using/auditing-export-logs.md)
* [Licenças](../../administration/using/licenses.md)

## Configuração de canais {#channels-configuration}

<img src="assets/do-not-localize/icon_channels.svg" width="60px">

Todos os canais de comunicação no Adobe Campaign devem estar configurados corretamente para poderem enviar mensagens com eficácia. O menu permite que você gerencie os parâmetros técnicos vinculados aos diferentes canais. **[!UICONTROL Channel]**

Configure vários parâmetros de **email** : regras de processamento para rejeição, quarentenas, propriedades de e-mail e parâmetros de roteamento, regras de tipos. Defina as configurações e propriedades do roteamento **SMS** , bem como a codificação e os formatos SMS.

Configure aplicativos **** móveis para que possam enviar mensagens no aplicativo e notificações por push usando SDKs do Adobe Experience Platform, e configure mensagens **transacionais** criando e configurando eventos.

Leia mais:

* [Sobre a configuração de canal](../../administration/using/about-channel-configuration.md)
* [Configuração do canal de email](../../administration/using/configuring-email-channel.md)
* [Configuração do canal SMS](../../administration/using/configuring-sms-channel.md)
* [Configurar um aplicativo móvel](../../administration/using/configuring-a-mobile-application.md)
* [Configuração de mensagens transacionais](../../administration/using/configuring-transactional-messaging.md)

## Configurações do aplicativo {#application-settings}

<img src="assets/do-not-localize/icon_settings.svg" width="60px">

O Campaign Standard vem com diferentes elementos de aplicativo que podem ser configurados para atender às suas necessidades.

Configure o **conta externa**, que é usado para conectar o Adobe Campaign a servidores externos. Acesse target mapping Campaign Standard e monitore sua plataforma usando **workflows técnicos**.

Defina uma ou várias **marcas** para sua organização e configure o envio de notificações **em tempo** real dentro do aplicativo, no caso de atividades importantes do sistema.

Leia mais:

* [Sobre as configurações do Campaign Standard](../../administration/using/about-campaign-standard-settings.md)
* [Contas externas](../../administration/using/external-accounts.md)
* [Mapeamentos do Target no Campaign](../../administration/using/target-mappings-in-campaign.md)
* [Fluxos de trabalho técnicos](../../administration/using/technical-workflows.md)
* [Identidade visual](../../administration/using/branding.md)
* [Enviar notificações internas](../../administration/using/sending-internal-notifications.md)

## Recursos adicionais

* [Gerenciamento de direitos de acesso do usuário (vídeo)](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/administrating/managing-user-access-rights.html)
* [Documentação do Painel de controle do Campaign](https://docs.adobe.com/content/help/pt-BR/control-panel/using/control-panel-home.translate.html)
