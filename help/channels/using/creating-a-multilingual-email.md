---
solution: Campaign Standard
product: campaign
title: Criação de um email multilíngue
description: Siga estas etapas para criar recipient de segmentação de email multilíngues com diferentes idiomas preferenciais.
audience: channels
content-type: reference
topic-tags: email-messages
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 25%

---


# Criação de um email multilíngue{#creating-a-multilingual-email}

Você pode enviar um email multilíngue para perfis com diferentes idiomas preferenciais: cada perfil receberá uma variante do email em seu idioma preferido.

Para fazer isso, verifique se você tem um modelo de email multilíngue disponível. Caso contrário, aprenda a criar um em [esta seção](../../channels/using/multilingual-messages-template.md).

A audiência é baseada em perfis com informações completas de idioma preferencial.

1. Crie um novo email com base em um [modelo multilíngue](../../channels/using/multilingual-messages-template.md).

   ![](assets/multi_create1.png)

1. Defina as propriedades gerais e o público-alvo do email, assim como para um email padrão. Consulte a seção [Criação de públicos](../../audiences/using/creating-audiences.md).
1. Na quarta etapa do assistente de criação, defina as opções da variante. Se [modelo multilíngue](../../channels/using/multilingual-messages-template.md) já contiver todos os parâmetros corretos, clique diretamente no botão **[!UICONTROL Create]**.

   ![](assets/multi_create4.png)

   Se necessário, adicione variantes usando o botão **[!UICONTROL Add an element]**. **[!UICONTROL Default]** não deve ser excluída. Quando definido como **[!UICONTROL default]**, [o idioma preferencial do perfil](../../audiences/using/creating-profiles.md) é usado para escolher a variante. Você também pode definir a variante **[!UICONTROL Default]** para qualquer outro idioma.

1. Confirmar criação de email: o painel de email será exibido.
1. Defina o conteúdo do email para cada variante. Dependendo do modelo escolhido, é possível definir vários assuntos, vários nomes de remetentes ou vários conteúdos diferentes. Use o menu suspenso para navegar entre as diferentes variantes do elemento. Para obter mais informações, consulte a seção [Editor de conteúdo](../../designing/using/designing-content-in-adobe-campaign.md).

   ![](assets/multi_selectcontent.png)

1. Teste e valide sua mensagem. Consulte a seção [Enviando prova](../../sending/using/sending-proofs.md).
1. Agende o envio com **[!UICONTROL Send after confirmation option]**.
1. Assim que seu email for enviado, você poderá acessar seus registros e relatórios para medir o sucesso de sua campanha. Para obter mais informações sobre relatórios, consulte [esta seção](../../reporting/using/about-dynamic-reports.md).

**Tópicos relacionados:**

* [Alcançar audiências multilíngues usando um fluxo de trabalho](https://helpx.adobe.com/br/campaign/kb/simplify-campaign-management.html#Engageyourcustomersateverystep)
