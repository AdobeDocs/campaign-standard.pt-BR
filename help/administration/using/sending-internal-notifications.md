---
title: Enviar notificações internas
seo-title: Enviar notificações internas
description: Enviar notificações internas
seo-description: Saiba como enviar notificações de sistema em tempo real aos usuários do Adobe Campaign.
page-status-flag: nunca ativado
uuid: f 196 f 025-dbb 9-4268-9 d 7 d-ff 626994 b 447
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: application-settings
discoiquuid: 4 d 51229 a -745 a -4 f 24-b 1 c 2-22 fa 203 b 499 c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6a877d878f01fa1e541dc20b8b0941602113d15b

---


# Sending internal notifications{#sending-internal-notifications}

O Adobe Campaign oferece a você a possibilidade de receber notificações relacionadas a atividades importantes do sistema diretamente no aplicativo. As notificações em tempo real mantêm os participantes informados e fornecem aos usuários a capacidade de agir imediatamente e diretamente em notificações de atividades dentro do aplicativo. O resultado para as equipes é agilidade avançada, eficiência e execução mais simplificada de campanhas.

![](assets/pulse_3.png)

Você pode configurar notificações para os seguintes objetos:

* **[!UICONTROL A/B Test emails]**: o criador e os modificadores de e-mail são notificados de que uma variante foi escolhida (modo automático) ou que uma variante precisa ser escolhida (modo manual). Clicar na notificação exibe o e-mail correspondente. As notificações são ativadas por padrão no modelo Teste A/B da caixa. If you want to deactivate them, edit the properties of the email or the email template and uncheck the box located under **General &gt; Notifications**. For more information on A/B Test emails, refer to [Creating an AB Test](../../channels/using/designing-an-a-b-test-email.md). For more on email properties, refer to [List of email properties](../../administration/using/configuring-email-channel.md#list-of-email-properties).

   ![](assets/pulse_2.png)

* **[!UICONTROL Workflows]**: cada membro do grupo de segurança selecionado é notificado (email e notificação no aplicativo) sempre que um fluxo de trabalho está em erro. Clicar na notificação ou no link de e-mail exibe o fluxo de trabalho correspondente. As notificações são desativadas por padrão no modelo de fluxo de trabalho predefinido. If you want to activate them, edit the properties of the workflow or workflow template and add a security group under **General &gt; Execution &gt; Error management &gt; Supervisors**. For more information on security groups, refer to [Managing groups and users](../../administration/using/managing-groups-and-users.md). For more on workflow properties, refer to [Workflow properties](../../automating/using/executing-a-workflow.md#workflow-properties).

   ![](assets/pulse_1.png)

