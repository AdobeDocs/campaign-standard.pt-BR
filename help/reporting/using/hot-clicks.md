---
title: Cliques ativos
seo-title: Cliques ativos
description: Cliques ativos
seo-description: Com o relatório de cliques fora da caixa, saiba onde o cliente clicou na entrega.
page-status-flag: nunca ativado
uuid: 7 ed 49 dd 3-d 7 ee -9 66 a -9 a 7 b-d 2 aa 16961667
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: relatórios
content-type: reference
topic-tags: lista de relatórios
discoiquuid: ecbc 1 ade -63 d 9-4 ac 2-9828-380 a 1 aa 95094
context-tags: Deliveryhotclicksrelatório, principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 77b0933bcd004cedc6a58f80717a4284b284e0cd

---


# Hot clicks{#hot-clicks}

This report can be accessed from the **[!UICONTROL Reports]** button in each delivery or transactional message.

![](assets/delivery_reports_hot-clicks_4.png)

Apresenta o conteúdo da mensagem (HTML e/ou texto) com a porcentagem de cliques em cada link.

![](assets/delivery_reports_10.png)

Se você tiver criado conteúdo dinâmico para a entrega, poderá exibir as porcentagens de cada condição definida. For more on inserting conditional content in a delivery, see [Defining dynamic content](../../designing/using/defining-dynamic-content-in-a-landing-page.md).

Por exemplo, imagine que você criou uma entrega com as seguintes condições:

* O link na imagem principal é diferente se o destinatário for um homem ou uma mulher.
* Também foi adicionado um link para uma oferta especial que é visível somente para os destinatários acima de 25.

Once your message is sent, select **[!UICONTROL Reports]** &gt; **[!UICONTROL Hot clicks]** from the delivery dashboard.

Por padrão, nenhum perfil é selecionado. Apenas cliques para destinatários cujo gênero é desconhecido e para os destinatários que estão abaixo de 25 ou cuja idade é desconhecida são exibidos.

![](assets/delivery_reports_hot-clicks_1.png)

To display clicks for women, click the **[!UICONTROL Change profile]** button and select a female test profile. Para exibir cliques para homens, prossiga de forma semelhante e selecione um perfil de teste masculino.

![](assets/delivery_reports_hot-clicks_2.png)

To display clicks for recipients over 25, click the **[!UICONTROL Change profile]** button and select a test profile whose birth date is matching this condition.

For more on test profiles, see [About test profiles](../../sending/using/managing-test-profiles-and-sending-proofs.md#about-test-profiles).

>[!NOTE]
>
>O número de cliques em um link específico é uma porcentagem do total de cliques para todo o conteúdo condicional em uma entrega. Portanto, se o conteúdo dinâmico tiver sido definido, o total de porcentagens exibidas para um perfil de teste específico talvez não seja igual a 100.

Da mesma forma, para entregas recorrentes e mensagens transacionais, você pode selecionar o perfil de teste correspondente ao conteúdo dinâmico que deseja exibir, mas também pode exibir as porcentagens de cliques de acordo com a entrega de execução selecionada.

Uma entrega de execução é uma mensagem técnica não acionável e não funcional que é criada nos seguintes casos:

* Cada vez que uma entrega recorrente é executada ou atualizada.

   Por exemplo, se o fluxo de trabalho gerenciar essa entrega é executado uma vez por mês, haverá uma entrega de execução por mês. Além disso, sempre que o conteúdo da entrega é atualizado, uma entrega de execução adicional é criada.

   For more on recurring email deliveries, see [Email delivery](../../automating/using/email-delivery.md).

* Por padrão, uma vez por mês para mensagens transacionais e cada vez que uma mensagem transacional é editada e publicada novamente.

   For more on transactional messages, see [About transactional messaging](../../channels/using/about-transactional-messaging.md).

>[!NOTE]
>
>Como as IDs rastreadas são diferentes para cada execução, os dados de cliques de hot cliques não podem ser agregados para todas as entregas de execução de uma determinada mensagem. Ela só pode ser exibida para uma entrega de execução por vez.

Once your message is sent, select **[!UICONTROL Reports]** &gt; **[!UICONTROL Hot clicks]** from the delivery dashboard.

Por padrão, a última entrega de execução é selecionada. Click the **[!UICONTROL Change execution delivery]** button to select another one.

![](assets/delivery_reports_hot-clicks_3.png)

Somente as porcentagens de cliques da execução de entrega selecionada são exibidas.
