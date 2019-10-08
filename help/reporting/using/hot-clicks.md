---
title: Hot clicks
seo-title: Hot clicks
description: Hot clicks
seo-description: Com o recurso Hot click out out-of-the-box, saiba onde o cliente clicou na entrega.
page-status-flag: nunca ativado
uuid: 7ed49dd3-d7ee-466a-9a7b-d2aa16961667
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: relatório
content-type: referência
topic-tags: lista de relatórios
discoiquuid: ecbc1ade-63d9-4ac2-9828-380a1aa95094
context-tags: deliveryHotClicksReport,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 159c33639ab7b53558dac2ce183c3801c15ccb0f

---


# Hot clicks{#hot-clicks}

Este relatório pode ser acessado a partir do **[!UICONTROL Reports]** botão em cada entrega ou mensagem transacional.

![](assets/delivery_reports_hot-clicks_4.png)

Ele apresenta o conteúdo da mensagem (HTML e/ou texto) com a porcentagem de cliques em cada link.

![](assets/delivery_reports_10.png)

Se você tiver criado conteúdo dinâmico para a entrega, poderá exibir as porcentagens para cada condição definida. Para obter mais informações sobre como inserir conteúdo condicional em uma entrega, consulte [Definição de conteúdo](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)dinâmico.

Por exemplo, imagine que você criou uma entrega com as seguintes condições:

* O link na imagem principal é diferente se o destinatário for um homem ou uma mulher.
* Você também adicionou um link a uma oferta especial que só é visível para destinatários com mais de 25 anos.

Depois que a mensagem for enviada, selecione **[!UICONTROL Reports]** &gt; **[!UICONTROL Hot clicks]** no painel de entrega.

Por padrão, nenhum perfil é selecionado. Somente os cliques para destinatários cujo gênero é desconhecido e para destinatários com menos de 25 anos ou idade desconhecida são exibidos.

![](assets/delivery_reports_hot-clicks_1.png)

Para exibir cliques para mulheres, clique no **[!UICONTROL Change profile]** botão e selecione um perfil de teste feminino. Para exibir cliques para homens, continue da mesma forma e selecione um perfil de teste masculino.

![](assets/delivery_reports_hot-clicks_2.png)

Para exibir cliques para destinatários com mais de 25 anos, clique no **[!UICONTROL Change profile]** botão e selecione um perfil de teste cuja data de nascimento corresponda a essa condição.

Para obter mais informações sobre perfis de teste, consulte [Sobre perfis](../../sending/using/managing-test-profiles-and-sending-proofs.md#about-test-profiles)de teste.

>[!NOTE]
>
>O número de cliques em um link específico é uma porcentagem do total de cliques para todo o conteúdo condicional em uma entrega. Portanto, se você definiu o conteúdo dinâmico, o total das porcentagens exibidas para um perfil de teste específico pode não ser igual a 100.

Da mesma forma, para entregas recorrentes e mensagens transacionais, você pode selecionar o perfil de teste correspondente ao conteúdo dinâmico que deseja exibir, mas também pode exibir as porcentagens de cliques de acordo com a entrega de execução selecionada.

Uma entrega de execução é uma mensagem técnica não acionável e não funcional criada nos seguintes casos:

* Cada vez que uma entrega recorrente é executada ou atualizada.

   Por exemplo, se o fluxo de trabalho que gerencia essa entrega for executado uma vez por mês, haverá uma entrega de execução por mês. Além disso, sempre que o conteúdo da entrega for atualizado, uma entrega de execução adicional será criada.

   Para obter mais informações sobre entregas recorrentes por email, consulte Entrega [por](../../automating/using/email-delivery.md)email.

* Por padrão, uma vez por mês para mensagens transacionais e sempre que uma mensagem transacional é editada e publicada novamente.

   Para obter mais informações sobre mensagens transacionais, consulte [Sobre mensagens transacionais](../../channels/using/about-transactional-messaging.md).

>[!NOTE]
>
>Como as IDs dos URLs rastreados são diferentes para cada execução, os dados de cliques em funcionamento não podem ser agregados para todas as entregas de execução de uma determinada mensagem. Ele só pode ser exibido para uma entrega de execução por vez.

Depois que a mensagem for enviada, selecione **[!UICONTROL Reports]** &gt; **[!UICONTROL Hot clicks]** no painel de entrega.

Por padrão, a entrega da última execução é selecionada. Clique no **[!UICONTROL Change execution delivery]** botão para selecionar outro.

![](assets/delivery_reports_hot-clicks_3.png)

Somente as porcentagens de cliques para a execução de entrega selecionada são exibidas.
