---
title: Hot clicks
description: Com o relatório pronto para uso Hot clicks, saiba onde seu cliente clicou em seu delivery.
audience: reporting
content-type: reference
topic-tags: list-of-reports
context-tags: deliveryHotClicksReport,main
feature: Reporting
role: Leader
level: Intermediate
exl-id: 5af37156-e93b-4ae9-9856-053364f211ef
source-git-commit: d0ef11f26a52603107af28231d70821b44753abb
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 0%

---

# Hot clicks{#hot-clicks}

>[!IMPORTANT]
>
>O relatório Hot Clicks mostra exclusivamente a versão do HTML do email e não é compatível com a versão de Texto.

Este relatório pode ser acessado pelo botão **[!UICONTROL Reports]** em cada entrega ou mensagem transacional.

![](assets/delivery_reports_hot-clicks_4.png)

Ele apresenta o conteúdo da mensagem com a porcentagem de cliques em cada link.

![](assets/delivery_reports_10.png)

Se você criou conteúdo dinâmico para o seu delivery, é possível visualizar as porcentagens de cada condição definida. Para obter mais informações sobre como inserir conteúdo condicional em uma entrega, consulte [Definindo conteúdo dinâmico](../../designing/using/personalization.md#defining-dynamic-content-in-an-email).

Por exemplo, imagine que você criou um delivery com as seguintes condições:

* O link na imagem principal é diferente se o recipient for um homem ou uma mulher.
* Você também adicionou um link para uma oferta especial que só é visível para recipients acima de 25 anos.

Depois que a mensagem for enviada, selecione **[!UICONTROL Reports]** > **[!UICONTROL Hot clicks]** no painel de entrega.

Por padrão, nenhum perfil está selecionado. Somente cliques para recipients cujo gênero é desconhecido e para recipients com menos de 25 anos ou cuja idade é desconhecida são exibidos.

![](assets/delivery_reports_hot-clicks_1.png)

Para exibir cliques de mulheres, clique no botão **[!UICONTROL Change profile]** e selecione um perfil de teste feminino. Para exibir cliques para homens, proceda de forma semelhante e selecione um perfil de teste macho.

![](assets/delivery_reports_hot-clicks_2.png)

Para exibir cliques de destinatários acima de 25 anos, clique no botão **[!UICONTROL Change profile]** e selecione um perfil de teste cuja data de nascimento corresponda a essa condição.

Para obter mais informações sobre perfis de teste, consulte [Sobre perfis de teste](../../audiences/using/managing-test-profiles.md).

>[!NOTE]
>
>O número de cliques em um link específico é uma porcentagem do total de cliques para todo o conteúdo condicional em um delivery. Portanto, se você definisse o conteúdo dinâmico, o total das porcentagens exibidas para um perfil de teste específico poderia não ser igual a 100.

Da mesma forma, para deliveries recorrentes e mensagens transacionais, é possível selecionar o perfil de teste correspondente ao conteúdo dinâmico que deseja exibir, mas também exibir as porcentagens de cliques de acordo com o delivery de execução selecionado.

Um delivery de execução é uma mensagem técnica não acionável e não funcional criada nos seguintes casos:

* Toda vez que um delivery recorrente é executado ou atualizado.

  Por exemplo, se o workflow que gerencia esse delivery for executado uma vez por mês, haverá um delivery de execução por mês. Além disso, cada vez que o conteúdo do delivery é atualizado, um delivery de execução adicional é criado.

  Para obter mais informações sobre entregas de email recorrentes, consulte [Entrega de email](../../automating/using/email-delivery.md).

* Por padrão, uma vez por mês para mensagens transacionais e sempre que uma mensagem transacional for editada e publicada novamente.

  Para obter mais informações sobre mensagens transacionais, consulte [Introdução a mensagens transacionais](../../channels/using/getting-started-with-transactional-msg.md).

>[!NOTE]
>
>Como as IDs dos URLs rastreados são diferentes para cada execução, os dados de cliques ativos não podem ser agregados para todos os deliveries de execução de uma determinada mensagem. Ele só pode ser exibido para um delivery de execução por vez.

Depois que a mensagem for enviada, selecione **[!UICONTROL Reports]** > **[!UICONTROL Hot clicks]** no painel de entrega.

Por padrão, o último delivery de execução é selecionado. Clique no botão **[!UICONTROL Change execution delivery]** para selecionar outro.

![](assets/delivery_reports_hot-clicks_3.png)

Somente as porcentagens de clique para a execução de delivery selecionada são exibidas.
