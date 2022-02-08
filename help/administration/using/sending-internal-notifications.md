---
title: Envio de notificações internas
description: Saiba como enviar notificações do sistema em tempo real para seus usuários do Adobe Campaign
audience: administration
role: Admin
level: Experienced
exl-id: 7e04275a-5413-4f03-b18c-b64ab482d7d5
source-git-commit: bfba6b156d020e8d2656239e713d2d24625bda54
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 2%

---

# Envio de notificações internas{#sending-internal-notifications}

O Adobe Campaign oferece a possibilidade de receber notificações sobre atividades importantes do sistema diretamente no aplicativo. As notificações em tempo real mantêm os participantes relevantes informados e fornecem aos usuários a capacidade de agir imediata e diretamente nas notificações de atividades dentro do aplicativo. O resultado para as equipes é agilidade avançada, eficiência e execução mais suave de campanhas.

![](assets/pulse_3.png)

É possível configurar notificações para os seguintes objetos:

* **[!UICONTROL A/B Test emails]**: o criador e o(s) modificador(es) de email são notificados que uma variante foi escolhida (modo automático) ou que uma variante precisa ser escolhida (modo manual). Clicar na notificação exibe o email correspondente. As notificações são ativadas por padrão no template de teste A/B pronto para uso. Se desejar desativá-los, edite as propriedades do email ou do template de email e desmarque a caixa localizada em **Geral > Notificações**. Para obter mais informações sobre emails de Teste A/B, consulte [Criação de um teste AB](../../channels/using/designing-an-a-b-test-email.md). Para obter mais informações sobre propriedades de email, consulte [Lista de propriedades de email](../../administration/using/configuring-email-channel.md#list-of-email-properties).

   ![](assets/pulse_2.png)

* **[!UICONTROL Workflows]**: cada membro do grupo de segurança selecionado é notificado (notificação por email e no aplicativo) sempre que um workflow está com erro. Clicar na notificação ou no link do email exibe o fluxo de trabalho correspondente. As notificações são desativadas por padrão no template de workflow pronto para uso. Para ativá-los, edite as propriedades do workflow ou do template do workflow e adicione um grupo de segurança em **Geral > Execução > Gestão de erros > Supervisores**. Para obter mais informações sobre grupos de segurança, consulte [Gerenciamento de grupos e usuários](../../administration/using/managing-groups-and-users.md). Para obter mais informações sobre propriedades do workflow, consulte [Propriedades do workflow](../../automating/using/managing-execution-options.md).

   ![](assets/pulse_1.png)
