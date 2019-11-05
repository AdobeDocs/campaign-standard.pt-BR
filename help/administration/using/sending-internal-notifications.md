---
title: Enviar notificações internas
description: Saiba como enviar notificações do sistema em tempo real aos usuários do Adobe Campaign.
page-status-flag: nunca ativado
uuid: f196f025-dbb9-4268-9d7d-ff626994b447
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: administração
content-type: referência
topic-tags: application-settings
discoiquuid: 4d51229a-745a-4f24-b1c2-22fa203b499c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Enviar notificações internas{#sending-internal-notifications}

O Adobe Campaign oferece a você a possibilidade de receber notificações sobre atividades importantes do sistema diretamente no aplicativo.  As notificações em tempo real mantêm as partes interessadas relevantes informadas e fornecem aos usuários a capacidade de agir imediata e diretamente nas notificações de atividade dentro do aplicativo. O resultado para as equipes é agilidade avançada, eficiência e execução mais suave de campanhas.

![](assets/pulse_3.png)

Você pode configurar notificações para os seguintes objetos:

* **[!UICONTROL A/B Test emails]**: o criador e modificador(es) de e-mail são notificados de que uma variante foi escolhida (modo automático) ou que uma variante precisa ser escolhida (modo manual). Clicar na notificação exibe o email correspondente. As notificações são ativadas por padrão no modelo A/B pronto para uso. Se desejar desativá-los, edite as propriedades do e-mail ou do modelo de e-mail e desmarque a caixa localizada em **Geral &gt; Notificações**. Para obter mais informações sobre emails de teste A/B, consulte [Criação de um teste](../../channels/using/designing-an-a-b-test-email.md)AB. Para obter mais informações sobre propriedades de e-mail, consulte a [Lista de propriedades](../../administration/using/configuring-email-channel.md#list-of-email-properties)de e-mail.

   ![](assets/pulse_2.png)

* **[!UICONTROL Workflows]**: cada membro do grupo de segurança selecionado é notificado (notificação por email e no aplicativo) sempre que um fluxo de trabalho está com erro. Clicar na notificação ou no link de email exibe o fluxo de trabalho correspondente. As notificações são desativadas por padrão no modelo de fluxo de trabalho predefinido. Se você quiser ativá-los, edite as propriedades do fluxo de trabalho ou modelo de fluxo de trabalho e adicione um grupo de segurança em **Geral &gt; Execução &gt; Gerenciamento de erros &gt; Supervisores**. Para obter mais informações sobre grupos de segurança, consulte [Gerenciamento de grupos e usuários](../../administration/using/managing-groups-and-users.md). Para obter mais informações sobre as propriedades do fluxo de trabalho, consulte as propriedades [do](../../automating/using/executing-a-workflow.md#workflow-properties)Fluxo de trabalho.

   ![](assets/pulse_1.png)

