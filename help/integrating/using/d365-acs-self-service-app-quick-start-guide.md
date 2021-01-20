---
title: 'Introdução à ferramenta de integração '
description: Introdução à ferramenta de integração
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
translation-type: tm+mt
source-git-commit: 1e05db3fecc87a026750f40acb0ff063706e3f38
workflow-type: tm+mt
source-wordcount: '1071'
ht-degree: 2%

---


# Introdução ao aplicativo de integração de autoatendimento {#gs-self-service-app}

A integração do Adobe Campaign Standard com o aplicativo de integração de autoatendimento do Microsoft Dynamics 365 oferece a capacidade de configurar fluxos de dados, controlar se eles estão ou não em execução e em qual ambiente. No entanto, você deve concluir alguns pré-requisitos antes de começar a usar o aplicativo de integração de autoatendimento.

## Conceitos e restrições {#concepts-and-restrictions}

Antes de começar com a ferramenta de integração, é necessário compreender os conceitos e as garantias associadas à integração e seguir algumas etapas iniciais para obter acesso.

Saiba mais sobre estas seções:

* [Introdução à integração com o Microsoft Dynamics 365](../../integrating/using/d365-acs-get-started.md)
* [Práticas recomendadas e limitações de integração](../../integrating/using/d365-acs-notices-and-recommendations.md)
* [Saiba mais sobre as principais etapas para implementar essa integração](../../integrating/using/d365-acs-get-started.md#request-and-implement-this-integration)
* [Usar a integração com o Microsoft Dynamics 365](../../integrating/using/d365-acs-using-the-integration.md)

## Pré-requisitos {#self-service-app-prerequisites}

É necessário configurar o Microsoft Dynamics 365 e o Adobe Campaign Standard para que o aplicativo de integração tenha acesso aos seus dados. Isso levará algum tempo para ser configurado no Dynamics 365, Adobe Campaign Standard e Adobe I/O; no entanto, uma vez configurados, você poderá controlar a integração por meio da interface do usuário do aplicativo de integração de autoatendimento.

Saiba mais sobre estas seções:

* [Configurar o Microsoft Dynamics 365 para integração com o Campaign](../../integrating/using/d365-acs-configure-d365.md)
* [Configurar o Adobe I/O](../../integrating/using/d365-acs-configure-adobe-io.md)
* [Mapear recursos personalizados da Campanha e entidades personalizadas do Microsoft Dynamics 365](../../integrating/using/d365-acs-notices-and-recommendations.md)

## Etapas principais para configurar o aplicativo de integração de autoatendimento {#self-service-app-configuration-steps}

Em seguida, você pode start com a ferramenta de integração. Siga as etapas abaixo:

1. [Obter acesso ao aplicativo de integração](../../integrating/using/d365-acs-self-service-app-control-access.md)
1. [Configure o aplicativo de integração para sua utilização](../../integrating/using/d365-acs-self-service-app-settings.md)
1. [Implementação da sincronização de dados](../../integrating/using/d365-acs-self-service-app-data-sync.md)
1. [Configurar workflows de sincronização](../../integrating/using/d365-acs-self-service-app-workflows.md)

## Link para o aplicativo de integração {#self-service-app-link}

Abra um navegador e navegue até o conector associado à sua região:

* [Pacífico Asiático](http://d365-acs-ap.ea.adobe.com/)
* [Europa, Oriente Médio ou África (EMEA)](http://d365-acs-em.ea.adobe.com/)
* [Américas](http://d365-acs-na.ea.adobe.com/)

## Confirmação de solicitação de privacidade {#self-service-app-acknowledgement}

Ao navegar pela primeira vez na interface de usuário de autoatendimento, você receberá a confirmação de privacidade. É necessário reconhecer que você entende sua função na execução de solicitações de privacidade no Campaign e no Microsoft Dynamics 365 separadamente antes de continuar.
Saiba mais sobre suas responsabilidades de privacidade e sobre como gerenciar solicitações de privacidade em [esta seção](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-privacy).

## Configurar suas credenciais {#self-service-app-credentials}

Ao navegar pela primeira vez na interface do usuário, você deverá ver uma página com um cabeçalho com a seguinte aparência:

![](assets/d365-to-acs-ui-header.png)

>[!NOTE]
>
> É normal receber alertas que mencionem que é &quot;impossível se conectar&quot; ao Adobe Campaign Standard ou ao Microsoft Dynamics 365 se as configurações do aplicativo ainda não foram definidas.

Verifique se as seleções &quot;ORG&quot; e &quot;INSTANCE&quot; são as que você pretende configurar.  Caso contrário, clique na lista suspensa e selecione a organização e a instância corretas.

>[!IMPORTANT]
>
> Se você estiver configurando o conector pela primeira vez e/ou se você for novo nesse processo, então nós **fortemente** solicitamos que você selecione a instância &quot;stage&quot; ou &quot;dev&quot;. Verifique se a configuração funciona bem antes de tentar a configuração na produção.

Se você tiver a organização e instância corretas, clique no menu &quot;hambúrguer&quot; para expor um menu suspenso. Em seguida, clique em **[!UICONTROL Settings...]** no menu suspenso para visitar a página na qual você insere suas credenciais para o Microsoft Dynamics 365 e Campaign (veja abaixo).

![](assets/d365-to-acs-ui-page-workflows-menu-pointers.png)

Na página **[!UICONTROL Settings]**, preencha as seguintes seções:

* Credenciais do Microsoft Dynamics 365
* Credenciais Adobe

Vá [aqui](../../integrating/using/d365-acs-self-service-app-settings.md) para encontrar informações mais detalhadas sobre onde encontrar as informações de cada entrada. Quando terminar, clique no botão **[!UICONTROL Save]** na parte inferior.

## Verifique a configuração inicial {#self-service-app-initial-config}

Presumindo que você concluiu os pré-requisitos acima e adicionou corretamente todas as suas credenciais, agora vamos navegar até a página **[!UICONTROL Workflows]**. Saiba mais sobre os workflows do aplicativo de integração em [esta página](../../integrating/using/d365-acs-self-service-app-workflows.md).

Na página **[!UICONTROL Workflows]**, clique no ícone de lápis associado ao fluxo de trabalho **[!UICONTROL Microsoft Dynamics 365 to Campaign]** para editar sua configuração.

![](assets/d365-to-acs-ui-page-workflows-ingress-edit-pointer.png)

Na página **[!UICONTROL Microsoft Dynamics 365 to Campaign]**, você pode acessar a lista dos mapeamentos de tabela configurados.  O padrão será um mapeamento de contato/perfil pronto para uso. Todas as outras entidades personalizadas precisarão ser configuradas separadamente.

![](assets/d365-to-acs-ui-page-ingress-top-pointers.png)

Na página **[!UICONTROL Edit Table Mapping]**, verifique a seção **[!UICONTROL Mappings]** para garantir que os campos do Microsoft Dynamics 365 estejam sendo mapeados para o campo correto na Campanha. Se precisar adicionar outros mapeamentos, faça isso agora, bem como quaisquer substituições ou filtros. [Saiba mais](../../integrating/using/d365-acs-self-service-app-data-sync.md).

Se desejar adicionar novos mapeamentos, consulte [esta seção](../../integrating/using/d365-acs-self-service-app-data-sync.md#add-a-new-mapping) para obter mais informações.

Quando a configuração estiver correta, clique no botão **[!UICONTROL Play]** ao lado do fluxo de trabalho **[!UICONTROL Microsoft Dynamics 365 to Campaign]** para start da integração e do fluxo de dados.

>[!IMPORTANT]
>
>Recomendamos que você execute isso primeiro em seus ambientes de Estágio ou de Desenvolvimento antes de executar na Produção. **** Verifique se a instância stage/dev está selecionada no cabeçalho.


![](assets/d365-to-acs-ui-page-workflows-ingress-play-pointer.png)

Depois de executado, você deve ser capaz de testar adicionando ou modificando entradas no Microsoft Dynamics 365 e observando essas alterações no Adobe Campaign em alguns minutos. Se, a qualquer momento, você precisar interromper esse processo, simplesmente pressione o mesmo botão para pará-lo. [Saiba mais](../../integrating/using/d365-acs-self-service-app-workflows.md#workflow-status)


## Área de trabalho do aplicativo de integração {#self-service-app-workspace}

### Cabeçalho do aplicativo {#app-header}

O cabeçalho no aplicativo de autoatendimento permite definir qual organização e instância você está visualizando e/ou configurando no momento.

Selecione **ORG** e **INSTANCE** que pretende visualização/editar. Esses campos aparecem somente leitura, no entanto, tornam-se editáveis quando você coloca o cursor do mouse sobre eles.

Um menu suspenso será exibido quando você clicar no botão com as três linhas horizontais ![](assets/d365-to-acs-icon-hamburger.png) no lado direito do cabeçalho.

As entradas no menu suspenso são

* **Configurações**: Selecionar essa opção enviará você para uma tela que permite especificar credenciais de API para o Microsoft Dynamics 365 e Adobe Campaign, bem como outras configurações gerais para o aplicativo.

* **Documentação**: Esta opção é um link para a Documentação da Adobe Campaign específico para essa integração

* **Atendimento** ao cliente: Este é um link para a documentação do Experience Cloud relacionada à abertura de um ticket do Atendimento ao cliente

* **Sair**: Isso permitirá que você saia do aplicativo e faça logon novamente como outro usuário.

* **Sobre**: Isso exibe uma caixa de diálogo que contém informações sobre o aplicativo, incluindo informações de direitos autorais.

### Trilhas {#app-breadcrumbs}

As navegações estruturais aparecem na parte superior de algumas telas à medida que você navega no aplicativo.

**Exemplo:**

Abaixo está um exemplo da tela **[!UICONTROL Edit Table Mapping]** que mostra as navegações estruturais e o título da página. Nesse caso, você pode clicar no texto **[!UICONTROL Workflows]** ou **[!UICONTROL Microsoft Dynamics 365 to Campaign]** para ir para uma das telas anteriores. **[!UICONTROL Edit Table Mapping]** neste caso, as navegações estruturais não podem ser clicadas porque são a tela atual.

![](assets/d365-to-acs-breadcrumbs-ingress.png)

### Botões comuns {#app-buttons}

Os ícones a seguir são usados em várias páginas no aplicativo de autoatendimento.

![](assets/d365-to-acs-icon-add.png) - Adicione um novo item a uma lista.

![](assets/d365-to-acs-icon-edit.png) - Editar algo que já existe

![](assets/d365-to-acs-icon-delete.png) - Excluir um item de uma lista de itens
