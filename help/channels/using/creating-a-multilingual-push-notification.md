---
title: Criação de uma notificação por push multilíngue
seo-title: Criação de uma notificação por push multilíngue
description: Criação de uma notificação por push multilíngue
seo-description: Crie notificações por push multilíngues para direcionar seus usuários em seus idiomas e regiões preferidos.
page-status-flag: nunca ativado
uuid: d 4 aff 741-e 969-47 c 6-bae 8-787 c 6 c 673191
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canais
content-type: reference
topic-tags: notificações por push
discoiquuid: f 9 bb 2235-d 388-4025-9 ace -734 beb 0 c 1961
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 782a5f89b0361f1cbe59c9b353ca90dec90c3906

---


# Criação de uma notificação por push multilíngue{#creating-a-multilingual-push-notification}

## Sobre a notificação por push multilíngue {#about-multilingual-push-notification}

Personalize o conteúdo de notificação por push enviando mensagens com base em idiomas e regiões preferenciais de seus usuários. Você pode importar diretamente variáveis de conteúdo de notificação por push multilíngues no editor de conteúdo e enviar uma notificação por push multilíngue em uma única entrega.

Esse recurso aproveita os idiomas preferidos especificados nos perfis dos destinatários ou na preferência idioma do sistema para Assinantes do aplicativo móvel, dependendo do modelo de entrega usado para a notificação por push. Se a preferência de idioma não for preenchida para um usuário específico, o sistema usará a variante padrão definida durante a criação de uma notificação por push multilíngue. Para obter mais informações sobre como gerenciar seus perfis e assinantes, consulte este [guia](../../audiences/using/about-profiles-and-audiences.md).

![](assets/multivariant_push_1.png)

Para usar variantes de conteúdo multilíngue para a entrega de notificações por push, siga estas etapas:

