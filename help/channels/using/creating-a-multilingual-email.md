---
title: Criação de um email multilíngue
description: Siga estas etapas para criar um email multilíngue direcionando destinatários com diferentes idiomas preferenciais.
page-status-flag: never-activated
uuid: e90f4ec8-14e3-4304-b5fc-bce0ba08a4ef
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: email-messages
discoiquuid: 79231445-1d51-499a-adcf-0c0f6db1cfa3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: cb5cc55c431cbe6050699a35ef2fff270f869dee

---


# Criação de um email multilíngue{#creating-a-multilingual-email}

Você pode enviar um email multilíngue para perfis com diferentes idiomas preferenciais: cada perfil receberá uma variante do email em seu idioma preferido.

Para fazer isso, verifique se você tem um modelo de email multilíngue disponível. Caso contrário, aprenda a criar um [nesta seção](../../channels/using/multilingual-messages-template.md).

O público-alvo é baseado em perfis com uma informação completa de idioma preferencial.

1. Crie um novo email com base em um modelo [](../../channels/using/multilingual-messages-template.md)multilíngue.

   ![](assets/multi_create1.png)

1. Defina as propriedades gerais e o público-alvo do email, assim como um email padrão. Consulte a seção [Criação de públicos-alvo](../../audiences/using/creating-audiences.md) .
1. Na quarta etapa do assistente de criação, defina as opções da variante. Se o modelo [](../../channels/using/multilingual-messages-template.md) multilíngue já contiver todos os parâmetros corretos, clique diretamente no **[!UICONTROL Create]**botão.

   ![](assets/multi_create4.png)

   Se necessário, adicione variantes usando o **[!UICONTROL Add an element]**botão.**[!UICONTROL Default]** não deve ser excluída. Quando definido como **[!UICONTROL default]**,[o idioma](../../audiences/using/creating-profiles.md)preferencial do perfil é usado para escolher a variante. Também é possível definir a**[!UICONTROL Default]** variante para qualquer outro idioma.

1. Confirmar criação de email: o painel de email será exibido.
1. Defina o conteúdo do email para cada variante. Dependendo do modelo escolhido, é possível definir vários assuntos, vários nomes de remetentes ou vários conteúdos diferentes. Use o menu suspenso para navegar entre as diferentes variantes do elemento. Para obter mais informações, consulte a seção do editor [de](../../designing/using/designing-content-in-adobe-campaign.md) conteúdo.

   ![](assets/multi_selectcontent.png)

1. Teste e valide sua mensagem. Consulte a seção [Enviando prova](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs) .
1. Agende o envio com o **[!UICONTROL Send after confirmation option]**.
1. Assim que seu email for enviado, você poderá acessar seus registros e relatórios para medir o sucesso de sua campanha. For more on reporting, refer to [this section](../../reporting/using/about-dynamic-reports.md).

**Tópico relacionado:**

* [Alcançar públicos multilíngues usando um fluxo de trabalho](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Engageyourcustomersateverystep)
