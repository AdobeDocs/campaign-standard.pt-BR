---
solution: Campaign Standard
product: campaign
title: Enviar notificações internas
description: Saiba como enviar notificações do sistema em tempo real para seus usuários do Adobe Campaign.
audience: administration
content-type: reference
topic-tags: application-settings
feature: Instance Settings
role: Administrator
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 2%

---


# Enviar notificações internas{#sending-internal-notifications}

O Adobe Campaign oferece a possibilidade de receber notificações sobre atividades importantes do sistema diretamente no aplicativo. As notificações em tempo real mantêm os participantes relevantes informados e fornecem aos usuários a capacidade de agir imediata e diretamente nas notificações de atividades dentro do aplicativo. O resultado para as equipes é agilidade avançada, eficiência e execução mais suave de campanhas.

![](assets/pulse_3.png)

É possível configurar notificações para os seguintes objetos:

* **[!UICONTROL A/B Test emails]**: o criador e o(s) modificador(es) de email são notificados que uma variante foi escolhida (modo automático) ou que uma variante precisa ser escolhida (modo manual). Clicar na notificação exibe o email correspondente. As notificações são ativadas por padrão no template de teste A/B pronto para uso. Se desejar desativá-los, edite as propriedades do email ou do modelo de email e desmarque a caixa localizada em **General > Notifications**. Para obter mais informações sobre emails de Teste A/B, consulte [Criação de um Teste AB](../../channels/using/designing-an-a-b-test-email.md). Para obter mais informações sobre propriedades de email, consulte [Lista de propriedades de email](../../administration/using/configuring-email-channel.md#list-of-email-properties).

   ![](assets/pulse_2.png)

* **[!UICONTROL Workflows]**: cada membro do grupo de segurança selecionado é notificado (notificação por email e no aplicativo) sempre que um workflow está com erro. Clicar na notificação ou no link do email exibe o fluxo de trabalho correspondente. As notificações são desativadas por padrão no template de workflow pronto para uso. Para ativá-los, edite as propriedades do workflow ou do template do workflow e adicione um grupo de segurança em **General > Execution > Error management > Supervisors**. Para obter mais informações sobre grupos de segurança, consulte [Gerenciamento de grupos e usuários](../../administration/using/managing-groups-and-users.md). Para obter mais informações sobre propriedades do workflow, consulte [Propriedades do workflow](../../automating/using/managing-execution-options.md).

   ![](assets/pulse_1.png)
