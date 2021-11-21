---
title: Criação de uma notificação por push multilíngue
description: Crie notificações por push multilíngues para direcionar seus usuários nos idiomas e regiões de sua preferência.
audience: channels
content-type: reference
topic-tags: push-notifications
feature: Push
role: User
level: Intermediate
exl-id: 1b81f6e9-cb31-4664-af78-22e70043fbc8
source-git-commit: b5e98c07ee55cab0b6a628a97162ccd64711501a
workflow-type: tm+mt
source-wordcount: '903'
ht-degree: 2%

---

# Criação de uma notificação por push multilíngue{#creating-a-multilingual-push-notification}

## Sobre a notificação por push multilíngue {#about-multilingual-push-notification}

Personalize seu conteúdo de notificação por push enviando mensagens com base nos idiomas e regiões preferidos de seus usuários. Você pode importar diretamente variantes de conteúdo de notificações por push multilíngues no editor de conteúdo e enviar uma notificação por push multilíngue em um único delivery.

Esse recurso utiliza os idiomas preferenciais especificados nos perfis dos destinatários ou na preferência de idioma do sistema para Assinantes de aplicativos móveis, dependendo do modelo de entrega usado para notificação por push. Se a preferência de idioma não for preenchida para um usuário específico, o sistema usará a variante padrão que é definida ao criar uma notificação por push multilíngue. Para obter mais informações sobre como gerenciar perfis e assinantes, consulte esta seção [guia](../../audiences/using/get-started-profiles-and-audiences.md).

![](assets/multivariant_push_1.png)

Para usar variantes de conteúdo multilíngues para o delivery de notificação por push, siga estas etapas:

