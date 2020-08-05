---
title: Configuração do canal SMS
description: '“Descubra as etapas de configuração do SMS: roteamento, codificação, formatos e propriedades avançadas. "'
page-status-flag: never-activated
uuid: 5f13dbd5-9522-4199-8d9a-44c397cb2458
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 356d4d4f-3d5a-468c-bff8-96767cd8fff6
context-tags: extAccountMobile,overview;extAccount,main;delivery,smsContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 10339aa3a5d16bb995a763b6d846e234c5f1325a
workflow-type: tm+mt
source-wordcount: '1625'
ht-degree: 99%

---


# Configuração do canal SMS{#configuring-sms-channel}

Para enviar mensagens SMS, uma ou várias contas externas devem ser configuradas por um administrador no menu **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL SMS]** > **[!UICONTROL SMS accounts]**.

As etapas para criar e modificar uma conta externa são detalhadas na seção [Contas externas](../../administration/using/external-accounts.md). Você encontrará abaixo os parâmetros específicos das contas externas para enviar mensagens SMS.

## Definição de um roteamento SMS {#defining-an-sms-routing}

A conta externa **[!UICONTROL SMS routing via SMPP]** é fornecida por padrão, mas convém adicionar outras contas.

Se quiser usar o protocolo SMPP, você também poderá criar uma nova conta externa. Para saber mais sobre o protocolo e as configurações de SMS, consulte esta [nota técnica](https://helpx.adobe.com/br/campaign/kb/sms-connector-protocol-and-settings.html).

1. Crie uma nova conta externa em **[!UICONTROL Administration > Application settings > External accounts]**.
1. Defina o tipo de conta como **[!UICONTROL Routing]**, o canal como **[!UICONTROL Mobile (SMS)]** e o modo de delivery como **[!UICONTROL Bulk delivery]**.

   ![](assets/sms_routing.png)

1. Defina as configurações de conexão.

   Para inserir as configurações de conexão específicas ao envio de mensagens SMS, entre em contato com seu provedor de serviço SMS que explicará como preencher os diferentes campos de conta externa.

   ![](assets/sms_connection.png)

   A opção **[!UICONTROL Enable TLS over SMPP]** permite criptografar o tráfego SMPP.

   **[!UICONTROL Enable verbose SMPP traces in the log file]** permite despejar todo o tráfego SMPP em arquivos de log. Essa opção deve estar ativada para solucionar problemas no conector e fazer uma comparação com o tráfego visto pelo provedor.

1. Entre em contato com a Adobe, que fornecerá o valor a ser inserido no campo **[!UICONTROL SMS-C implementation name]**, dependendo do provedor escolhido.
1. Defina as configurações do canal SMPP. Você pode saber mais na seção [Codificação e formatos de SMS](#sms-encoding-and-formats).

   Ative a opção **[!UICONTROL Store incoming MO in the database]** se quiser que todo o SMS recebido seja armazenado na tabela inSMS. Para saber mais sobre como recuperar o SMS recebido, consulte esta [seção](../../channels/using/managing-incoming-sms.md#storing-incoming-sms).

   A opção **[!UICONTROL Enable Real-time KPI updates during SR processing]** permite que o KPI **[!UICONTROL Delivered]** ou **[!UICONTROL Bounces + Errors]** seja atualizado em tempo real após o envio do delivery. Esses KPIs podem ser encontrados na janela **[!UICONTROL Deployment]** e são recalculados diretamente do SR (relatório de status) recebido do provedor.

   ![](assets/sms_connection_1.png)

1. Defina os parâmetros de **[!UICONTROL Throughput and timeouts]**.

   Você pode especificar a taxa de transferência máxima das mensagens de saída (“MT”, Mobile Terminated) em MT por segundo. Se inserir &quot;0&quot; no campo correspondente, a taxa de transferência será ilimitada.

   Os valores de todos os campos correspondentes às durações precisam ser preenchidos em segundos.

1. Determine os parâmetros específicos do SMS-C caso precise definir um mapeamento de codificação específico. Para saber mais, consulte a seção [Especificações do SMSC](#smsc-specifics).

   Ative a opção **[!UICONTROL Send full phone number (send characters other than digits)]** se não quiser respeitar o protocolo SMPP e transfira o prefixo **[!UICONTROL +]** para o servidor do provedor de SMS (SMS-C).

   Contudo, considerando que alguns provedores exigem o uso do prefixo **[!UICONTROL +]**, recomenda-se consultar seu provedor para saber se essa opção deve ser ativada.

1. Se necessário, defina respostas automáticas para acionar ações com base no conteúdo de uma resposta. Para obter mais informações, consulte [esta seção](../../channels/using/managing-incoming-sms.md#managing-stop-sms).
1. Salve a configuração da conta externa do roteamento de SMS.

Agora você pode usar seu novo roteamento para enviar mensagens SMS com o Adobe Campaign.

## Codificação e formatos de SMS {#sms-encoding-and-formats}

### Codificação, comprimento e transliteração do SMS {#sms-encoding--length-and-transliteration}

Por padrão, o número de caracteres em um SMS atende aos padrões GSM (Global System for Mobile Communications).

As mensagens SMS que usam a codificação GSM são limitadas a 160 caracteres ou a 153 caracteres por SMS para as mensagens enviadas em várias partes.

>[!NOTE]
>
>Alguns caracteres contam como dois (chaves, colchetes, o símbolo do euro etc.). A lista de caracteres GSM disponíveis é apresentada na seção [Tabela de caracteres - padrão GSM](#table-of-characters---gsm-standard).

Você pode autorizar a transliteração de caracteres marcando a caixa correspondente.

![](assets/sms_transliteration.png)

A transliteração consiste em substituir um caractere de um SMS por outro quando esse caractere não é considerado pelo padrão GSM.

* Se a transliteração for **authorized**, cada caractere que não for levado em consideração será substituído por um caractere GSM quando a mensagem for enviada. Por exemplo, a letra &quot;ë&quot; é substituída por &quot;e&quot;. Portanto, a mensagem é ligeiramente alterada, mas o limite de caracteres permanecerá o mesmo.
* Quando a transliteração é **not authorized**, cada mensagem que contém caracteres que não são levados em consideração é enviada em formato binário (Unicode): todos os caracteres são enviados como estão. No entanto, as mensagens SMS usando Unicode são limitadas a 70 caracteres (ou 67 caracteres por SMS para mensagens enviadas em várias partes). Se o número máximo de caracteres for excedido, várias mensagens serão enviadas, o que pode ocasionar custos adicionais.

>[!IMPORTANT]
>
>A inserção de campos de personalização no conteúdo da mensagem SMS pode inserir caracteres que não são considerados pela codificação GSM. Um exemplo de conteúdo é apresentado na seção [Personalização de mensagens SMS](../../channels/using/personalizing-sms-messages.md).

Por padrão, a transliteração de caractere é desabilitada. Se você quiser que todos os caracteres em suas mensagens SMS sejam mantidos como estão, não altere nomes próprios, por exemplo, recomendamos que você não habilite essa opção.

No entanto, se as mensagens SMS contiverem muitos caracteres que geram mensagens Unicode, você poderá optar por habilitar essa opção para limitar os custos de envio de mensagens.

### Tabela de caracteres - padrão GSM {#table-of-characters---gsm-standard}

A tabela a seguir apresenta os caracteres considerados pelo padrão GSM. Todos os caracteres inseridos no corpo da mensagem, além dos mencionados abaixo, convertem toda a mensagem em formato binário (Unicode) e, portanto, a limita a 70 caracteres. Para saber mais, consulte a seção [Codificação, comprimento e transliteração do SMS](#sms-encoding--length-and-transliteration).

**Caracteres básicos**

<table> 
 <tbody> 
  <tr> 
   <td> @<br /> </td> 
   <td> <img height="21px" src="assets/delta.png" /> <br /> </td> 
   <td> SP<br /> </td> 
   <td> 0<br /> </td> 
   <td> ¡<br /> </td> 
   <td> P<br /> </td> 
   <td> ¿<br /> </td> 
   <td> P<br /> </td> 
  </tr> 
  <tr> 
   <td> £<br /> </td> 
   <td> _<br /> </td> 
   <td> !<br /> </td> 
   <td> 1<br /> </td> 
   <td> A<br /> </td> 
   <td> Q<br /> </td> 
   <td> a<br /> </td> 
   <td> q<br /> </td> 
  </tr> 
  <tr> 
   <td> $<br /> </td> 
   <td> <img height="21px" src="assets/phi.png" /> <br /> </td> 
   <td> "<br /> </td> 
   <td> 2<br /> </td> 
   <td> B<br /> </td> 
   <td> R<br /> </td> 
   <td> b<br /> </td> 
   <td> r<br /> </td> 
  </tr> 
  <tr> 
   <td> ¥<br /> </td> 
   <td> <img height="21px" src="assets/gamma.png" /> <br /> </td> 
   <td> #<br /> </td> 
   <td> 3<br /> </td> 
   <td> C<br /> </td> 
   <td> S<br /> </td> 
   <td> c<br /> </td> 
   <td> s<br /> </td> 
  </tr> 
  <tr> 
   <td> è<br /> </td> 
   <td> <img height="21px" src="assets/delta.png" /> <br /> </td> 
   <td> ¤<br /> </td> 
   <td> 4<br /> </td> 
   <td> D<br /> </td> 
   <td> T<br /> </td> 
   <td> d<br /> </td> 
   <td> t<br /> </td> 
  </tr> 
  <tr> 
   <td> é<br /> </td> 
   <td> <img height="21px" src="assets/omega.png" /> <br /> </td> 
   <td> %<br /> </td> 
   <td> 5<br /> </td> 
   <td> E<br /> </td> 
   <td> U<br /> </td> 
   <td> e<br /> </td> 
   <td> u<br /> </td> 
  </tr> 
  <tr> 
   <td> ù<br /> </td> 
   <td> <img height="21px" src="assets/pi.png" /> <br /> </td> 
   <td> &amp;<br /> </td> 
   <td> 6<br /> </td> 
   <td> F<br /> </td> 
   <td> V<br /> </td> 
   <td> f<br /> </td> 
   <td> v<br /> </td> 
  </tr> 
  <tr> 
   <td> ì<br /> </td> 
   <td> <img height="21px" src="assets/psi.png" /> <br /> </td> 
   <td> '<br /> </td> 
   <td> 7<br /> </td> 
   <td> G<br /> </td> 
   <td> W<br /> </td> 
   <td> g<br /> </td> 
   <td> w<br /> </td> 
  </tr> 
  <tr> 
   <td> ò<br /> </td> 
   <td> <img height="21px" src="assets/sigma.png" /> <br /> </td> 
   <td> (<br /> </td> 
   <td> 8<br /> </td> 
   <td> H<br /> </td> 
   <td> X<br /> </td> 
   <td> h<br /> </td> 
   <td> x<br /> </td> 
  </tr> 
  <tr> 
   <td> Ç<br /> </td> 
   <td> <img height="21px" src="assets/theta.png" /> <br /> </td> 
   <td> )<br /> </td> 
   <td> 9 </td> 
   <td> I<br /> </td> 
   <td> Y<br /> </td> 
   <td> i<br /> </td> 
   <td> y<br /> </td> 
  </tr> 
  <tr> 
   <td> LF<br /> </td> 
   <td> <img height="21px" src="assets/xi.png" /> <br /> </td> 
   <td> *<br /> </td> 
   <td> :<br /> </td> 
   <td> J<br /> </td> 
   <td> Z<br /> </td> 
   <td> j<br /> </td> 
   <td> z<br /> </td> 
  </tr> 
  <tr> 
   <td> Ø<br /> </td> 
   <td> ESC<br /> </td> 
   <td> +<br /> </td> 
   <td> ;<br /> </td> 
   <td> K<br /> </td> 
   <td> Ä<br /> </td> 
   <td> k<br /> </td> 
   <td> ä<br /> </td> 
  </tr> 
  <tr> 
   <td> ø<br /> </td> 
   <td> Æ<br /> </td> 
   <td> ,<br /> </td> 
   <td> &lt;<br /> </td> 
   <td> L<br /> </td> 
   <td> Ö<br /> </td> 
   <td> l<br /> </td> 
   <td> ö<br /> </td> 
  </tr> 
  <tr> 
   <td> CR<br /> </td> 
   <td> æ<br /> </td> 
   <td> -<br /> </td> 
   <td> = </td> 
   <td> M<br /> </td> 
   <td> Ñ<br /> </td> 
   <td> m<br /> </td> 
   <td> ñ<br /> </td> 
  </tr> 
  <tr> 
   <td> Å<br /> </td> 
   <td> ß<br /> </td> 
   <td> .<br /> </td> 
   <td> &gt;<br /> </td> 
   <td> N<br /> </td> 
   <td> Ü<br /> </td> 
   <td> n<br /> </td> 
   <td> ü<br /> </td> 
  </tr> 
  <tr> 
   <td> å<br /> </td> 
   <td> É<br /> </td> 
   <td> /<br /> </td> 
   <td> ?<br /> </td> 
   <td> O<br /> </td> 
   <td> §<br /> </td> 
   <td> o<br /> </td> 
   <td> à<br /> </td> 
  </tr> 
 </tbody> 
</table>

SP: espaço

ESC: escape

LF: alimentação de linha

CR: retorno

**Caracteres avançados (contados duas vezes)**

^ { } [ ~ ] | €

### Especificações do SMSC {#smsc-specifics}

>[!NOTE]
>
>Essas opções permitem adaptar o conector para funcionar com SMSC não padrão (isto é, sem seguir exatamente a especificação SMPP 3.4) ou requisitos específicos de codificação e só devem ser configuradas por usuários avançados.

Ao enviar uma mensagem SMS, o Adobe Campaign pode usar uma ou várias codificações de texto. Cada codificação tem seu próprio conjunto específico de caracteres e determina o número de caracteres que cabem em uma mensagem SMS.

O campo **[!UICONTROL DATA_CODING]** permite que o Adobe Campaign comunique com o SMS-C que a codificação é usada.

>[!NOTE]
>
>O mapeamento entre o valor **data_coding** e a codificação realmente usada é padronizado. No entanto, alguns SMS-C têm mapeamento específico. Nesse caso, o administrador do **Adobe Campaign** precisa declarar esse mapeamento. Consulte seu provedor para saber mais.

A funcionalidade **[!UICONTROL Define a specific mapping of encodings]** permite declarar **data_codings** e forçar a codificação, se necessário. Para isso, especifique uma única codificação na tabela.

**Configuração**

* Quando a funcionalidade **[!UICONTROL Define a specific mapping of encodings]** não estiver selecionada, o conector assume um comportamento genérico:

   * Ele tentará usar a codificação GSM para a qual atribui o valor **data_coding = 0**.
   * Se a codificação GSM falhar, ele usará a codificação **UCS2** para a qual atribui o valor **data_coding = 8**.

   ![](assets/sms_data_coding.png)

* Quando a funcionalidade **[!UICONTROL Define a specific mapping of encodings]** estiver marcada, você poderá definir as codificações que deseja usar, bem como os valores do campo **[!UICONTROL data_coding]** vinculados. O Adobe Campaign tentará usar a primeira codificação da lista, depois a seguinte se a primeira codificação for impossível.

   A ordem da declaração é importante: é recomendável colocar a lista em ordem crescente **de custo** para favorecer as codificações que permitem usar o máximo possível de caracteres em cada mensagem SMS.

   Apenas declare as codificações que deseja usar. Se algumas codificações fornecidas pelo SMS-C não corresponderem à sua finalidade de uso, não as declare na lista.

   ![](assets/sms_data_coding1.png)

### Resposta automática enviada ao MO {#automatic-reply-sent-to-the-mo}

Quando um perfil responde a uma mensagem SMS enviada pelo Campaign, você pode configurar mensagens que serão automaticamente enviadas para ele, bem como a ação a ser executada.

Para saber mais, consulte [esta seção](../../channels/using/managing-incoming-sms.md).

## Configuração das propriedades de SMS {#configuring-sms-properties}

Esta seção detalha a lista de parâmetros exclusivos ao SMS na tela de propriedades de um delivery ou de um template de SMS.

Os parâmetros específicos para envio de mensagens SMS são reagrupados nas seções **[!UICONTROL Send]** e **[!UICONTROL Advanced parameters]**.

![](assets/sms_options.png)

Na **[!UICONTROL Advanced parameters]** seção:

* A opção **[!UICONTROL From]** permite personalizar o nome do remetente da mensagem SMS usando uma sequência de caracteres. Ele aparecerá como o nome do remetente da mensagem SMS no celular do recipient.

   Se esse campo estiver vazio, será usado o número de origem fornecido na conta externa. Se nenhum número de origem for fornecido, o código curto será usado. A conta externa específica do delivery de SMS é apresentada na seção [Definição de um roteamento de SMS](#defining-an-sms-routing).

   ![](assets/sms_smpp_2.png)

   >[!IMPORTANT]
   >
   >Consulte a legislação do seu país quanto à modificação do endereço do remetente. Você também deve consultar seu provedor de serviço SMS se ele oferecer essa funcionalidade.

Na **[!UICONTROL Send]** seção de um modelo SMS:

* A opção **[!UICONTROL Maximum number of SMS per message]** permite definir o número de mensagens SMS a serem usadas para enviar uma mensagem. Se esse número for excedido, a mensagem não será enviada.

   >[!IMPORTANT]
   >
   >Se você tiver inserido campos de personalização ou texto condicional no conteúdo da mensagem SMS, o comprimento da mensagem e, consequentemente, o número de mensagens SMS a serem enviadas, poderão variar de um recipient para outro. Para saber mais, consulte a seção [Personalização de mensagens SMS](../../channels/using/personalizing-sms-messages.md).

   ![](assets/sms_smpp_3.png)

* O campo **[!UICONTROL Transmission mode]** permite determinar o método de delivery das mensagens SMS:

   * **[!UICONTROL Saved on SIM card]**: a mensagem é armazenada no cartão SIM do telefone do recipient.
   * **[!UICONTROL Saved on mobile]**: a mensagem é armazenada na memória interna do telefone.
   * **[!UICONTROL Flash]**: a mensagem é exibida no celular do recipient como uma notificação e depois desaparece sem ser salva.
