---
title: Criação de um email multilíngue com a integração do Adobe Experience Manager.
description: Com a integração do Adobe Experience Manager, é possível criar conteúdo diretamente no AEM e usá-lo posteriormente no Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 0f66fe2b-22b1-49d7-a080-29b00941a2cc
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '616'
ht-degree: 12%

---

# Criação de um email multilíngue com a integração do Adobe Experience Manager {#creating-multilingual-email-aem}

Com este documento, você aprenderá a criar um email multilíngue usando conteúdo do Adobe Experience Manager e cópias de idioma.

Os pré-requisitos são:

* Acesso a uma instância do AEM configurada para a integração.
* Acesso a uma instância do Adobe Campaign configurada para a integração.
* Um template de email multilíngue do Adobe Campaign configurado para receber conteúdo AEM.

## Criação de novo conteúdo de e-mail no Adobe Experience Manager {#creating-email-content-aem}

1. Na página inicial do Adobe Experience Manager, selecione **[!UICONTROL Site]**.

   ![](assets/aem_acs_1.png)

1. Selecione em qual pasta você deseja criar sua página e clique em **[!UICONTROL Create]** e depois em **[!UICONTROL Page]**. Aqui, criamos nossa página na pasta en_us, que será nosso idioma padrão.

   ![](assets/aem_acs_2.png)

1. Selecione o modelo **[!UICONTROL Adobe Campaign Email (ACS)]**.

1. Preencha as propriedades do seu email e clique em **[!UICONTROL Create]**.

   ![](assets/aem_acs_3.png)

1. Abra o novo conteúdo de email e personalize-o conforme necessário. Para obter mais informações, consulte esta [página](../../integrating/using/creating-email-experience-manager.md#editing-email-aem).

   ![](assets/aem_acs_4.png)

1. Na guia **[!UICONTROL Workflow]**, selecione o fluxo de trabalho de validação **[!UICONTROL Approve for Adobe Campaign]**. Você não poderá enviar um e-mail no Adobe Campaign se ele usar um conteúdo que não tenha sido aprovado.

   ![](assets/aem_acs_7.png)

1. Clique em **[!UICONTROL Complete]** e depois em **[!UICONTROL Newsletter review]** na janela **[!UICONTROL Complete work item]**.

1. Clique em **[!UICONTROL Complete]** e em **[!UICONTROL Newsletter approval]**. Após definir o conteúdo e os parâmetros de envio, você pode prosseguir para a aprovação, preparação e envio do email no Adobe Campaign Standard.

   ![](assets/aem_acs_8.png)

## Criação de cópias de idioma {#creating-language-copies}

Depois de criar o conteúdo de email, agora é necessário criar suas cópias de idioma que serão sincronizadas com o Adobe Campaign Standard como variantes.

1. Selecione a página criada anteriormente, clique em **[!UICONTROL Create]** e depois em **[!UICONTROL Language Copy]**.

   ![](assets/aem_acs_5.png)

1. Selecione o conteúdo de email criado anteriormente que será traduzido nos idiomas escolhidos e clique em **[!UICONTROL Next]**.

   ![](assets/aem_acs_6.png)

1. Na lista suspensa **[!UICONTROL Target language(s)]**, selecione em qual idioma o conteúdo será traduzido e clique em **[!UICONTROL Next]**.

   ![](assets/aem_acs_9.png)

1. Clique em **[!UICONTROL Create]**.

Suas cópias de idioma agora estão criadas, e você pode editar o conteúdo dependendo do idioma escolhido.

>[!CAUTION]
>
>Toda cópia de idioma precisa ser aprovada por meio do fluxo de trabalho de validação **[!UICONTROL Approve for Adobe Campaign]**. Você não poderá enviar um e-mail no Adobe Campaign se ele usar um conteúdo que não tenha sido aprovado.

![](assets/aem_acs_11.png)

## Criação de conteúdo multilíngue no Adobe Campaign Standard {#multilingual-acs}

1. Na página inicial do Adobe Campaign Standard, clique em **[!UICONTROL Create an email]**.

   ![](assets/aem_acs_12.png)

1. Selecione o modelo de email multilíngue do Adobe Campaign configurado para receber conteúdo do Adobe Experience Manager. Para saber mais sobre como criar um modelo vinculado à sua instância do Adobe Experience Manager, consulte esta [página](../../integrating/using/configure-experience-manager.md#config-acs).

   >[!NOTE]
   >
   >Nesse caso, será necessário duplicar o modelo interno **[!UICONTROL Multilingual email (mailMultiLang)]** para enviar seu email multilíngue.

   ![](assets/aem_acs_13.png)

1. Preencha os **[!UICONTROL Properties]** e **[!UICONTROL Audience]** do seu email e clique em **[!UICONTROL Create]**.

1. No **[!UICONTROL Edit properties]**, verifique se sua conta do Adobe Experience Manager está definida corretamente no menu suspenso **[!UICONTROL Content]**.

   ![](assets/aem_acs_20.png)

1. Clique em **[!UICONTROL Language copy creation]**.

   ![](assets/aem_acs_16.png)

1. Selecione o conteúdo do Adobe Experience Manager criado anteriormente e clique em **[!UICONTROL Confirm]**. O conteúdo do Adobe Experience Manager exibido aqui é apenas conteúdo validado e pode ser filtrado em seus **[!UICONTROL Label]** e **[!UICONTROL Path]**.

   >[!NOTE]
   >
   >A cópia do idioma escolhido será definida como padrão, você poderá alterá-la posteriormente no bloco **[!UICONTROL Content variant]**.

   ![](assets/aem_acs_17.png)

1. Clique em **[!UICONTROL Create variants]** para vincular seu conteúdo multilíngue. Em seguida, o Adobe Campaign Standard vinculará automaticamente as cópias de outros idiomas a esse conteúdo. As variantes criadas terão o mesmo rótulo e idioma de código que os escolhidos no Adobe Experience Manager.

   ![](assets/aem_acs_18.png)

1. Clique no bloco **[!UICONTROL Content variant]** para alterar a variante padrão, se necessário, e clique em **[!UICONTROL Confirm]**.

   ![](assets/aem_acs_19.png)

1. Se seu conteúdo ou suas variantes forem atualizados no Adobe Experience Manager, você poderá sincronizá-los diretamente no Adobe Campaign Standard com o botão **[!UICONTROL Refresh AEM contents]**.

1. Seu email agora está pronto para ser enviado. Para obter mais informações, consulte esta [página](../../sending/using/get-started-sending-messages.md).

   >[!NOTE]
   >
   >Você não poderá enviar um email no Adobe Campaign se ele usar um conteúdo AEM que não tenha sido aprovado.

Seu público receberá seu email dependendo do **[!UICONTROL Preferred languages]** definido no **[!UICONTROL Profiles]**. Para saber mais sobre como editar perfis e idiomas preferidos, consulte esta [página](../../audiences/using/editing-profiles.md).
