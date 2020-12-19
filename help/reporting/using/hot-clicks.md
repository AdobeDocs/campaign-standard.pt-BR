---
solution: Campaign Standard
product: campaign
title: Hot clicks
description: Com o recurso Hot click out out-of-the-box, saiba onde o cliente clicou no seu delivery.
audience: reporting
content-type: reference
topic-tags: list-of-reports
context-tags: deliveryHotClicksReport,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '477'
ht-degree: 0%

---


# Hot clicks{#hot-clicks}

Este relatório pode ser acessado do botão **[!UICONTROL Reports]** em cada delivery ou mensagen transacional.

![](assets/delivery_reports_hot-clicks_4.png)

Ele apresenta o conteúdo da mensagem (HTML e/ou texto) com a porcentagem de cliques em cada link.

![](assets/delivery_reports_10.png)

Se você tiver criado conteúdo dinâmico para seu delivery, poderá visualização as porcentagens para cada condição definida. Para obter mais informações sobre como inserir conteúdo condicional em um delivery, consulte [Definição de conteúdo dinâmico](../../designing/using/personalization.md#defining-dynamic-content-in-an-email).

Por exemplo, imagine que você criou um delivery com as seguintes condições:

* O link na imagem principal é diferente se o recipient for um homem ou uma mulher.
* Você também adicionou um link a uma oferta especial que só é visível para recipient com mais de 25 anos.

Depois que sua mensagem for enviada, selecione **[!UICONTROL Reports]** > **[!UICONTROL Hot clicks]** no painel do delivery.

Por padrão, nenhum perfil é selecionado. Somente os cliques para recipient cujo sexo é desconhecido e para recipient com menos de 25 anos ou idade desconhecida são exibidos.

![](assets/delivery_reports_hot-clicks_1.png)

Para exibir cliques para mulheres, clique no botão **[!UICONTROL Change profile]** e selecione um perfil de teste feminino. Para exibir cliques para homens, continue da mesma forma e selecione um perfil de teste masculino.

![](assets/delivery_reports_hot-clicks_2.png)

Para exibir cliques para recipient com mais de 25 anos, clique no botão **[!UICONTROL Change profile]** e selecione um perfil de teste cuja data de nascimento corresponda a essa condição.

Para obter mais informações sobre perfis de teste, consulte [Sobre perfis de teste](../../audiences/using/managing-test-profiles.md).

>[!NOTE]
>
>O número de cliques em um link específico é uma porcentagem do total de cliques para todo o conteúdo condicional em um delivery. Portanto, se você definiu o conteúdo dinâmico, o total das porcentagens exibidas para um perfil de teste específico pode não ser igual a 100.

Da mesma forma, para delivery e mensagens transacionais recorrentes, você pode selecionar o perfil de teste correspondente ao conteúdo dinâmico que deseja exibir, mas também pode visualização as porcentagens de cliques de acordo com o delivery de execução selecionado.

Um delivery de execução é uma mensagem técnica não acionável e não funcional criada nos seguintes casos:

* Cada vez que um delivery recorrente é executado ou atualizado.

   Por exemplo, se o fluxo de trabalho que gerencia esse delivery for executado uma vez por mês, haverá um delivery de execução por mês. Além disso, sempre que o conteúdo do delivery é atualizado, um delivery de execução adicional é criado.

   Para obter mais informações sobre delivery de email recorrentes, consulte [delivery de email](../../automating/using/email-delivery.md).

* Por padrão, uma vez por mês para mensagens transacionais e sempre que um mensagen transacional é editado e publicado novamente.

   Para obter mais informações sobre mensagens transacionais, consulte [Introdução às mensagens transacionais](../../channels/using/getting-started-with-transactional-msg.md).

>[!NOTE]
>
>Como as IDs dos URLs rastreados são diferentes para cada execução, os dados de cliques em funcionamento não podem ser agregados para todos os delivery de execução de uma determinada mensagem. Ele só pode ser exibido para um delivery de execução por vez.

Depois que sua mensagem for enviada, selecione **[!UICONTROL Reports]** > **[!UICONTROL Hot clicks]** no painel do delivery.

Por padrão, o último delivery de execução é selecionado. Clique no botão **[!UICONTROL Change execution delivery]** para selecionar outro.

![](assets/delivery_reports_hot-clicks_3.png)

Somente as porcentagens de cliques para a execução do delivery selecionado são exibidas.
