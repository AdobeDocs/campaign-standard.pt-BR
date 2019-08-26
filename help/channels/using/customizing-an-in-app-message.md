---
title: Personalização de uma mensagem no aplicativo
seo-title: Personalização de uma mensagem no aplicativo
description: Personalização de uma mensagem no aplicativo
seo-description: Saiba como personalizar suas mensagens no aplicativo com várias opções.
page-status-flag: nunca ativado
uuid: 1 d 9 c 08 ed -4 de 5-440 d-bf 51-4 a 437 eec 67 d 5
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canais
content-type: reference
topic-tags: in-app-messaging
discoiquuid: c 9 c 3 e 033-e 319-447 b -8 d 87-ff 7 dd 4941876
context-tags: entrega, inappcontent, voltar
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 43183a3adc35da3dac807a888f1b694fbb9a623c

---


# Personalização de uma mensagem no aplicativo{#customizing-an-in-app-message}

Para ajustar a mensagem no aplicativo, o Adobe Campaign permite acessar um conjunto de opções avançadas durante a criação de um aplicativo.

O editor de conteúdo dentro do aplicativo permite escolher entre dois modos de mensagens no aplicativo:

* [Modelo de mensagem](../../channels/using/customizing-an-in-app-message.md#customizing-with-a-message-template): este modelo permite que você personalize totalmente o seu aplicativo com imagens ou vídeos e botões de ação.
* [Mensagem personalizada](../../channels/using/customizing-an-in-app-message.md#customizing-with-a-custom-html-message): este modelo permite importar HTML personalizado.

![](assets/inapp_customize_1.png)

**Tópicos relacionados:**

* [Enviar sua mensagem no aplicativo](../../channels/using/preparing-and-sending-an-in-app-message.md#sending-your-in-app-message)
* [Relatório no aplicativo](../../reporting/using/in-app-report.md)

## Personalização com um modelo de mensagem {#customizing-with-a-message-template}

### Layout {#layout}

O **[!UICONTROL Layout]** menu suspenso oferece quatro opções diferentes para escolher dependendo das suas necessidades de mensagens:

* **[!UICONTROL Full page]**: Esse tipo de layout cobre toda a tela de seus dispositivos de público-alvo.

   Suporta mídia (imagem, vídeo), texto e componentes de botão.

* **[!UICONTROL Large modal]**: Esse layout aparece em uma janela de estilo de alerta grande, enquanto seu aplicativo ainda está visível em segundo plano.

   Suporta mídia (imagem, vídeo), texto e componentes de botão.

* **[!UICONTROL Small modal]**: Esse layout aparece como uma pequena janela de tipo de alerta, seu aplicativo ainda está visível em segundo plano.

   Suporta mídia (imagem, vídeo), texto e componentes de botão.

* **[!UICONTROL Alert]**: Esse tipo de layout aparece como uma mensagem de alerta nativa do SO.

   Ele pode suportar apenas os componentes de texto e botão.

* **[!UICONTROL Local notification]**: Esse tipo de layout aparece como uma mensagem de banner.

   Ele só pode suportar som, texto e destino. Para obter mais informações sobre a notificação local, consulte [Personalizar um tipo de mensagem de notificação local](../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type).

Cada tipo de layouts pode ser visualizado em diferentes dispositivos como telefone, tablet, plataforma por exemplo Android ou iOS e orientação, por exemplo, paisagem ou retrato na janela direita do editor de conteúdo.

![](assets/inapp_customize_4.png)

### Mídia {#media}

O **[!UICONTROL Media]** menu suspenso permite adicionar mídia à mensagem no aplicativo para criar uma experiência atraente para o usuário final.

1. Selecione sua **[!UICONTROL Media Type]** imagem e vídeo.
1. Para o tipo **[!UICONTROL Image]** de mídia, digite o URL no **[!UICONTROL Media URL]** campo com base nos formatos suportados.

   Se necessário, também é possível inserir o caminho para um **[!UICONTROL Bundled image]** que pode ser usado se o dispositivo estiver offline.

   ![](assets/inapp_customize_5.png)

1. Para o tipo **[!UICONTROL Video]** de mídia, digite o URL no **[!UICONTROL Media URL]** campo.

   Em seguida, insira o seu **[!UICONTROL Video poster]** a ser usado enquanto o vídeo está baixando nos dispositivos do público-alvo ou até que os usuários toquem no botão de reprodução.

   ![](assets/inapp_customize_6.png)

### Texto {#text}

Se necessário, você também pode adicionar um título de mensagem e conteúdo à sua mensagem no aplicativo. Para personalizar melhor sua mensagem no aplicativo, você pode adicionar diferentes campos de personalização, blocos de conteúdo e texto dinâmico ao seu conteúdo.

1. No **[!UICONTROL Text]** menu suspenso, adicione um título no **[!UICONTROL Message title]** campo.

   ![](assets/inapp_customize_9.png)

1. Adicione seu conteúdo no **[!UICONTROL Message content]** campo.
1. Para personalizar ainda mais o texto, clique no ![](assets/edit_darkgrey-24px.png) ícone para adicionar campos de personalização.

   ![](assets/inapp_customize_8.png)

1. Digite o conteúdo da mensagem e adicione seus campos de personalização, se necessário.

   Para obter mais informações sobre o campo de personalização, consulte esta [seção](../../designing/using/inserting-a-personalization-field.md).

   ![](assets/inapp_customize_10.png)

1. Verifique o conteúdo da mensagem na janela de visualização.

   ![](assets/inapp_customize_11.png)

### Botões {#buttons}

Você pode adicionar até dois botões à mensagem no aplicativo.

1. No **[!UICONTROL Buttons]** menu suspenso, digite o texto do seu primeiro botão na **[!UICONTROL Primary]** categoria.

   ![](assets/inapp_customize_12.png)

1. Escolha qual das duas ações **[!UICONTROL Dismiss]** e **[!UICONTROL Redirect]** será atribuído ao seu botão primário.
1. Na **[!UICONTROL Secondary]** categoria, adicione um segundo botão ao seu aplicativo, se necessário, digitando o texto.
1. Selecione a ação associada ao segundo botão.
1. Se você escolher **[!UICONTROL Redirect]** a ação, digite o URL da Web ou o deep link no **[!UICONTROL Destination URL]** campo.

   ![](assets/inapp_customize_13.png)

1. Insira o URL da Web ou o deep link no **[!UICONTROL Destination URL]** campo, se você escolher a **[!UICONTROL Redirect]** ação,
1. Verifique o conteúdo da mensagem na janela de visualização ou clique no botão Visualizar.

   Consulte a [página de mensagens](../../channels/using/customizing-an-in-app-message.md#previewing-the-in-app-message) no aplicativo.

   ![](assets/inapp_customize_11.png)

### Configurações {#settings}

1. Na **[!UICONTROL Settings]** categoria, selecione a cor do plano de fundo entre claro e escuro.
1. Escolha exibir ou não um botão Fechar com a **[!UICONTROL Show close button]** opção de fornecer aos usuários uma maneira de recusar a mensagem no aplicativo.
1. Selecione se o alinhamento do botão será horizontal ou vertical com a **[!UICONTROL Button alignment]** opção.
1. Escolha se a mensagem no aplicativo pode ser fechada automaticamente ou não após alguns segundos.

   ![](assets/inapp_customize_7.png)

## Personalizar um tipo de mensagem de notificação local {#customizing-a-local-notification-message-type}

As notificações locais podem ser acionadas somente por um aplicativo em um determinado momento e dependendo de um evento. Eles alertarão os usuários a que algo está acontecendo em seu aplicativo mesmo sem ter acesso à Internet.

Para personalizar uma notificação local:

1. Na **[!UICONTROL Content]** página, selecione **[!UICONTROL Local notification]** na **[!UICONTROL Layout]** categoria

   ![](assets/inapp_customize_17.png)

1. Na **[!UICONTROL Text]** categoria, digite seu **[!UICONTROL Message title]** e **[!UICONTROL Message content]**.

   ![](assets/inapp_customize_18.png)

1. Na **[!UICONTROL Advanced option]** categoria, no **[!UICONTROL Wait to display]** campo, escolha por quanto tempo a notificação local será exibida na tela quando o evento for acionado.
1. No **[!UICONTROL Sound]** campo, insira o nome de arquivo do arquivo de som com a extensão, a ser reproduzido pelo dispositivo móvel quando a notificação local for recebida.

   O arquivo de som é reproduzido ao entregar a notificação se o arquivo estiver definido no pacote do aplicativo móvel. Caso contrário, o som padrão do dispositivo será reproduzido.

   ![](assets/inapp_customize_19.png)

1. Especifique um destino para redirecionar os usuários quando eles interagem com sua notificação local no **[!UICONTROL Deeplink URL]** campo.
1. Para transmitir dados personalizados na carga na forma de um par de valor chave, você pode adicionar campos personalizados à notificação local. Na **[!UICONTROL Custom fields]** categoria, clique no **[!UICONTROL Create an element]** botão.
1. Digite o e **[!UICONTROL Keys]** - **[!UICONTROL Values]** mail associado a cada chave.

   Observe que a manipulação e a finalidade dos campos personalizados está totalmente no aplicativo móvel.

1. Na **[!UICONTROL Apple options]** categoria, preencha **[!UICONTROL Category]** os campos para adicionar uma ID de categoria para ações personalizadas, se disponível em seu aplicativo móvel da Apple.

## Personalização com uma mensagem HTML personalizada {#customizing-with-a-custom-html-message}

>[!NOTE]
>
>A mensagem HTML personalizada não suporta a personalização de conteúdo.

O **[!UICONTROL Custom message]** modo permite importar diretamente uma de sua mensagem HTML pré-configurada.

Para fazer isso, basta arrastar e soltar ou selecionar o arquivo do computador.

O arquivo deve ter um layout específico que pode ser encontrado clicando no **Download da opção de arquivo** de amostra.

![](assets/inapp_customize_16.png)

Você também pode encontrar uma lista de requisitos de HTML personalizados para uma importação bem-sucedida no Adobe Campaign.

![](assets/inapp_customize_3.png)

Após a importação do HTML, você pode encontrar uma visualização do arquivo em diferentes dispositivos na janela de visualização.

## Visualização da mensagem no aplicativo {#previewing-the-in-app-message}

Antes de enviar a mensagem no aplicativo, você pode testar com seus perfis de teste para verificar o que será visto pelo público-alvo quando eles receberem sua entrega.

1. Clique no **[!UICONTROL Preview]** botão.

   ![](assets/inapp_sending_2.png)

1. Clique no **[!UICONTROL Select a test profile]** botão e selecione um dos perfis de teste para começar a visualizar sua entrega. Para obter mais informações sobre perfis de teste, consulte esta [seção](../../sending/using/managing-test-profiles-and-sending-proofs.md).
1. Verifique a mensagem em dispositivos diferentes, como Android, telefones para iphone ou até mesmo tablets. Você também pode verificar se os campos de personalização estão recuperando os dados corretos.

   ![](assets/inapp_sending_3.png)

1. Agora você pode enviar sua mensagem e medir seu impacto com os relatórios de entrega. For more on reporting, refer to [this section](../../reporting/using/in-app-report.md).

