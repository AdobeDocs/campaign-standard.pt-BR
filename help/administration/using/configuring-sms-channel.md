---
title: Configuração de canal SMS
seo-title: Configuração de canal SMS
description: Configuração de canal SMS
seo-description: '" Descubra as etapas de configuração do SMS: roteamento, codificação, formatos e propriedades avançadas. "'
page-status-flag: nunca ativado
uuid: 5 f 13 dbd 5-9522-4199-8 d 9 a -44 c 397 cb 2458
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuração-canais
discoiquuid: 356 d 4 d 4 f -3 d 5 a -468 c-bff 8-96767 cd 8 fff 6
context-tags: Extaccountmobile, visão geral; Extaccount, main; entrega, smscontent, voltar
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 866567d63dd2798eb56d42d4e163e5484c9b4d68

---


# Configuring SMS channel{#configuring-sms-channel}

To send SMS messages, one or several external accounts must be configured by an administrator under the **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL SMS]** &gt; **[!UICONTROL SMS accounts]** menu.

The steps for creating and modifying an external account are detailed in the [External accounts](../../administration/using/external-accounts.md) section. Você encontrará abaixo dos parâmetros específicos de contas externas para enviar mensagens SMS.

## Defining an SMS Routing {#defining-an-sms-routing}

The external account **[!UICONTROL SMS routing via SMPP]** is provided by default, but it can be useful to add other accounts.

