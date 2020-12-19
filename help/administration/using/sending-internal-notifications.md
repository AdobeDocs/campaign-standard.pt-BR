---
solution: Campaign Standard
product: campaign
title: Enviar notificações internas
description: Saiba como enviar notificações do sistema em tempo real aos usuários do Adobe Campaign.
audience: administration
content-type: reference
topic-tags: application-settings
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 2%

---


# Enviar notificações internas{#sending-internal-notifications}

A Adobe Campaign oferece a possibilidade de receber notificações relacionadas a atividades importantes do sistema diretamente no aplicativo. As notificações em tempo real mantêm as partes interessadas relevantes informadas e fornecem aos usuários a capacidade de agir imediata e diretamente nas notificações de atividade no aplicativo. O resultado para as equipes é agilidade avançada, eficiência e execução mais suave do campanha.

![](assets/pulse_3.png)

Você pode configurar notificações para os seguintes objetos:

* **[!UICONTROL A/B Test emails]**: o criador e modificador(es) de e-mail são notificados de que uma variante foi escolhida (modo automático) ou que uma variante precisa ser escolhida (modo manual). Clicar na notificação exibe o email correspondente. As notificações são ativadas por padrão no modelo pronto para uso do teste A/B. Se desejar desativá-los, edite as propriedades do e-mail ou do modelo de e-mail e desmarque a caixa localizada em **Geral > Notificações**. Para obter mais informações sobre emails de teste A/B, consulte [Criação de um teste AB](../../channels/using/designing-an-a-b-test-email.md). Para obter mais informações sobre as propriedades de email, consulte [Lista das propriedades de email](../../administration/using/configuring-email-channel.md#list-of-email-properties).

   ![](assets/pulse_2.png)

* **[!UICONTROL Workflows]**: cada membro do grupo de segurança selecionado é notificado (notificação por email e no aplicativo) sempre que um fluxo de trabalho está com erro. Clicar na notificação ou no link de email exibe o fluxo de trabalho correspondente. As notificações são desativadas por padrão no modelo de fluxo de trabalho predefinido. Se quiser ativá-los, edite as propriedades do fluxo de trabalho ou modelo de fluxo de trabalho e adicione um grupo de segurança em **Geral > Execução > Gerenciamento de erros > Supervisores**. Para obter mais informações sobre grupos de segurança, consulte [Gerenciar grupos e usuários](../../administration/using/managing-groups-and-users.md). Para obter mais informações sobre as propriedades do fluxo de trabalho, consulte [Propriedades do fluxo de trabalho](../../automating/using/managing-execution-options.md).

   ![](assets/pulse_1.png)