* [Etapa 1: Carregar variante de conteúdo multilíngue](../../channels/using/creating-a-multilingual-push-notification.md#step-1--upload-multilingual-content-variant)
* [Etapa 2: Visualizar e finalizar uma notificação por push usando variantes de conteúdo multilíngue](../../channels/using/creating-a-multilingual-push-notification.md#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants)
* [Etapa 3: Enviar e analisar a entrega de notificação por push multilíngue](../../channels/using/creating-a-multilingual-push-notification.md#step-3--send-and-analyze-multilingual-push-notification-delivery)

## Etapa 1: Carregar variante de conteúdo multilíngue {#step-1--upload-multilingual-content-variant}

Antes de personalizar a notificação por push multilíngue, primeiro carregue as variantes de conteúdo em um modelo de entrega multilíngue e crie a entrega.

>[!NOTE]
>
>Você também pode ignorar esta etapa se quiser criar uma variante manualmente para cada variante de idioma.

1. No **[!UICONTROL Marketing activities]**, clique no **[!UICONTROL Create]** botão, em seguida, selecione **[!UICONTROL Push notification]**.
1. Selecione o modelo **[!UICONTROL Send multilingual push to Campaign profiles]** se desejar direcionar os perfis do Adobe Campaign que assinaram o aplicativo móvel ou o modelo **[!UICONTROL Send multilingual push to app subscriber]** para enviar uma notificação por push para todos os usuários que aceitaram receber notificações de seu aplicativo móvel.

   ![](assets/multivariant_push_2.png)

1. Insira suas propriedades de notificação por push e selecione seu aplicativo móvel no **[!UICONTROL Associate a Mobile App to a delivery]** campo.

   Observe que a lista suspensa exibirá aplicativos SDK V 4 e Adobe Experience Platform sdks.

1. Nas **[!UICONTROL Audiences]** janelas, arraste e solte consultas para ajustar o público.

   As consultas adicionadas dependem do modelo escolhido: se você escolher o **[!UICONTROL Send multilingual push to Campaign profiles]** modelo, poderá consultar destinatários conhecidos do seu aplicativo móvel. Se você escolher o **[!UICONTROL Send multilingual push to app subscriber]** modelo, poderá consultar todos os assinantes de um aplicativo específico que tenha aceitado.

   ![](assets/push_notif_audience.png)

1. Na **[!UICONTROL Manage Content Variants]** janela, arraste e solte seu arquivo ou selecione um arquivo do seu computador.

   O arquivo deve ser codificado UTF 8 e ter um layout específico que pode ser encontrado clicando na **[!UICONTROL Download the sample file]** opção. Você também deve usar a sintaxe apropriada para valores de localidade. Para obter mais informações sobre o formato de arquivo e as localidades compatíveis, consulte esta [technote](http://helpx.adobe.com/campaign/kb/acs-generate-csv-multilingual-push.html).

   ![](assets/multivariant_push_4.png)

1. Após carregar o arquivo, as variantes de idioma são automaticamente preenchidas na **[!UICONTROL Variants]** guia. Observe que você pode fornecer um **[!UICONTROL Default variant]** arquivo que será a variante de conteúdo padrão se nenhum idioma preferencial for especificado para o usuário direcionado.

   ![](assets/multivariant_push_5.png)

1. A **[!UICONTROL Variant selection]** guia fornecerá um script para determinar qual preferência de idioma deve ser levada em conta, dependendo do modelo de entrega. Esse script não requer alterações.
1. Se quiser adicionar mais variantes não presentes no arquivo importado, você pode fazê-lo clicando no **[!UICONTROL Add an element]** botão e adicionando quantas variantes de idioma novas forem necessárias.

   Ao adicionar variantes diferentes daqueles carregados do arquivo, nenhum conteúdo será vinculado a esse idioma. Você precisará editar o conteúdo diretamente no painel de entrega.

   ![](assets/multivariant_push_6.png)

1. Clique **[!UICONTROL Create]** em quando a configuração é feita. Você sempre pode retornar à **[!UICONTROL Content variant]** janela e fazer algumas alterações no painel de entrega.

   ![](assets/multivariant_push_8.png)

Agora você pode começar a personalizar a notificação por push multilíngue.

## Etapa 2: Visualizar e finalizar uma notificação por push usando variantes de conteúdo multilíngue {#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants}

Após carregar o arquivo que contém variantes de conteúdo, agora é possível visualizar as diferentes variantes da entrega de notificações por push.

Também é possível criar e editar mais variantes além das carregadas do arquivo.

1. Na **[!UICONTROL Content]** janela do painel de entrega, o menu suspenso permite visualizar o conteúdo de notificação por push, dependendo do idioma escolhido.

   ![](assets/multivariant_push_7.png)

1. Se uma variante de conteúdo não for especificada para um idioma específico, clique no ícone de sintoma abaixo da visualização para começar a adicionar o conteúdo a essa variante de idioma.

   Ao clicar na **[!UICONTROL Content]** janela, a notificação por push representa o conteúdo do idioma selecionado no menu suspenso. As alterações feitas nesta janela afetarão apenas um idioma.

1. Você também pode clicar em uma variante de conteúdo para personalizá-la ainda mais, por exemplo, com campos de personalização.

   Para obter mais informações sobre como personalizar a notificação por push, consulte esta [seção](../../channels/using/customizing-a-push-notification.md).

   ![](assets/multivariant_push_9.png)

1. Clique na **[!UICONTROL Content variant]** janela se desejar adicionar ou excluir variantes de idioma.

   Observe que ao adicionar um novo idioma, é necessário adicionar manualmente o conteúdo à notificação por push vinculada ao idioma adicionado.

   ![](assets/multivariant_push_10.png)

Sua entrega de notificação por push multilíngue está pronta para ser enviada.

## Etapa 3: Enviar e analisar a entrega de notificação por push multilíngue {#step-3--send-and-analyze-multilingual-push-notification-delivery}

Suas notificações por push de variante multilíngues estão prontas para serem enviadas aos usuários.

1. Para começar a preparar o envio, clique no **[!UICONTROL Prepare]** botão.
1. Quando a preparação for concluída sem avisos, você poderá clicar no **[!UICONTROL Confirm]** botão para começar a enviar seu push multilíngue.

   ![](assets/multivariant_push_12.png)

1. Depois de enviar a notificação por push com êxito, clique no **[!UICONTROL Reports]** ícone em seguida **[!UICONTROL Dynamic reports]** para analisar o sucesso da entrega.

   ![](assets/multivariant_push_13.png)

1. Selecione **[!UICONTROL Push notification report]**.
1. Arraste e solte a **[!UICONTROL Variant]** dimensão em seu painel para começar a filtrar seus dados.

   ![](assets/multivariant_push_11.png)

Agora você pode medir o impacto da entrega de notificação por push multilíngue nos seus destinatários.

**Tópicos relacionados:**

* [Relatório de notificação por push](../../reporting/using/push-notification-report.md)
* [Envio de uma notificação por push em um fluxo de trabalho](../../automating/using/push-notification-delivery.md)
* [Obtenção de públicos-alvo multilíngues usando um fluxo de trabalho](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Engageyourcustomersateverystep)