Se você quiser usar o protocolo SMPP, também poderá criar uma nova conta externa. For more information on SMS protocol and settings, refer to this [technical note](https://helpx.adobe.com/campaign/kb/sms-connector-protocol-and-settings.html).

1. Create a new external account from **[!UICONTROL Administration > Application settings > External accounts]**.
1. Define the account type as **[!UICONTROL Routing]**, the channel as **[!UICONTROL Mobile (SMS)]** and the delivery mode as **[!UICONTROL Bulk delivery]**.

   Once these routing parameters have been defined, the SMS connector ( **[!UICONTROL Generic SMPP]** ) is selected automatically. Esse conector permite que o Adobe Campaign envie mensagens SMS diretamente para os perfis direcionados, conectando-se a um centro de serviço de mensagens curtas (SMS-C) pelo protocolo SMPP.

   ![](assets/sms_routing.png)

1. Defina as configurações de conexão.

   Para inserir as definições de conexão específicas ao envio de mensagens SMS, entre em contato com seu provedor de serviços SMS, que será explicado como preencher os diferentes campos de conta externos.

   ![](assets/sms_connection.png)

   The **[!UICONTROL Enable TLS over SMPP]** option allows you to encrypt SMPP traffic.

   **[!UICONTROL Enable verbose SMPP traces in the log file]** permite que você despeje todo o tráfego SMPP em arquivos de log. Essa opção deve ser habilitada para resolver o conector e comparar com o tráfego visto pelo provedor.

1. Contact Adobe who will give you the value to enter into the **[!UICONTROL SMS-C implementation name]** field, depending on the provider chosen.
1. Defina as configurações do canal SMPP. You can learn more in the [SMS encoding and formats](../../administration/using/configuring-sms-channel.md#sms-encoding-and-formats) section.

   Enable the **[!UICONTROL Store incoming MO in the database]** if you want all incoming SMS to be stored in the inSMS table. For more information on how to retrieve your incoming SMS, refer to this [section](../../channels/using/managing-incoming-sms.md#storing-incoming-sms).

   The **[!UICONTROL Enable Real-time KPI updates during SR processing]** option allows the **[!UICONTROL Delivered]** or **[!UICONTROL Bounces + Errors]** KPIs to be updated in real time after sending your delivery. These KPIs can be found in the **[!UICONTROL Deployment]** window and are directly recalculated from the SR (Status Report) received from the provider.

   ![](assets/sms_connection_1.png)

1. Define the **[!UICONTROL Throughput and timeouts]** parameters.

   É possível especificar o número máximo de mensagens de saída ("MT", Mobile Terminated) em MT por segundo. Se você inserir "0" no campo correspondente, o resultado será ilimitado.

   Os valores de todos os campos correspondentes a durações precisam ser concluídos em segundos.

1. Defina os parâmetros específicos do SMS-C caso precise definir um mapeamento de codificação específico. For more information, refer to the [SMSC specifics](../../administration/using/configuring-sms-channel.md#smsc-specifics) section.

   Enable the **[!UICONTROL Send full phone number (send characters other than digits)]** option if you don't want to respect the SMPP protocol and transfer the **[!UICONTROL +]** prefix to the server of the SMS provider (SMS-C).

   However, given that certain providers require the use of the **[!UICONTROL +]** prefix, it is advised that you check with your provider and they will suggest that you enable this option if necessary.

1. Se necessário, defina respostas automáticas para acionar ações com base no conteúdo de uma resposta. For more on this, refer to [this section](../../channels/using/managing-incoming-sms.md#managing-stop-sms).
1. Salve a configuração da conta externo de roteamento de SMS.

Agora você pode usar seu novo roteamento para enviar mensagens SMS com o Adobe Campaign.

## SMS encoding and formats {#sms-encoding-and-formats}

### SMS encoding, length and transliteration {#sms-encoding--length-and-transliteration}

Por padrão, o número de caracteres em um SMS atende aos padrões GSM (Global System for Mobile Communications).

Mensagens SMS usando codificação GSM estão limitadas a 160 caracteres, ou 153 caracteres por SMS para mensagens enviadas em várias partes.

>[!NOTE]
>
>Determinados caracteres contam como duas (chaves, colchetes, o símbolo de euro etc.). The list of available GSM characters is presented in the [Table of characters - GSM Standard](../../administration/using/configuring-sms-channel.md#table-of-characters---gsm-standard) section.

Se desejar, você pode autorizar a transliteração de caracteres marcando a caixa correspondente.

![](assets/sms_transliteration.png)

A transliteração consiste em substituir um caractere de um SMS por outro quando esse caractere não é considerado pelo padrão GSM.

* If transliteration is **authorized**, each character that is not taken into account is replaced by a GSM character when the message is sent. Por exemplo, a letra "ë" é substituída por "e". Portanto, a mensagem é ligeiramente alterada, mas o limite de caracteres permanecerá a mesma.
* When transliteration is **not authorized**, each message that contains characters that are not taken into account is sent in binary format (Unicode): all of the characters are therefore sent as they are. No entanto, as mensagens SMS usando Unicode são limitadas a 70 caracteres (ou 67 caracteres por SMS para mensagens enviadas em várias partes). Se o número máximo de caracteres for excedido, várias mensagens serão enviadas, o que pode criar custos adicionais.

>[!CAUTION]
>
>Inserir campos de personalização no conteúdo de sua mensagem SMS pode inserir caracteres que não são considerados pela codificação GSM. A content example is offered in the [Personalizing SMS messages](../../channels/using/personalizing-sms-messages.md) section.

Por padrão, a transliteração de caracteres está desativada. Se desejar que todos os caracteres nas mensagens SMS sejam mantidos como estão, para que não altere nomes adequados, recomendamos que você não ative esta opção.

No entanto, se suas mensagens SMS contiverem muitos caracteres que geram mensagens Unicode, você poderá optar por ativar essa opção para limitar os custos de envio de suas mensagens.

### Table of characters - GSM Standard {#table-of-characters---gsm-standard}

Esta seção apresenta os caracteres considerados pelo padrão GSM. Todos os caracteres inseridos no corpo da mensagem, exceto os mencionados abaixo, convertem toda a mensagem em formato binário (Unicode) e, portanto, limite a 70 caracteres. For more on this, refer to the [SMS encoding, length and transliteration](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) section.

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

SP: Espaço

ESC: Esc

LF: Feed de linha

CR: Retorno de carro

**Caracteres avançados (contados duas vezes)**

^ { } [ ~ ] | €

### SMSC specifics {#smsc-specifics}

>[!NOTE]
>
>Essas opções permitem adaptar o conector para trabalhar com SMSC não padrão (ou seja, não seguindo exatamente a especificação SMPP 3.4) ou requisitos específicos de codificação e devem ser configurados apenas pelos usuários avançados.

Ao enviar uma mensagem SMS, o Adobe Campaign pode usar uma ou várias codificações de texto. Cada codificação possui seu próprio conjunto de caracteres específico e determina o número de caracteres que se encaixam em uma mensagem SMS.

**[!UICONTROL DATA_CODING]** O campo permite que o Adobe Campaign se comunique com o SMS-C, que é usado por codificação.

>[!NOTE]
>
>The mapping between the **data_coding** value and the encoding actually used is standardized. Nevertheless, certain SMS-C have their own specific mapping: in this case, your **Adobe Campaign** administrator needs to declare this mapping. Verifique com seu provedor para descobrir mais.

The **[!UICONTROL Define a specific mapping of encodings]** functionality allows you to declare **data_codings** and to force the encoding if necessary: to do this, specify a single encoding in the table.

**Configuração**

* When the **[!UICONTROL Define a specific mapping of encodings]** functionality is not checked, the connector takes on a generic behavior:

   * It will try to use GSM encoding to which it assigns the value **data_coding = 0**.
   * If GSM encoding fails, it will use **UCS2** encoding to which it assigns the value **data_coding = 8**.
   ![](assets/sms_data_coding.png)

* When the **[!UICONTROL Define a specific mapping of encodings]** functionality is checked, you can define the encodings that you would like to use as well as the linked **[!UICONTROL data_coding]** field values. O Adobe Campaign tentará usar a primeira codificação na lista e o seguinte, se a primeira codificação não for obrigatória.

   The order of declaration is important: it is recommended that you put the list in ascending order **of cost** in order to favor the encodings allowing you to fit as many characters as possible in each SMS message.

   Declare apenas as codificações que deseja usar. Se algumas codificações fornecidas pelo SMS-C não corresponderem à sua finalidade de uso, não as declare na lista.

   ![](assets/sms_data_coding1.png)

### Automatic reply sent to the MO {#automatic-reply-sent-to-the-mo}

Quando um perfil responde a uma mensagem SMS enviada por meio da Campanha, é possível configurar mensagens que são enviadas automaticamente para ele, bem como a ação a ser executada.

For more information, refer to [this section](../../channels/using/managing-incoming-sms.md).

## Configuring SMS properties {#configuring-sms-properties}

Esta seção detalha a lista de parâmetros exclusivos do SMS na tela de propriedades de uma entrega SMS ou de um modelo SMS.

The specific parameters for sending SMS messages are regrouped in the **[!UICONTROL Send]** and in the **[!UICONTROL Advanced parameters]** sections.

![](assets/sms_options.png)

* The **[!UICONTROL From]** option allows you to personalize the name of the SMS message sender using a string of characters. Esse é o nome que aparecerá como o nome do remetente da mensagem SMS no telefone móvel do destinatário.

   Se esse campo estiver vazio, será o número de origem fornecido na conta externa que será usada. Se nenhum número de fonte for fornecido, será o código curto que será usado. The external account specific to SMS delivery is presented in the [External SMS account](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing) section.

   ![](assets/sms_smpp.png)

   >[!CAUTION]
   >
   >Verifique a legislação em seu país sobre a modificação do endereço do remetente. Você também deve verificar com seu provedor de serviço SMS para ver se eles oferecem essa funcionalidade.

* The **[!UICONTROL Maximum number of SMS per message]** option allows you to define the number of SMS messages to use to send a message. Se esse número for excedido, a mensagem não será enviada.

   >[!CAUTION]
   >
   >Se você tiver inserido campos de personalização ou texto condicional no conteúdo de sua mensagem SMS, o comprimento da mensagem e, como resultado, o número de mensagens SMS a serem enviadas poderão variar de um destinatário para outro. For more on this, refer to the [Personalizing SMS messages](../../channels/using/personalizing-sms-messages.md) section.

* **[!UICONTROL Transmission mode]** O campo permite que você determine o método de entrega para mensagens SMS:

   * **[!UICONTROL Saved on SIM card]**: a mensagem é armazenada no cartão YES do destinatário do destinatário.
   * **[!UICONTROL Saved on mobile]**: a mensagem é armazenada na memória interna do telefone.
   * **[!UICONTROL Flash]**: a mensagem é exibida no telefone móvel do destinatário como uma notificação e desaparece sem ser salva.

