---
title: Personalizar mensagens SMS
description: Descubra a especificidade das opções de transliteração ao personalizar mensagens SMS.
page-status-flag: nunca ativado
uuid: 123fe70c-c279-40a3-88b6-6bfb2453ec83
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: canais
content-type: referência
topic-tags: sms-messages
discoiquuid: 7c64785c-e3c2-4caa-a547-002990aae3f9
delivercontext-tags: delivery,assistente;delivery,smsContent,back;delivery,smsContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Personalizar mensagens SMS{#personalizing-sms-messages}

Os princípios para personalizar mensagens SMS são os mesmos que para [emails](../../designing/using/personalization.md#inserting-a-personalization-field). No entanto, devem estar cientes das opções de transliteração, uma vez que estas podem afetar a codificação e, por conseguinte, o número de mensagens SMS a enviar. Para obter mais informações, consulte a seção [Transliteração e comprimento](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) do SMS.

Aqui, pegamos uma amostra de mensagem SMS contendo campos de personalização que, dependendo se a transliteração foi selecionada, não gerará o mesmo número de envios:

**Ei &lt; FirstName &gt; &lt; LastName &gt;, novos produtos agora estão disponíveis. Venha ver eles na loja!**

* Para um destinatário chamado 'John Smith', como não contém caracteres especiais, o Adobe Campaign escolherá a codificação GSM que autorizará até 160 caracteres por mensagem SMS. Por conseguinte, a mensagem será enviada numa única parte.
* Para um destinatário chamado "Raphaël Forêt", os caracteres "ë" e "ê" não podem ser codificados no GSM. Dependendo de a transliteração ter sido ativada ou não, o Adobe Campaign pode selecionar entre dois comportamentos:

   * Se a transliteração for autorizada, as palavras "ë" e "ê" serão substituídas por "e", o que significa que a codificação GSM pode ser usada e, portanto, até 160 caracteres podem ser usados no SMS. Esta mensagem será enviada como uma única mensagem SMS, mas será ligeiramente alterada.
   * Se a transliteração não estiver autorizada, o Adobe Campaign escolherá enviar a mensagem em formato binário (Unicode): todos os caracteres serão, portanto, enviados como tal. Como as mensagens SMS em Unicode são limitadas a 70 caracteres, o Adobe Campaign terá que enviar a mensagem em duas partes.

>[!NOTE]
>
>O algoritmo que escolhe automaticamente a melhor codificação é executado independentemente para cada mensagem, caso a caso. Dessa forma, somente as mensagens personalizadas que exigem codificação Unicode serão enviadas em Unicode; todos os outros usarão a codificação GSM.

## Remetente SMS {#sms-sender}

Você pode personalizar o nome do remetente do SMS. For more on this, refer to the [SMS configuration](../../administration/using/configuring-sms-channel.md#configuring-sms-properties) section.
