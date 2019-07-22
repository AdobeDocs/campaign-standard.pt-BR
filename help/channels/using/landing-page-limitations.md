---
title: Limitações da página de aterrissagem
seo-title: Limitações da página de aterrissagem
description: Limitações da página de aterrissagem
seo-description: Página de aterrissagem do Discover Campaign e seu ciclo de vida.
page-status-flag: nunca ativado
uuid: b 316 bf 47-7 d 98-46 fa-ab 4 f -67 ff 50 de 8095
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canais
content-type: reference
topic-tags: páginas de aterrissagem
discoiquuid: ca 8 d 1698-6 e 8 a -4 f 5 a-b 017-74 a 152 e 14286
context-tags: Landingpage, assistente; Landingpage, overview; Landingpage, main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5dbb89eca363f252d0c69126878d4f79320e0f19

---


# Landing page limitations{#landing-page-limitations}

**Gravação e atualização de dados**

* Landing pages are limited to **[!UICONTROL Profile]** and **[!UICONTROL Subscription]** resources only. Record can be saved and updated from **[!UICONTROL Profile]** and a subscription/unsubscription to a **[!UICONTROL Service]**.
To learn more on resources configuration, see [Configuring the resource's data structure](../../developing/using/configuring-the-resource-s-data-structure.md).

>[!CAUTION]
>
>A landing page cannot display or update data from any other resource than **[!UICONTROL Profile]** and **[!UICONTROL Subscription]**.

**Pré-carregamento**

* A página de aterrissagem não pode exibir uma lista de registros automaticamente, ele não pode listar os serviços aos quais os perfis já se inscreveram. For more information on services, refer to this [page](../../audiences/using/creating-a-service.md).

* A página de aterrissagem com um formulário pré-preenchido (dados pré-carregados com a página) pode ser acessada somente a partir de um email do Adobe Campaign. Não é possível acessar esse formulário a partir de uma página de site.

**Reconciliação**

* O comportamento de reconciliação é o seguinte: assim que uma correspondência for encontrada, o processo de reconciliação será interrompido. Isso significa que a reconciliação só pode ser feita em um registro de perfil e não em vários registros quando há duplicatas.

Por exemplo, você deseja enviar a seguinte página de aterrissagem de aquisição para seus perfis para atualizar o banco de dados da campanha com os números móveis dos perfis.

![](assets/landing_page_limitation_1.png)

Se um dos seus perfis de perfil for preenchido na página de aterrissagem com novas informações, mas já tiver um perfil duplicado, o perfil correspondente com a data de criação mais antiga será atualizado, pois os perfis são priorizados dependendo da data de criação apenas.

Aqui, somente o primeiro perfil foi atualizado, já que era a entrada mais antiga.

![](assets/landing_page_limitation_2.png)

**Teste da página de aterrissagem**

* As páginas de aterrissagem funcionam somente em perfis e não em perfis, o que significa que as páginas iniciais não podem ser testadas como parte de uma prova de email.
