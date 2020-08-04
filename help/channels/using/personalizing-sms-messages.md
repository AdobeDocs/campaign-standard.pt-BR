---
title: Personalizar mensagens SMS
description: Descubra a especificidade das opções de transliteração ao personalizar mensagens SMS.
page-status-flag: never-activated
uuid: 123fe70c-c279-40a3-88b6-6bfb2453ec83
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: sms-messages
discoiquuid: 7c64785c-e3c2-4caa-a547-002990aae3f9
delivercontext-tags: deliveryCreation,wizard;delivery,smsContent,back;delivery,smsContent,back
internal: n
snippet: y
translation-type: ht
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e
workflow-type: ht
source-wordcount: '331'
ht-degree: 100%

---


# Personalizar mensagens SMS{#personalizing-sms-messages}

Os princípios para personalizar mensagens SMS são os mesmos válidos para [emails](../../designing/using/personalization.md#inserting-a-personalization-field). No entanto, você deve estar ciente das opções de transliteração, pois elas podem afetar a codificação e, portanto, o número de mensagens SMS que serão enviadas. Para obter mais informações, consulte a seção [Transliteração e comprimento do SMS](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration).

Aqui, usamos um exemplo de mensagem SMS contendo campos de personalização que, dependendo de a transliteração ter ou não sido selecionada, não gerarão o mesmo número de envios:

**Olá, &lt; FirstName > &lt; LastName >, novos produtos já estão disponíveis. Visite-nos e confira-os na loja!**

* Para um recipient chamado &quot;John Smith&quot;, como não existem caracteres especiais, o Adobe Campaign escolherá a codificação GSM, que autorizará até 160 caracteres por mensagem SMS. A mensagem será, portanto, enviada em uma única parte.
* Para um recipient chamado &quot;Raphaël Forêt&quot;, os caracteres &quot;ë&quot; e &quot;ê&quot; não podem ser codificados no GSM. Dependendo de a transliteração ter sido ativada ou não, o Adobe Campaign poderá selecionar entre dois comportamentos:

   * Se a transliteração for autorizada, as letras &quot;ë&quot; e &quot;ê&quot; serão substituídas por &quot;e&quot;, o que significa que a codificação GSM pode ser usada e, portanto, até 160 caracteres podem ser usados no SMS. Essa mensagem será enviada como uma única mensagem SMS, mas será ligeiramente alterada.
   * Se a transliteração não estiver autorizada, o Adobe Campaign escolherá enviar a mensagem em formato binário (Unicode): portanto, todos os caracteres serão enviados como estão. Como as mensagens SMS em Unicode são limitadas a 70 caracteres, o Adobe Campaign terá que enviar a mensagem em duas partes.

>[!NOTE]
>
>O algoritmo que escolhe automaticamente a melhor codificação é executado independentemente para cada mensagem, caso a caso. Dessa forma, somente as mensagens personalizadas que exigirem codificação Unicode serão enviadas em Unicode. Todas as outras usarão a codificação GSM.

## Remetente do SMS {#sms-sender}

Você pode personalizar o nome do remetente do SMS. Para obter mais informações, consulte a seção [Configuração de SMS](../../administration/using/configuring-sms-channel.md#configuring-sms-properties).
