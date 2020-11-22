---
solution: Campaign Standard
product: campaign
title: Criação de uma notificação por push multilíngue
description: Crie notificações por push multilíngues para público alvo de seus usuários em seus idiomas e regiões preferidos.
audience: channels
content-type: reference
topic-tags: push-notifications
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '920'
ht-degree: 3%

---


# Criação de uma notificação por push multilíngue{#creating-a-multilingual-push-notification}

## Sobre a notificação por push multilíngue {#about-multilingual-push-notification}

Personalize seu conteúdo de notificação por push enviando mensagens com base nos idiomas e regiões preferidos de seus usuários. É possível importar diretamente variantes de conteúdo de notificação por push multilíngues no editor de conteúdo e enviar uma notificação por push multilíngue em um único delivery.

Esse recurso utiliza os idiomas preferenciais especificados nos perfis do recipient ou a preferência de idioma do sistema para assinantes de aplicativos móveis, dependendo do template do delivery usado para a notificação por push. Se a preferência de idioma não for preenchida para um determinado usuário, o sistema usará a variante padrão definida ao criar uma notificação por push multilíngue. Para obter mais informações sobre como gerenciar seus perfis e assinantes, consulte este [guia](../../audiences/using/get-started-profiles-and-audiences.md).

![](assets/multivariant_push_1.png)

Para usar variantes de conteúdo multilíngues para o delivery de notificação por push, siga estas etapas:

