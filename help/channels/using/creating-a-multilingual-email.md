---
title: Criação de um email multilíngue
description: Siga estas etapas para criar um email multilíngue direcionado a recipients com diferentes idiomas preferenciais.
audience: channels
content-type: reference
topic-tags: email-messages
feature: Email
role: User
level: Intermediate
exl-id: fcf192cb-f2d5-4340-bc2f-add0c195ad4e
TQID: https://experienceleague.adobe.com/dz14KptzZtyP8Oo-RaYvZKP5D3L4akcJJmY2f-p1nuE
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 279
ht-degree: 24%

---

# Criação de um email multilíngue{#creating-a-multilingual-email}

É possível enviar um email multilíngue para perfis com diferentes idiomas preferenciais: cada perfil receberá uma variante do email em seu idioma preferencial.

Para fazer isso, verifique se você tem um template de email multilíngue disponível. Caso contrário, saiba como criar um em [esta seção](../../channels/using/multilingual-messages-template.md).

O público-alvo é baseado em perfis com informações de idioma preferencial preenchidas.

1. Crie um novo email com base em um [modelo multilíngue](../../channels/using/multilingual-messages-template.md).

   ![](assets/multi_create1.png)

1. Defina as propriedades gerais e o público-alvo do email, assim como para um email padrão. Consulte a seção [Criação de públicos-alvos](../../audiences/using/creating-audiences.md).

1. Na quarta etapa do assistente de criação, defina as opções de variante. Se o [modelo multilíngue](../../channels/using/multilingual-messages-template.md) já contiver todos os parâmetros corretos, clique diretamente no botão **[!UICONTROL Create]**.

   ![](assets/multi_create4.png)

   Se necessário, adicione variantes usando o botão **[!UICONTROL Add an element]**. A variante **[!UICONTROL Default]** não deve ser excluída. Quando definido como **[!UICONTROL default]**, [o idioma preferencial do perfil](../../audiences/using/creating-profiles.md) é usado para escolher a variante. Você também pode definir a variante **[!UICONTROL Default]** para qualquer outro idioma.

1. Confirme a criação do email: o painel de email será exibido.
1. Defina o conteúdo do email para cada variante. Dependendo do modelo escolhido, é possível definir vários assuntos, vários nomes de remetentes ou vários conteúdos diferentes. Use o menu suspenso para navegar entre as diferentes variantes do elemento. Para obter mais informações, consulte a seção [Editor de conteúdo](../../designing/using/designing-content-in-adobe-campaign.md).

   ![](assets/multi_selectcontent.png)

1. Teste e valide a mensagem. Consulte a seção [Enviando prova](../../sending/using/sending-proofs.md).
1. Agende o envio com o **[!UICONTROL Send after confirmation option]**.
1. Depois que o email é enviado, você pode acessar os logs e relatórios para medir o sucesso da campanha. Para obter mais informações sobre relatórios, consulte [esta seção](../../reporting/using/about-dynamic-reports.md).

