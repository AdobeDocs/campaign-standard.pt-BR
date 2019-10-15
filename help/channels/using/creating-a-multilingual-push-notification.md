---
title: Criação de uma notificação por push multilíngue
seo-title: Criação de uma notificação por push multilíngue
description: Criação de uma notificação por push multilíngue
seo-description: Crie notificações por push multilíngues para direcionar seus usuários em seus idiomas e regiões preferidos.
page-status-flag: nunca ativado
uuid: d4aff741-e969-47c6-bae8-787c6c673191
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: canais
content-type: referência
topic-tags: notificações por push
discoiquuid: f9bb2235-d388-4025-9ace-734beb0c1961
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 650be2faa35d7e6d1279c952e1207a995c3297c5

---


# Criação de uma notificação por push multilíngue{#creating-a-multilingual-push-notification}

## Sobre a notificação por push multilíngue {#about-multilingual-push-notification}

Personalize seu conteúdo de notificação por push enviando mensagens com base nos idiomas e regiões preferidos de seus usuários. É possível importar diretamente variantes de conteúdo de notificação por push multilíngues no editor de conteúdo e enviar uma notificação por push multilíngue em uma única entrega.

Esse recurso utiliza os idiomas preferenciais especificados nos perfis dos destinatários ou a preferência de idioma do sistema para assinantes de aplicativos móveis, dependendo do modelo de entrega usado para a notificação por push. Se a preferência de idioma não for preenchida para um determinado usuário, o sistema usará a variante padrão definida ao criar uma notificação por push multilíngue. Para obter mais informações sobre como gerenciar seus perfis e assinantes, consulte este [guia](../../audiences/using/about-profiles-and-audiences.md).

![](assets/multivariant_push_1.png)

Para usar variantes de conteúdo multilíngues para a entrega da notificação por push, siga estas etapas:

