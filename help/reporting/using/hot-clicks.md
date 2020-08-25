---
title: Hot clicks
description: Com o recurso Hot click out out-of-the-box, saiba onde o cliente clicou no seu delivery.
page-status-flag: never-activated
uuid: 7ed49dd3-d7ee-466a-9a7b-d2aa16961667
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: reporting
content-type: reference
topic-tags: list-of-reports
discoiquuid: ecbc1ade-63d9-4ac2-9828-380a1aa95094
context-tags: deliveryHotClicksReport,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1efcd646f4af86175b3b09b53185c792cb4cf7dd
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 0%

---


# Hot clicks{#hot-clicks}

Esse relatório pode ser acessado a partir do **[!UICONTROL Reports]** botão em cada delivery ou mensagen transacional.

![](assets/delivery_reports_hot-clicks_4.png)

Ele apresenta o conteúdo da mensagem (HTML e/ou texto) com a porcentagem de cliques em cada link.

![](assets/delivery_reports_10.png)

Se você tiver criado conteúdo dinâmico para seu delivery, poderá visualização as porcentagens para cada condição definida. Para obter mais informações sobre como inserir conteúdo condicional em um delivery, consulte [Definição de conteúdo](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)dinâmico.

Por exemplo, imagine que você criou um delivery com as seguintes condições:

* O link na imagem principal é diferente se o recipient for um homem ou uma mulher.
* Você também adicionou um link a uma oferta especial que só é visível para recipient com mais de 25 anos.

Depois que sua mensagem for enviada, selecione **[!UICONTROL Reports]** > **[!UICONTROL Hot clicks]** do painel do delivery.

Por padrão, nenhum perfil é selecionado. Somente os cliques para recipient cujo sexo é desconhecido e para recipient com menos de 25 anos ou idade desconhecida são exibidos.

![](assets/delivery_reports_hot-clicks_1.png)

Para exibir cliques para mulheres, clique no **[!UICONTROL Change profile]** botão e selecione um perfil de teste feminino. Para exibir cliques para homens, continue da mesma forma e selecione um perfil de teste masculino.

![](assets/delivery_reports_hot-clicks_2.png)

Para exibir cliques para recipient com mais de 25 anos, clique no **[!UICONTROL Change profile]** botão e selecione um perfil de teste cuja data de nascimento corresponda a essa condição.

Para obter mais informações sobre perfis de teste, consulte [Sobre perfis](../../audiences/using/managing-test-profiles.md)de teste.

>[!NOTE]
>
>O número de cliques em um link específico é uma porcentagem do total de cliques para todo o conteúdo condicional em um delivery. Portanto, se você definiu o conteúdo dinâmico, o total das porcentagens exibidas para um perfil de teste específico pode não ser igual a 100.

Da mesma forma, para delivery e mensagens transacionais recorrentes, você pode selecionar o perfil de teste correspondente ao conteúdo dinâmico que deseja exibir, mas também pode visualização as porcentagens de cliques de acordo com o delivery de execução selecionado.

Um delivery de execução é uma mensagem técnica não acionável e não funcional criada nos seguintes casos:

* Cada vez que um delivery recorrente é executado ou atualizado.

   Por exemplo, se o fluxo de trabalho que gerencia esse delivery for executado uma vez por mês, haverá um delivery de execução por mês. Além disso, sempre que o conteúdo do delivery é atualizado, um delivery de execução adicional é criado.

   Para obter mais informações sobre delivery de email recorrentes, consulte delivery [de](../../automating/using/email-delivery.md)email.

* Por padrão, uma vez por mês para mensagens transacionais e sempre que um mensagen transacional é editado e publicado novamente.

   Para obter mais informações sobre mensagens transacionais, consulte [Sobre mensagens](../../channels/using/getting-started-with-transactional-msg.md)transacionais.

>[!NOTE]
>
>Como as IDs dos URLs rastreados são diferentes para cada execução, os dados de cliques em funcionamento não podem ser agregados para todos os delivery de execução de uma determinada mensagem. Ele só pode ser exibido para um delivery de execução por vez.

Depois que sua mensagem for enviada, selecione **[!UICONTROL Reports]** > **[!UICONTROL Hot clicks]** do painel do delivery.

Por padrão, o último delivery de execução é selecionado. Clique no **[!UICONTROL Change execution delivery]** botão para selecionar outro.

![](assets/delivery_reports_hot-clicks_3.png)

Somente as porcentagens de cliques para a execução do delivery selecionado são exibidas.
