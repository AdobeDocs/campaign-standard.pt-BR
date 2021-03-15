---
solution: Campaign Standard
product: campaign
title: Criação de um email multilíngue
description: Siga estas etapas para criar um email multilíngue direcionado a recipients com diferentes idiomas de preferência.
audience: channels
content-type: reference
topic-tags: email-messages
feature: Email
role: Profissional
level: Intermediário
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 25%

---


# Criação de um email multilíngue{#creating-a-multilingual-email}

Você pode enviar um email multilíngue para perfis com diferentes idiomas de preferência: cada perfil receberá uma variante do email no idioma preferencial.

Para fazer isso, verifique se você tem um template de email multilíngue disponível. Caso contrário, saiba como criar um em [esta seção](../../channels/using/multilingual-messages-template.md).

O público-alvo é baseado em perfis com uma informação completa sobre o idioma preferencial.

1. Crie um novo email com base em um [modelo multilíngue](../../channels/using/multilingual-messages-template.md).

   ![](assets/multi_create1.png)

1. Defina as propriedades gerais e o público-alvo do email, assim como para um email padrão. Consulte a seção [Criação de públicos](../../audiences/using/creating-audiences.md).
1. Na quarta etapa do assistente de criação, defina as opções da variante. Se o [modelo multilíngue](../../channels/using/multilingual-messages-template.md) já contiver todos os parâmetros corretos, clique diretamente no botão **[!UICONTROL Create]**.

   ![](assets/multi_create4.png)

   Se necessário, adicione variantes usando o botão **[!UICONTROL Add an element]**. **[!UICONTROL Default]** não deve ser excluída. Quando definido como **[!UICONTROL default]**, [o idioma preferencial do perfil](../../audiences/using/creating-profiles.md) é usado para escolher a variante. Você também pode definir a variante **[!UICONTROL Default]** para qualquer outro idioma.

1. Confirmar criação de email: o painel de email será exibido.
1. Defina o conteúdo do email para cada variante. Dependendo do modelo escolhido, é possível definir vários assuntos, vários nomes de remetentes ou vários conteúdos diferentes. Use o menu suspenso para navegar entre as diferentes variantes do elemento. Para obter mais informações, consulte a seção [Editor de conteúdo](../../designing/using/designing-content-in-adobe-campaign.md).

   ![](assets/multi_selectcontent.png)

1. Teste e valide sua mensagem. Consulte a seção [Envio de prova](../../sending/using/sending-proofs.md) .
1. Programe o envio com o **[!UICONTROL Send after confirmation option]**.
1. Depois que seu email for enviado, você poderá acessar seus logs e relatórios para medir o sucesso de sua campanha. Para obter mais informações sobre relatórios, consulte [esta seção](../../reporting/using/about-dynamic-reports.md).

**Tópicos relacionados:**

* [Alcance de públicos-alvo multilíngues usando um fluxo de trabalho](https://helpx.adobe.com/br/campaign/kb/simplify-campaign-management.html#Engageyourcustomersateverystep)