* [Etapa 1: Carregar variante de conteúdo multilíngue](../../channels/using/creating-a-multilingual-push-notification.md#step-1--upload-multilingual-content-variant)
* [Etapa 2: Visualizar e finalizar uma notificação por push usando variantes de conteúdo multilíngue](../../channels/using/creating-a-multilingual-push-notification.md#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants)
* [Etapa 3: Enviar e analisar a entrega de notificações por push multilíngues](../../channels/using/creating-a-multilingual-push-notification.md#step-3--send-and-analyze-multilingual-push-notification-delivery)

## Etapa 1: Carregar variante de conteúdo multilíngue {#step-1--upload-multilingual-content-variant}

Antes de personalizar sua notificação por push multilíngue, primeiro precisamos carregar as variantes de conteúdo em um modelo de entrega multilíngue e criar a entrega.

>[!NOTE]
>
>Você também pode ignorar essa etapa se quiser criar uma variante manualmente para cada variante de idioma.

1. No **[!UICONTROL Marketing activities]**, clique no **[!UICONTROL Create]** botão e selecione **[!UICONTROL Push notification]**.
1. Selecione o modelo **[!UICONTROL Send multilingual push to Campaign profiles]** se desejar direcionar os perfis do Adobe Campaign que se inscreveram no aplicativo móvel ou no modelo **[!UICONTROL Send multilingual push to app subscriber]** para enviar uma notificação por push a todos os usuários que aceitaram receber notificações do aplicativo móvel.

   ![](assets/multivariant_push_2.png)

1. Digite as propriedades de notificação por push e selecione o aplicativo móvel no **[!UICONTROL Associate a Mobile App to a delivery]** campo.

   Observe que o menu suspenso exibirá os aplicativos SDK V4 e SDKs da plataforma Adobe Experience.

1. Nas **[!UICONTROL Audiences]** janelas, arraste e solte consultas para ajustar seu público-alvo.

   As consultas adicionadas dependem do modelo escolhido: se você escolher o **[!UICONTROL Send multilingual push to Campaign profiles]** modelo, poderá consultar destinatários conhecidos do seu aplicativo móvel. Enquanto que se você escolher o **[!UICONTROL Send multilingual push to app subscriber]** modelo, poderá consultar todos os assinantes de um aplicativo específico que aceitaram.
   >[!NOTE]
   >
   >Se você direcionar públicos-alvo com idiomas específicos, será necessário listar cada idioma direcionado no arquivo CSV.

   ![](assets/push_notif_audience.png)

1. Na **[!UICONTROL Manage Content Variants]** janela, arraste e solte o arquivo ou selecione um arquivo do computador.

   O arquivo deve ser codificado em UTF8 e ter um layout específico que pode ser encontrado clicando na **[!UICONTROL Download the sample file]** opção. Você também deve usar a sintaxe apropriada para valores de localidade. Para obter mais informações sobre o formato de arquivo e as localidades compatíveis, consulte esta [nota técnica](http://helpx.adobe.com/campaign/kb/acs-generate-csv-multilingual-push.html).

   ![](assets/multivariant_push_4.png)

1. Após carregar o arquivo, as variantes de idioma são automaticamente preenchidas na **[!UICONTROL Variants]** guia. Observe que você pode fornecer uma variável de conteúdo padrão **[!UICONTROL Default variant]** no arquivo se nenhum idioma preferencial for especificado para o usuário direcionado.

   ![](assets/multivariant_push_5.png)

1. A **[!UICONTROL Variant selection]** guia fornecerá um script para determinar a preferência de idioma a ser considerada, dependendo do modelo de entrega. Este é um script predefinido que não requer alterações.
1. Se quiser adicionar mais variantes não presentes no arquivo importado, clique no botão e adicione quantas novas variantes de idioma forem necessárias. **[!UICONTROL Add an element]**

   Ao adicionar variantes diferentes daquelas carregadas do arquivo, nenhum conteúdo será vinculado a esse idioma. Será necessário editar o conteúdo diretamente no painel de entrega.

   ![](assets/multivariant_push_6.png)

1. Clique **[!UICONTROL Create]** quando a configuração estiver concluída. Você sempre pode voltar para a **[!UICONTROL Content variant]** janela e fazer algumas alterações no painel de entrega.

   ![](assets/multivariant_push_8.png)

Agora você pode começar a personalizar sua notificação por push multilíngue.

## Etapa 2: Visualizar e finalizar uma notificação por push usando variantes de conteúdo multilíngue {#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants}

Depois de carregar o arquivo que contém as variantes de conteúdo, agora é possível visualizar as diferentes variantes da entrega da notificação por push.

Também é possível criar e editar mais variantes além das que são carregadas do arquivo.

1. Na **[!UICONTROL Content]** janela do painel de entrega, a lista suspensa permite que você visualize o conteúdo da notificação por push, dependendo do idioma escolhido.

   ![](assets/multivariant_push_7.png)

1. Se uma variante de conteúdo não for especificada para um idioma específico, clique no ícone de sino abaixo da visualização para começar a adicionar conteúdo a essa variante de idioma.

   Ao clicar na **[!UICONTROL Content]** janela, a notificação por push representa o conteúdo do idioma selecionado na lista suspensa. As alterações feitas nesta janela afetarão apenas um idioma.

1. Você também pode clicar em uma variante de conteúdo para personalizá-la ainda mais, por exemplo, com campos de personalização.

   Para obter mais informações sobre como personalizar sua notificação por push, consulte esta [seção](../../channels/using/customizing-a-push-notification.md).

   ![](assets/multivariant_push_9.png)

1. Clique na **[!UICONTROL Content variant]** janela se desejar adicionar ou excluir variantes de idioma.

   Observe que ao adicionar um novo idioma, você terá que adicionar manualmente conteúdo à notificação por push vinculada ao idioma adicionado.

   ![](assets/multivariant_push_10.png)

Sua entrega de notificação por push multilíngue está pronta para ser enviada.

## Etapa 3: Enviar e analisar a entrega de notificações por push multilíngues {#step-3--send-and-analyze-multilingual-push-notification-delivery}

Suas notificações por push de variantes de conteúdo multilíngue estão prontas para serem enviadas aos usuários.

1. Para começar a preparar o envio, clique no **[!UICONTROL Prepare]** botão.
1. Quando a preparação estiver concluída sem avisos, clique no **[!UICONTROL Confirm]** botão para começar a enviar o seu push multilingue.

   ![](assets/multivariant_push_12.png)

1. Depois de enviar sua notificação por push com êxito, clique no **[!UICONTROL Reports]** ícone e **[!UICONTROL Dynamic reports]** para analisar o sucesso de sua entrega.

   ![](assets/multivariant_push_13.png)

1. Select **[!UICONTROL Push notification report]**.
1. Arraste e solte a **[!UICONTROL Variant]** dimensão no painel para começar a filtrar seus dados.

   ![](assets/multivariant_push_11.png)

Agora você pode medir o impacto da entrega de notificações por push multilíngues em seus destinatários.

**Tópicos relacionados:**

* [Relatório de notificação por push](../../reporting/using/push-notification-report.md)
* [Envio de uma notificação por push em um fluxo de trabalho](../../automating/using/push-notification-delivery.md)
* [Alcançar públicos multilíngues usando um fluxo de trabalho](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Engageyourcustomersateverystep)
