---
title: Personalização de mensagens SMS
seo-title: Personalização de mensagens SMS
description: Personalização de mensagens SMS
seo-description: Descubra a especificidade das opções de transliteração ao personalizar mensagens SMS.
page-status-flag: nunca ativado
uuid: 123 fe 70 c-c 279-40 a 3-88 b 6-6 bfb 2453 ec 83
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canais
content-type: reference
topic-tags: sms-messages
discoiquuid: 7 c 64785 c-e 3 c 2-4 caa-a 547-002990 aae 3 f 9
delivercontext-tags: Deliverycreation, assistente; entrega, smscontent, back; entrega, smscontent, voltar
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b0cf437ec97153b53bd4502171b24286abb25731

---


# Personalizing SMS messages{#personalizing-sms-messages}

The principles for personalizing SMS messages are the same as those for [emails](../../designing/using/inserting-a-personalization-field.md). Você deve, contudo, estar ciente das opções de transliteração, pois elas podem afetar a codificação e, portanto, o número de mensagens SMS a serem enviadas. For more on this, refer to the [Transliteration and SMS length](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) section.

Aqui, tomamos uma amostra de mensagem SMS contendo campos de personalização que, dependendo da transliteração ter sido selecionada ou não, não gerarão o mesmo número de envios:

**Ei &lt; firstname &gt; &lt; lastname &gt;, novos produtos agora disponíveis. Come and check them out in store!**

* Para um destinatário chamado'John Smith ', como não contém caracteres especiais, o Adobe Campaign escolherá a codificação GSM que autorizará até 160 caracteres por mensagem SMS. A mensagem será enviada em uma única parte.
* Para um destinatário chamado "Raphaël Forêt", os caracteres "ë" e "od" não podem ser codificados em GSM. Se a transliteração tiver sido habilitada ou não, o Adobe Campaign poderá selecionar entre dois comportamentos:

   * Se a transliteração for autorizada,' ë'e'od'serão substituídas por'e ', o que significa que a codificação GSM pode ser usada e, portanto, até 160 caracteres podem ser usados no SMS. Esta mensagem será enviada como uma única mensagem SMS, mas será ligeiramente alterada.
   * Se a transliteração não estiver autorizada, o Adobe Campaign escolherá enviar a mensagem em formato binário (Unicode): todos os caracteres serão enviados assim. Como as mensagens SMS em Unicode estão limitadas a 70 caracteres, o Adobe Campaign precisa enviar a mensagem em duas partes.

>[!NOTE]
>
>O algoritmo que escolhe automaticamente a melhor codificação é executado independentemente para cada mensagem, caso a caso. Dessa forma, apenas as mensagens personalizadas que exigem codificação Unicode serão enviadas em Unicode; todos os outros usarão a codificação GSM.