* [Etapa 1: Carregar variante de conteúdo multilíngue](#step-1--upload-multilingual-content-variant)
* [Etapa 2: Pré-visualização e finalização de uma notificação por push usando variantes de conteúdo multilíngue](#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants)
* [Etapa 3: Enviar e analisar o delivery de notificação por push multilíngue](#step-3--send-and-analyze-multilingual-push-notification-delivery)

## Etapa 1: Carregar variante de conteúdo multilíngue {#step-1--upload-multilingual-content-variant}

Antes de personalizar sua notificação por push multilíngue, precisamos primeiro carregar as variantes de conteúdo em um template do delivery multilíngue e criar o delivery.

>[!NOTE]
>
>Você também pode ignorar essa etapa se quiser criar uma variante manualmente para cada variante de idioma.

1. No **[!UICONTROL Marketing activities]**, clique no **[!UICONTROL Create]** botão e selecione **[!UICONTROL Push notification]**.
1. Selecione o modelo **[!UICONTROL Send multilingual push to Campaign profiles]** se desejar público alvo dos perfis Adobe Campaign que assinaram seu aplicativo móvel ou o modelo **[!UICONTROL Send multilingual push to app subscriber]** para enviar uma notificação por push a todos os usuários que opt in receber notificações de seu aplicativo móvel.

   ![](assets/multivariant_push_2.png)

1. Enter your push notification properties and select your mobile app in the **[!UICONTROL Associate a Mobile App to a delivery]** field.

   Observe que o menu suspenso exibirá os aplicativos SDK V4 e SDKs do Adobe Experience Platform.

1. Nas **[!UICONTROL Audiences]** janelas, arraste e solte query para ajustar sua audiência.

   Os query adicionados dependem do modelo escolhido: se você escolher o **[!UICONTROL Send multilingual push to Campaign profiles]** modelo, poderá query recipient conhecidos do seu aplicativo móvel. Ao passo que se você escolher o **[!UICONTROL Send multilingual push to app subscriber]** modelo, poderá query todos os assinantes de um aplicativo específico que opt in.
   >[!NOTE]
   >
   >Se você público alvo audiências com idiomas específicos, é necessário lista cada idioma direcionado no arquivo CSV.

   ![](assets/push_notif_audience.png)

1. Na **[!UICONTROL Manage Content Variants]** janela, arraste e solte o arquivo ou selecione um arquivo do computador.

   O arquivo deve ser codificado em UTF8 e ter um layout específico que pode ser encontrado clicando na **[!UICONTROL Download the sample file]** opção. Você também deve usar a sintaxe apropriada para valores de localidade. Para obter mais informações sobre o formato de arquivo e as localidades compatíveis, consulte esta [nota técnica](https://helpx.adobe.com/br/campaign/kb/acs-generate-csv-multilingual-push.html).

   ![](assets/multivariant_push_4.png)

1. Após carregar o arquivo, as variantes de idioma são automaticamente preenchidas na **[!UICONTROL Variants]** guia. Observe que você pode fornecer uma variável de conteúdo padrão **[!UICONTROL Default variant]** no arquivo se nenhum idioma preferencial for especificado para o usuário direcionado.

   ![](assets/multivariant_push_5.png)

1. A **[!UICONTROL Variant selection]** guia fornecerá um script para determinar a preferência de idioma a ser considerada, dependendo do template do delivery. Este é um script predefinido que não requer alterações.
1. Se quiser adicionar mais variantes não presentes no arquivo importado, clique no botão e adicione quantas novas variantes de idioma forem necessárias. **[!UICONTROL Add an element]**

   Ao adicionar variantes diferentes daquelas carregadas do arquivo, nenhum conteúdo será vinculado a esse idioma. Você precisará editar o conteúdo diretamente no painel do delivery.

   ![](assets/multivariant_push_6.png)

1. Clique **[!UICONTROL Create]** quando a configuração estiver concluída. Você sempre pode voltar para a **[!UICONTROL Content variant]** janela e fazer algumas alterações em seu painel de delivery.

   ![](assets/multivariant_push_8.png)

Agora você pode personalizar a sua notificação por push multilíngue em start.

## Etapa 2: Pré-visualização e finalização de uma notificação por push usando variantes de conteúdo multilíngue {#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants}

Depois de carregar o arquivo que contém as variantes de conteúdo, agora é possível pré-visualização as diferentes variantes do delivery de notificação por push.

Também é possível criar e editar mais variantes além das que são carregadas do arquivo.

1. Na **[!UICONTROL Content]** janela do painel do delivery, a lista suspensa permite que você pré-visualização o conteúdo da notificação por push, dependendo do idioma escolhido.

   ![](assets/multivariant_push_7.png)

1. Se uma variante de conteúdo não for especificada para um idioma específico, clique no ícone de sino abaixo da pré-visualização para adicionar conteúdo a essa variante de idioma.

   Ao clicar na **[!UICONTROL Content]** janela, a notificação por push representa o conteúdo do idioma selecionado na lista suspensa. As alterações feitas nesta janela afetarão apenas um idioma.

1. Você também pode clicar em uma variante de conteúdo para personalizá-la ainda mais, por exemplo, com campos de personalização.

   For more information on how to customize your push notification, refer to this [section](../../channels/using/customizing-a-push-notification.md).

   ![](assets/multivariant_push_9.png)

1. Clique na **[!UICONTROL Content variant]** janela se desejar adicionar ou excluir variantes de idioma.

   Observe que ao adicionar um novo idioma, você terá que adicionar manualmente conteúdo à notificação por push vinculada ao idioma adicionado.

   ![](assets/multivariant_push_10.png)

Seu delivery de notificação por push multilíngue está pronto para ser enviado.

## Etapa 3: Enviar e analisar o delivery de notificação por push multilíngue {#step-3--send-and-analyze-multilingual-push-notification-delivery}

Suas notificações por push de variantes de conteúdo multilíngue estão prontas para serem enviadas aos usuários.

1. Para preparar o start, clique no **[!UICONTROL Prepare]** botão.
1. Quando a preparação estiver terminada sem avisos, clique no **[!UICONTROL Confirm]** botão para start de envio do seu empurrão multilingue.

   ![](assets/multivariant_push_12.png)

1. Depois de enviar sua notificação por push com êxito, clique no **[!UICONTROL Reports]** ícone e **[!UICONTROL Dynamic reports]** para analisar o sucesso do seu delivery.

   ![](assets/multivariant_push_13.png)

1. Selecione **[!UICONTROL Push notification report]**.
1. Arraste e solte a **[!UICONTROL Variant]** dimensão em seu painel para filtrar seus dados por start.

   ![](assets/multivariant_push_11.png)

Agora você pode medir o impacto de seu delivery de notificação por push multilíngue em seus recipient.

**Tópicos relacionados:**

* [Relatório de notificação por push](../../reporting/using/push-notification-report.md)
* [Enviar uma notificação por push em um workflow](../../automating/using/push-notification-delivery.md)
* [Alcançar audiências multilíngues usando um fluxo de trabalho](https://helpx.adobe.com/br/campaign/kb/simplify-campaign-management.html#Engageyourcustomersateverystep)
