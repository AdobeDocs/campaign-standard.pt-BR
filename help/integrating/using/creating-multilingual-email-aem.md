---
title: Criação de um email multilíngue com a integração do Adobe Experience Manager.
description: Com a integração do Adobe Experience Manager, você pode criar conteúdo diretamente no AEM e usá-lo posteriormente no Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 0f66fe2b-22b1-49d7-a080-29b00941a2cc
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '617'
ht-degree: 15%

---

# Criação de um email multilíngue com a integração do Adobe Experience Manager {#creating-multilingual-email-aem}

Com este documento, você aprenderá a criar um email multilíngue usando o conteúdo do Adobe Experience Manager e cópias de idioma.

Os pré-requisitos são:

* Acesso a uma instância de AEM configurada para a integração.
* Acesso a uma instância do Adobe Campaign configurada para a integração.
* Um modelo de email multilíngue do Adobe Campaign configurado para receber conteúdo AEM.

## Criação de novo conteúdo de e-mail no Adobe Experience Manager {#creating-email-content-aem}

1. Na página inicial do Adobe Experience Manager, selecione **[!UICONTROL Site]**.

   ![](assets/aem_acs_1.png)

1. Selecione em qual pasta você deseja criar a página e clique em **[!UICONTROL Create]** then **[!UICONTROL Page]**. Aqui, criamos a página na pasta en_us, que será o nosso idioma padrão.

   ![](assets/aem_acs_2.png)

1. Selecione o **[!UICONTROL Adobe Campaign Email (ACS)]** modelo .

1. Preencha as propriedades do seu email e clique em **[!UICONTROL Create]**.

   ![](assets/aem_acs_3.png)

1. Abra seu novo conteúdo de email e personalize-o conforme necessário. Para obter mais informações, consulte esta [página](../../integrating/using/creating-email-experience-manager.md#editing-email-aem).

   ![](assets/aem_acs_4.png)

1. No **[!UICONTROL Workflow]** selecione a guia **[!UICONTROL Approve for Adobe Campaign]** fluxo de trabalho de validação. Você não poderá enviar um e-mail no Adobe Campaign se ele usar um conteúdo que não tenha sido aprovado.

   ![](assets/aem_acs_7.png)

1. Clique em **[!UICONTROL Complete]** then **[!UICONTROL Newsletter review]** do **[!UICONTROL Complete work item]** janela.

1. Clique em **[!UICONTROL Complete]** e em **[!UICONTROL Newsletter approval]**. Depois que os parâmetros de conteúdo e envio forem definidos, você poderá prosseguir com a aprovação, preparação e envio do email no Adobe Campaign Standard.

   ![](assets/aem_acs_8.png)

## Criação de cópias de idioma {#creating-language-copies}

Depois de criar o conteúdo de email, agora é necessário criar cópias de idioma que serão sincronizadas com o Adobe Campaign Standard como variantes.

1. Selecione a página criada anteriormente e clique em **[!UICONTROL Create]** then **[!UICONTROL Language Copy]**.

   ![](assets/aem_acs_5.png)

1. Selecione o conteúdo de email criado anteriormente que será traduzido nos idiomas escolhidos e clique em **[!UICONTROL Next]**.

   ![](assets/aem_acs_6.png)

1. No **[!UICONTROL Target language(s)]** , selecione em qual idioma o conteúdo será traduzido e clique em **[!UICONTROL Next]**.

   ![](assets/aem_acs_9.png)

1. Clique em **[!UICONTROL Create]**.

Agora, suas cópias de idioma são criadas. Agora é possível editar o conteúdo dependendo do idioma escolhido.

>[!CAUTION]
>
>Todas as cópias de idioma precisam ser aprovadas por meio do **[!UICONTROL Approve for Adobe Campaign]** fluxo de trabalho de validação. Você não poderá enviar um e-mail no Adobe Campaign se ele usar um conteúdo que não tenha sido aprovado.

![](assets/aem_acs_11.png)

## Criar seu conteúdo multilíngue no Adobe Campaign Standard {#multilingual-acs}

1. Na página inicial do Adobe Campaign Standard, clique em **[!UICONTROL Create an email]**.

   ![](assets/aem_acs_12.png)

1. Selecione o modelo de email multilíngue do Adobe Campaign configurado para receber conteúdo do Adobe Experience Manager. Para saber mais sobre como criar um template vinculado à instância do Adobe Experience Manager, consulte [página](../../integrating/using/configure-experience-manager.md#config-acs).

   >[!NOTE]
   >
   >Nesse caso, será necessário duplicar o template incorporado **[!UICONTROL Multilingual email (mailMultiLang)]** para enviar seu email multilíngue.

   ![](assets/aem_acs_13.png)

1. Preencha o **[!UICONTROL Properties]** e **[!UICONTROL Audience]** do seu email e clique em **[!UICONTROL Create]**.

1. No **[!UICONTROL Edit properties]**, verifique se a conta do Adobe Experience Manager está definida corretamente na variável **[!UICONTROL Content]** lista suspensa.

   ![](assets/aem_acs_20.png)

1. Clique em **[!UICONTROL Language copy creation]**.

   ![](assets/aem_acs_16.png)

1. Selecione o conteúdo do Adobe Experience Manager criado anteriormente e clique em **[!UICONTROL Confirm]**. O conteúdo do Adobe Experience Manager exibido aqui é apenas um conteúdo validado e pode ser filtrado em seus **[!UICONTROL Label]** e **[!UICONTROL Path]**.

   >[!NOTE]
   >
   >A cópia de idioma escolhida será definida como padrão. Posteriormente, você poderá alterá-la no **[!UICONTROL Content variant]** bloco.

   ![](assets/aem_acs_17.png)

1. Clique em **[!UICONTROL Create variants]** para vincular seu conteúdo multilíngue. O Adobe Campaign Standard vinculará automaticamente as cópias de outro idioma a esse conteúdo. As variantes criadas terão o mesmo rótulo e idioma de código que os escolhidos no Adobe Experience Manager.

   ![](assets/aem_acs_18.png)

1. Clique no botão **[!UICONTROL Content variant]** bloquear para alterar sua variante padrão, se necessário, e clicar em **[!UICONTROL Confirm]**.

   ![](assets/aem_acs_19.png)

1. Se seu conteúdo ou variantes forem atualizados no Adobe Experience Manager, você poderá sincronizá-lo diretamente no Adobe Campaign Standard com a variável **[!UICONTROL Refresh AEM contents]** botão.

1. Seu email agora está pronto para ser enviado. Para obter mais informações sobre essas operações, consulte esta [página](../../sending/using/get-started-sending-messages.md).

   >[!NOTE]
   >
   >Você não poderá enviar um email no Adobe Campaign se ele usar um conteúdo AEM que não tenha sido aprovado.

Seu público-alvo receberá seu email dependendo do **[!UICONTROL Preferred languages]** , **[!UICONTROL Profiles]**. Para saber mais sobre como editar perfis e idiomas de preferência, consulte esta seção [página](../../audiences/using/editing-profiles.md).
