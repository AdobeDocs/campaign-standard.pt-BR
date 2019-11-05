---
title: Sobre as páginas de aterrissagem
description: Descubra as páginas iniciais da Campanha e seu ciclo de vida.
page-status-flag: nunca ativado
uuid: b316bf47-7d98-46fa-ab4f-67ff50de8095
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: canais
content-type: referência
topic-tags: páginas de aterrissagem
discoiquuid: ca8d1698-6e8a-4f5a-b017-74a152e14286
context-tags: landingPage,assistente;landingPage,overview;landingPage,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Sobre as páginas de aterrissagem{#about-landing-pages}

A campanha vem com páginas de aterrissagem que são formulários da Web que podem ser usados para capturar informações em seus públicos-alvo, oferecer assinaturas para um serviço, exibir dados e aumentar seu banco de dados. As páginas iniciais também podem ser usadas para adquirir ou atualizar perfis existentes.

Para obter mais informações sobre as etapas necessárias para configurar uma página de aterrissagem, consulte [esta seção](../../channels/using/main-steps-to-set-up-a-landing-page.md)

**Tópicos relacionados:**

* [Vídeo Criar um tutorial de página de aterrissagem](https://helpx.adobe.com/campaign/kt/acs/using/acs-create-edit-landing-page-feature-video-use.html)
* [Usar uma página de aterrissagem para assinar um serviço](../../audiences/using/creating-a-service.md)

## Ciclo de vida das páginas iniciais {#landing-pages-life-cycle}

O ciclo de vida completo de uma página de aterrissagem é o seguinte:

1. Criação: crie e defina o conteúdo da página de aterrissagem.
1. Teste: simule a execução da página inicial em um perfil de teste.
1. Publicação: publique a página de aterrissagem para colocá-la ao vivo.
1. Expiração ou publicação: cancele a publicação manualmente ou aguarde até que a página de aterrissagem expire e então ela não estará mais disponível.

![](assets/lp_livecycle.png)

Depois de criada e publicada, você pode tornar a página de aterrissagem acessível por meio de um site ou [inserindo um link direto para a página de aterrissagem em um email](../../designing/using/links.md#inserting-a-link).

## Limitações da página inicial{#landing-page-limitations}

A seção abaixo lista as limitações que devem ser observadas antes de iniciar a configuração de páginas iniciais.

**Gravação e atualização de dados**

* As páginas de aterrissagem são limitadas apenas a **[!UICONTROL Profile]** e **[!UICONTROL Subscription]** recursos. O registro pode ser salvo e atualizado de uma assinatura **[!UICONTROL Profile]** ou cancelamento de assinatura para uma **[!UICONTROL Service]**.
Para saber mais sobre a configuração de recursos, consulte [Configuração da estrutura](../../developing/using/configuring-the-resource-s-data-structure.md)de dados do recurso.

>[!CAUTION]
>
>Uma página inicial não pode exibir ou atualizar dados de nenhum outro recurso além **[!UICONTROL Profile]** e **[!UICONTROL Subscription]**.

**Pré-carregamento**

* A página de aterrissagem não pode exibir uma lista de registros automaticamente, não pode listar os serviços aos quais os perfis já se inscreveram. For more information on services, refer to this [page](../../audiences/using/creating-a-service.md).

* A página de aterrissagem com um formulário pré-preenchido (os dados são pré-carregados com a página) só pode ser acessada de um email do Adobe Campaign. Não é possível acessar esse formulário a partir de uma página do site.

**Reconciliação**

* O comportamento de reconciliação é o seguinte: assim que uma correspondência é encontrada, o processo de reconciliação para. Isso significa que a reconciliação só pode ser feita em um registro de perfil e não em vários registros quando houver duplicatas.

Por exemplo, você deseja enviar a seguinte página inicial de aquisição para seus perfis para atualizar seu banco de dados do Campaign com os números de celular dos seus perfis.

![](assets/landing_page_limitation_1.png)

Se um de seus perfis preencher sua página inicial com novas informações, mas já tiver um perfil duplicado, o perfil correspondente com a data de criação mais antiga será atualizado, pois os perfis são priorizados dependendo apenas da data de criação.

Aqui, somente o primeiro perfil foi atualizado, pois era a entrada mais antiga.

![](assets/landing_page_limitation_2.png)

**Teste de páginas de aterrissagem**

* As páginas iniciais funcionam somente em perfis e não em perfis de teste, o que significa que as páginas iniciais não podem ser testadas como parte de uma prova de email.
