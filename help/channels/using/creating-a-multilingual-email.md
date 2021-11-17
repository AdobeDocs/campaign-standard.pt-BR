---
title: Criação de um email multilíngue
description: Siga estas etapas para criar um email multilíngue direcionado a recipients com diferentes idiomas de preferência.
audience: channels
content-type: reference
topic-tags: email-messages
feature: Email
role: User
level: Intermediate
exl-id: fcf192cb-f2d5-4340-bc2f-add0c195ad4e
source-git-commit: 8be43668d1a4610c3388ad27e493a689925dc88c
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 24%

---

# Criação de um email multilíngue{#creating-a-multilingual-email}

Você pode enviar um email multilíngue para perfis com diferentes idiomas de preferência: cada perfil receberá uma variante do email no idioma preferencial.

Para fazer isso, verifique se você tem um template de email multilíngue disponível. Caso contrário, saiba como criar um em [esta seção](../../channels/using/multilingual-messages-template.md).

O público-alvo é baseado em perfis com uma informação completa sobre o idioma preferencial.

1. Crie um novo email com base em um [modelo multilíngue](../../channels/using/multilingual-messages-template.md).

   ![](assets/multi_create1.png)

1. Defina as propriedades gerais e o público-alvo do email, assim como para um email padrão. Consulte a seção [Criação de públicos](../../audiences/using/creating-audiences.md).
1. Na quarta etapa do assistente de criação, defina as opções da variante. Se a variável [modelo multilíngue](../../channels/using/multilingual-messages-template.md) já contém todos os parâmetros corretos, você pode clicar diretamente no botão **[!UICONTROL Create]** botão.

   ![](assets/multi_create4.png)

   Se necessário, adicione variantes usando a variável **[!UICONTROL Add an element]** botão. **[!UICONTROL Default]** não deve ser excluída. Quando definido como **[!UICONTROL default]**, [o idioma preferencial do perfil](../../audiences/using/creating-profiles.md) é usada para escolher a variante. Também é possível definir a variável **[!UICONTROL Default]** para qualquer outro idioma.

1. Confirmar criação de email: o painel de email será exibido.
1. Defina o conteúdo do email para cada variante. Dependendo do modelo escolhido, é possível definir vários assuntos, vários nomes de remetentes ou vários conteúdos diferentes. Use o menu suspenso para navegar entre as diferentes variantes do elemento. Para obter mais informações, consulte a seção [Editor de conteúdo](../../designing/using/designing-content-in-adobe-campaign.md).

   ![](assets/multi_selectcontent.png)

1. Teste e valide sua mensagem. Consulte a [Envio de prova](../../sending/using/sending-proofs.md) seção.
1. Programe o envio com a **[!UICONTROL Send after confirmation option]**.
1. Depois que seu email for enviado, você poderá acessar seus logs e relatórios para medir o sucesso de sua campanha. Para obter mais informações sobre relatórios, consulte [esta seção](../../reporting/using/about-dynamic-reports.md).

