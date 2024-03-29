---
title: Etapas principais para enviar uma mensagem
description: Siga estas etapas para criar e enviar mensagens com o Adobe Campaign.
audience: channels
content-type: reference
topic-tags: about-communication-channels
feature: Overview
role: User
level: Beginner
exl-id: a903d7e2-7654-46b3-bc61-4653a065faad
source-git-commit: 13d419c5fc51845ee14f8a3b288f4c467e0a60d9
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 13%

---

# Etapas principais para enviar uma mensagem{#key-steps-to-send-a-message}

Nesta seção, você aprenderá a criar e enviar mensagens personalizadas para um público-alvo usando o Adobe Campaign Standard.

Informações específicas sobre como criar e configurar cada canal de comunicação estão disponíveis nestas seções:

* [Criação de um email](../../channels/using/creating-an-email.md)
* [Criação de um SMS](../../channels/using/creating-an-sms-message.md)
* [Criação de uma entrega de correspondência direta](../../channels/using/creating-the-direct-mail.md)
* [Criação de uma notificação por push](../../channels/using/preparing-and-sending-a-push-notification.md).
* [Preparação e envio de uma mensagem no aplicativo](../../channels/using/preparing-and-sending-an-in-app-message.md)

Para saber mais sobre as práticas recomendadas de delivery, consulte o [Práticas recomendadas de entrega](../../sending/using/delivery-best-practices.md) seção.

## Criar sua mensagem

Aproveitar o Campaign Standard [atividades de marketing](../../start/using/marketing-activities.md) para criar um email, SMS, correspondência direta, notificação por push ou mensagem no aplicativo.

![](assets/marketing-activities.png)

As mensagens podem ser criadas na lista de atividades de marketing ou em um workflow usando [atividades dedicadas](../../automating/using/about-channel-activities.md).

![](assets/steps-channel.png)

## Definir o público-alvo

Defina os recipients da mensagem. Para fazer isso, use o [editor de consulta](../../automating/using/editing-queries.md) no painel esquerdo, para filtrar os dados contidos no banco de dados e criar regras para direcionar o público-alvo.

Há vários tipos de públicos-alvo disponíveis:

* **[!UICONTROL Target]** é o principal público-alvo do seu email,
* **[!UICONTROL Test profiles]** são os perfis usados para testar e validar seu email (consulte [Gerenciamento de perfis de teste](../../audiences/using/managing-test-profiles.md)).

![](assets/steps-audience.png)

## Projetar e personalizar conteúdo

No **[!UICONTROL Content]** bloquear, projetar e personalizar o conteúdo da mensagem usando campos do banco de dados. Para obter mais informações sobre como projetar conteúdo para um canal específico, consulte as seções listadas na parte superior desta página.

![](assets/steps-content.png)

## Preparar e testar

[Preparar](../../sending/using/preparing-the-send.md) a mensagem. Esse processo calcula a população do target e prepara a mensagem personalizada.

![](assets/steps-prepare.png)

**Verificar e testar a mensagem** antes de enviá-lo usando os recursos do Campaign Standard: pré-visualização, renderização de email, prova etc. Para obter mais informações, consulte [esta seção](../../sending/using/previewing-messages.md).

Use o **[!UICONTROL Schedule]** bloco para definir quando suas mensagens serão enviadas (consulte [Agendamento de mensagens](../../sending/using/about-scheduling-messages.md)).

![](assets/steps-schedule.png)

## Enviar e rastrear

Quando a mensagem estiver pronta, você poderá confirmar o envio. A variável **[!UICONTROL Deployment]** exibe o progresso do envio e o resultado.

![](assets/steps-send.png)

Vários logs estão disponíveis para ajudar a monitorar o delivery de suas mensagens (consulte [monitoramento de um delivery](../../sending/using/monitoring-a-delivery.md)). Também é possível rastrear o comportamento dos recipients do delivery graças ao Campaign Standard [funcionalidades de rastreamento](../../sending/using/tracking-messages.md).

![](../../sending/using/assets/tracking_logs.png)

Meça a eficácia de suas mensagens e a evolução de seus envios e campanhas por meio de vários indicadores e gráficos (consulte [Acesso ao relatórios](../../reporting/using/about-dynamic-reports.md)).

![](assets/steps-reports.png)
