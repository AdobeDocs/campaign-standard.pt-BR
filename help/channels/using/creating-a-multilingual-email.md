---
title: Criação de um email multilíngue
seo-title: Criação de um email multilíngue
description: Criação de um email multilíngue
seo-description: Siga estas etapas para criar um direcionamento de email multilíngue com idiomas preferenciais diferentes.
page-status-flag: nunca ativado
uuid: e 90 f 4 ec 8-14 e 3-4304-b 5 fc-bce 0 ba 08 a 4 ef
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canais
content-type: reference
topic-tags: por email
discoiquuid: 79231445-1 d 51-499 a-adcf -0 c 0 f 6 db 1 cfa 3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 855db33971afdf9f02bf1b00be67c9e3f50bee06

---


# Creating a multilingual email{#creating-a-multilingual-email}

É possível enviar um email multilíngue para perfis com diferentes idiomas preferenciais: cada perfil receberá uma variante do email em seu idioma preferido.

Para fazer isso, verifique se você tem um modelo de email multilíngue disponível. If not, learn how to create one in [this section](../../start/using/creating-a-multilingual-template.md).

O público-alvo se baseia em perfis com informações de idioma preferenciais concluídas.

1. Create a new email based on a [multilingual template](../../start/using/creating-a-multilingual-template.md).

   ![](assets/multi_create1.png)

1. Defina as propriedades gerais e o público-alvo do email, como para um email padrão. Refer to the [Creating audiences](../../audiences/using/creating-audiences.md) section.
1. Na quarta etapa do assistente de criação, defina as opções de variante. If the [multilingual template](../../start/using/creating-a-multilingual-template.md) already contains all the right parameters, you can directly click on the **[!UICONTROL Create]** button.

   ![](assets/multi_create4.png)

   If needed, add variants using the **[!UICONTROL Add an element]** button. **[!UICONTROL Default]** não deve ser excluída. When set to **[!UICONTROL default]**, [the profile's preferred language](../../audiences/using/creating-profiles.md) is used to choose the variant. You can also set the **[!UICONTROL Default]** variant to any other language.

1. Confirme a criação de e-mail: o painel de e-mail será exibido.
1. Defina o conteúdo de email para cada variação. Dependendo do modelo escolhido, você pode definir vários assuntos, vários nomes de remetentes ou vários conteúdos diferentes. Use o menu suspenso para navegar entre as diferentes variantes do elemento. For more information, consult the [content editor](../../designing/using/about-email-content-design.md) section.

   ![](assets/multi_selectcontent.png)

1. Teste e valide a mensagem. Refer to the [Sending proof](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs) section.
1. Schedule the send with the **[!UICONTROL Send after confirmation option]**.
1. Após o envio do email, você poderá acessar seus registros e relatórios para medir o sucesso da sua campanha. For more on reporting, refer to [this section](../../reporting/using/about-dynamic-reports.md).