* [Etapa 1: Fazer upload de variante de conteúdo multilíngue](#step-1--upload-multilingual-content-variant)
* [Etapa 2: Visualizar e finalizar uma notificação por push usando variantes de conteúdo multilíngues](#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants)
* [Etapa 3: Enviar e analisar o delivery de notificação por push multilíngue](#step-3--send-and-analyze-multilingual-push-notification-delivery)

## Etapa 1: Fazer upload de variante de conteúdo multilíngue {#step-1--upload-multilingual-content-variant}

Antes de personalizar sua notificação por push multilíngue, primeiro precisamos carregar as variantes de conteúdo em um template de delivery multilíngue e criar o delivery.

>[!NOTE]
>
>Também é possível ignorar essa etapa se quiser criar uma variante manualmente para cada variante de idioma.

1. No **[!UICONTROL Marketing activities]**, clique no botão **[!UICONTROL Create]** botão e selecione **[!UICONTROL Push notification]**.
1. Selecionar o modelo **[!UICONTROL Send multilingual push to Campaign profiles]** se quiser direcionar os perfis do Adobe Campaign que assinaram seu aplicativo móvel ou o modelo **[!UICONTROL Send multilingual push to app subscriber]** para enviar uma notificação por push a todos os usuários que optaram por receber notificações do aplicativo móvel.

   ![](assets/multivariant_push_2.png)

1. Insira suas propriedades de notificação por push e selecione seu aplicativo móvel no **[!UICONTROL Associate a Mobile App to a delivery]** campo.

   Observe que a lista suspensa exibirá os aplicativos SDK V4 e SDKs do Adobe Experience Platform.

1. No **[!UICONTROL Audiences]** , arraste e solte queries para ajustar o público-alvo.

   As consultas adicionadas dependem do template escolhido: se você escolher a variável **[!UICONTROL Send multilingual push to Campaign profiles]** Você pode consultar recipients conhecidos do seu aplicativo móvel. Considerando que, se você escolher a variável **[!UICONTROL Send multilingual push to app subscriber]** , você pode consultar todos os assinantes de um aplicativo específico que optaram por participar.
   >[!NOTE]
   >
   >Se você direcionar públicos-alvo com idiomas específicos, será necessário listar cada idioma direcionado no arquivo CSV.

   ![](assets/push_notif_audience.png)

1. No **[!UICONTROL Manage Content Variants]** arraste e solte o arquivo ou selecione um arquivo de seu computador.

   O arquivo deve ser codificado em UTF8 e ter um layout específico que pode ser encontrado clicando no link **[!UICONTROL Download the sample file]** opção. Você também deve usar a sintaxe apropriada para valores de localidade. Para obter mais informações sobre o formato de arquivo e as localidades compatíveis, consulte esta seção [página](../../channels/using/generating-csv-multilingual-push.md).

   ![](assets/multivariant_push_4.png)

1. Depois de fazer upload do arquivo, as variantes de idioma são automaticamente preenchidas na variável **[!UICONTROL Variants]** guia . Observe que você pode fornecer um **[!UICONTROL Default variant]** no arquivo que será sua variante de conteúdo padrão se nenhum idioma preferencial for especificado para o usuário direcionado.

   ![](assets/multivariant_push_5.png)

1. O **[!UICONTROL Variant selection]** A guia fornecerá um script para determinar qual preferência de idioma será levada em conta, dependendo do template do delivery. Este é um script pronto para uso que não requer alterações.
1. Se quiser adicionar mais variantes não presentes no arquivo importado, clique no botão **[!UICONTROL Add an element]** e adicione quantas novas variantes de idioma forem necessárias.

   Ao adicionar variantes diferentes das carregadas do arquivo, nenhum conteúdo será vinculado a esse idioma. Você terá que editar o conteúdo diretamente no painel do delivery.

   ![](assets/multivariant_push_6.png)

1. Clique em **[!UICONTROL Create]** quando a configuração for concluída. Você sempre pode voltar para a **[!UICONTROL Content variant]** e faça algumas alterações no seu painel de delivery.

   ![](assets/multivariant_push_8.png)

Agora é possível começar a personalizar a notificação por push multilíngue.

## Etapa 2: Visualizar e finalizar uma notificação por push usando variantes de conteúdo multilíngues {#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants}

Após carregar o arquivo que contém as variantes de conteúdo, você pode visualizar as diferentes variantes do delivery de notificação por push.

Também é possível criar e editar mais variantes além das que foram carregadas do arquivo.

1. No **[!UICONTROL Content]** no painel do delivery, a lista suspensa permite visualizar o conteúdo da notificação por push, dependendo do idioma escolhido.

   ![](assets/multivariant_push_7.png)

1. Se uma variante de conteúdo não for especificada para um idioma específico, clique no ícone de sino abaixo da visualização para começar a adicionar conteúdo a essa variante de idioma.

   Ao clicar no botão **[!UICONTROL Content]** , a notificação por push representa o conteúdo do idioma selecionado no menu suspenso. As alterações feitas nessa janela afetarão apenas um idioma.

1. Você também pode clicar em uma variante de conteúdo para personalizá-la ainda mais, por exemplo, com campos de personalização.

   Para obter mais informações sobre como personalizar sua notificação por push, consulte esta seção [seção](../../channels/using/customizing-a-push-notification.md).

   ![](assets/multivariant_push_9.png)

1. Clique no botão **[!UICONTROL Content variant]** se desejar adicionar ou excluir variantes de idioma.

   Observe que, ao adicionar um novo idioma, é necessário adicionar manualmente o conteúdo à notificação por push vinculada ao idioma adicionado.

   ![](assets/multivariant_push_10.png)

O delivery de notificação por push multilíngue agora está pronto para ser enviado.

## Etapa 3: Enviar e analisar o delivery de notificação por push multilíngue {#step-3--send-and-analyze-multilingual-push-notification-delivery}

Suas notificações por push de variante de conteúdo multilíngue agora estão prontas para serem enviadas aos usuários.

1. Para começar a preparar o envio, clique no link **[!UICONTROL Prepare]** botão.
1. Quando a preparação for concluída sem avisos, você poderá clicar no botão **[!UICONTROL Confirm]** para começar a enviar o push multilíngue.

   ![](assets/multivariant_push_12.png)

1. Depois de enviar sua notificação por push com êxito, clique no link **[!UICONTROL Reports]** ícone e **[!UICONTROL Dynamic reports]** para analisar o sucesso do seu delivery.

   ![](assets/multivariant_push_13.png)

1. Selecione **[!UICONTROL Push notification report]**.
1. Arraste e solte a **[!UICONTROL Variant]** no painel para começar a filtrar os dados.

   ![](assets/multivariant_push_11.png)

Agora é possível medir o impacto do delivery de notificação por push multilíngue nos recipients.

**Tópicos relacionados:**

* [Relatório de notificação por push](../../reporting/using/push-notification-report.md)
* [Enviar uma notificação por push em um workflow](../../automating/using/push-notification-delivery.md)
