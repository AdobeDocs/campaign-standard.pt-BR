---
title: Introdução à administração do Campaign Standard
description: Saiba mais sobre as permissões e o gerenciamento de usuários, as diretrizes de monitoramento, as configurações específicas por canal e as diretrizes de configuração do aplicativo
audience: administration
feature: Access Management
role: Admin
level: Experienced
exl-id: 9676b5e8-4c34-4848-8616-235e0bac5d6b
source-git-commit: bfba6b156d020e8d2656239e713d2d24625bda54
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Introdução à administração do Campaign Standard {#about-administrating-adobe-campaign}

<table>
<tr><td><img src="assets/do-not-localize/icon_menu.svg" width="60px"><p><a href="#administration-menu">Menu Administração</a></p></td>
<td><img src="assets/do-not-localize/icon_users.svg" width="60px"><p><a href="#users-security">Usuários e segurança</a></p></td>
<td><img src="assets/do-not-localize/icon_channels.svg" width="60px"><p><a href="#channels-configuration">Configuração de canais</a></p></td>
<td><img src="assets/do-not-localize/icon_settings.svg" width="60px"><p><a href="#application-settings">Configurações do aplicativo</a></p></td></tr>
</table>

Como solução baseada em nuvem, a Adobe Campaign oferece aos administradores diferentes maneiras de configurar o aplicativo. Embora a configuração da infraestrutura seja executada pelo Adobe, os administradores funcionais podem realizar várias operações de configuração detalhadas abaixo.

>[!NOTE]
>
>Em caso de dúvidas ou solicitações sobre questões de implementação e configuração, entre em contato com o executivo da sua conta Adobe.

Observe que os usuários administradores também podem aproveitar o Painel de controle do Campaign para gerenciar configurações e rastrear o uso de cada uma de suas instâncias. Para obter mais informações, consulte a [documentação dedicada](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=pt-BR).

## Menu Administração {#administration-menu}

<img src="assets/do-not-localize/icon_menu.svg" width="60px">

As diferentes operações de administrador do Adobe Campaign são realizadas por meio do **[!UICONTROL Administration]** acessível ao clicar no logotipo do Adobe Campaign no canto superior esquerdo. Essa parte da interface só pode ser acessada por administradores funcionais da plataforma.

Os diferentes menus disponíveis são:

* [Usuários e segurança](../../administration/using/about-access-management.md): Esse menu permite gerenciar o acesso à plataforma (usuários, funções, grupos de segurança, unidades).
* [Canais](../../administration/using/about-channel-configuration.md): Esse menu reúne os parâmetros técnicos vinculados aos diferentes canais da plataforma (Email, dispositivos móveis), bem como a tipologia e o gerenciamento de quarentena.
* [Configurações do aplicativo](../../administration/using/external-accounts.md): Esse menu permite configurar diferentes elementos do aplicativo (contas externas, opções, fluxos de trabalho técnicos).
* [Desenvolvimento](../../developing/using/data-model-concepts.md): Esse menu permite gerenciar os recursos personalizados e acessar as ferramentas de diagnóstico.
* [Configurações de instância](../../administration/using/branding.md): Este menu permite definir suas diferentes marcas e definir suas configurações (logotipo, gerenciamento do rastreamento, domínio de URL para acessar landing pages etc.).
* [Implantação](../../automating/using/managing-packages.md): Esse menu agrupa as opções de importação e exportação de pacotes.
* [Métricas do cliente](../../audiences/using/active-profiles.md): O Adobe Campaign fornece um relatório que exibe o número de perfis ativos. Este relatório é apenas informativo, não tem impacto direto na cobrança.
* [Ferramentas de privacidade](../../start/using/privacy-management.md): Esse menu permite criar solicitações de acesso e exclusão do GDPR e acompanhar sua evolução.

## Usuários e segurança {#users-security}

<img src="assets/do-not-localize/icon_users.svg"  width="60px">

Convidar usuários para acessar o aplicativo e gerenciar **grupos de segurança**, que são conjuntos de usuários que compartilham as mesmas funções e direitos em sua organização. Por padrão, a Adobe Campaign oferece um conjunto de **funções** O que permite definir autorizações unitárias atribuídas a usuários e grupos de usuários. Combinado com **unidades organizacionais**, as funções fornecem aos usuários uma visualização filtrada da interface e definem o acesso aos diferentes recursos.

O Campaign standard também permite monitorar informações relacionadas à segurança. Você pode recuperar informações sobre exportações de dados realizadas pelos usuários por meio do **[!UICONTROL Export audits]** e aproveite a **[!UICONTROL Licenses]** para monitorar todas as licenças do Campaign instaladas em sua organização, bem como informações diferentes, como o número da compilação, a versão da versão e os termos do contrato.

Leia mais:

* [Gerenciamento de usuários](../../administration/using/users-management.md)
* [Unidades organizacionais](../../administration/using/organizational-units.md)
* [Lista de funções](../../administration/using/list-of-roles.md)
* [Gerenciamento de grupos e usuários](../../administration/using/managing-groups-and-users.md)
* [Auditoria de logs de exportação](../../administration/using/auditing-export-logs.md)
* [Licenças](../../administration/using/licenses.md)

## Configuração de canais {#channels-configuration}

<img src="assets/do-not-localize/icon_channels.svg" width="60px">

Todos os canais de comunicação no Adobe Campaign devem ser configurados corretamente para enviar mensagens de maneira eficaz. **[!UICONTROL Channel]**  permite gerenciar os parâmetros técnicos vinculados aos diferentes canais.

Configurar vários **email** parâmetros: regras de processamento para saltos, quarentenas, propriedades de email e parâmetros de roteamento, regras de tipos. Definir configurações e propriedades de roteamento para a **SMS** , bem como codificação e formatos de SMS.

Configurar **aplicativos móveis** para poder enviar mensagens no aplicativo e notificações por push usando SDKs do Adobe Experience Platform.

Leia mais:

* [Sobre a configuração de canal](../../administration/using/about-channel-configuration.md)
* [Configuração do canal de email](../../administration/using/configuring-email-channel.md)
* [Configuração do canal SMS](../../administration/using/configuring-sms-channel.md)
* [Configurar um aplicativo para dispositivos móveis](../../administration/using/configuring-a-mobile-application.md)

## Configurações do aplicativo {#application-settings}

<img src="assets/do-not-localize/icon_settings.svg" width="60px">

O Campaign Standard vem com elementos de aplicativo diferentes que podem ser configurados para atender às suas necessidades.

Configurar **contas externas**, que são usadas para conectar o Adobe Campaign a servidores externos. Acesse os mapeamentos do Campaign Standard target e monitore sua plataforma usando **workflows técnicos**.

Definir um ou vários **marcas** para sua organização e configure o envio de **notificações em tempo real** no âmbito do pedido, no caso de atividades importantes do sistema.

Leia mais:

* [Sobre as configurações do Campaign Standard](../../administration/using/about-campaign-standard-settings.md)
* [Contas externas](../../administration/using/external-accounts.md)
* [Mapeamentos do Target no Campaign](../../administration/using/target-mappings-in-campaign.md)
* [Workflows técnicos](../../administration/using/technical-workflows.md)
* [Marca](../../administration/using/branding.md)
* [Envio de notificações internas](../../administration/using/sending-internal-notifications.md)
