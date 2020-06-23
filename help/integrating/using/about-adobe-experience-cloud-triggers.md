---
title: Sobre os acionadores da Adobe Experience Cloud
description: Ao rastrear comportamentos específicos de clientes com o Adobe Analytics, agora você pode enviar emails personalizados para seus clientes no Adobe Campaign.
page-status-flag: never-activated
uuid: 0aa4bd6e-1bb5-4d0b-913b-eca93f050acd
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
discoiquuid: e526b205-2d01-4a8b-9685-ba1d9a1f459f
context-tags: trigger,overview;trigger,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f7adb7a4725129727010c2486ca34bbc2021c539
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 4%

---


# Sobre os acionadores da Adobe Experience Cloud{#about-adobe-experience-cloud-triggers}

Integration between the Experience Cloud Activation core service **[!UICONTROL Triggers]** and Adobe Campaign allows you to send personalized emails to your customers as a reaction to specific behaviors that are tracked on your website by Adobe Analytics (within 15 minutes).

Na Adobe Experience Cloud, você define os diferentes acionadores, ou seja, os comportamentos do cliente que você gostaria de monitorar, como todos os clientes que abandonaram sua visita em seu site, fizeram uma pesquisa em seu site, mas não fizeram uma compra ou até mesmo os clientes cuja sessão expirou. Ao criar um acionador, você define a condição do acionador e os dados que serão enviados no evento (carregamento) para o Adobe Campaign.

No Adobe Campaign, selecione o acionador que foi criado anteriormente, você aprimora os dados do evento com dados do datamart e define um template de mensagem transacional vinculado a esse acionador. Por exemplo, quando um cliente abandona sua visita em seu site, um evento é enviado para o Adobe Campaign, que pode aproveitar esse evento por meio de um email de remarketing enviado ao cliente em 15 minutos.

**Tópicos relacionados:**

* Saiba mais sobre os diferentes tipos de acionadores: [Documentação](https://docs.adobe.com/content/help/en/core-services/interface/activation/triggers.html)da Adobe Experience Cloud.
* Assista ao vídeo [Acionar mensagens de recomercialização com base na Atividade](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two) do site.
* Descubra que nossos dois Acionadores de [Abandono usam casos](../../integrating/using/abandonment-triggers-use-cases.md).

## Aciona o processo do usuário {#triggers-user-process}

>[!CAUTION]
>
>Antes de executar as etapas principais do usuário, a funcionalidade precisa ser configurada. Para obter mais informações, consulte [Ativação da funcionalidade](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality), [Configuração de soluções e serviços](../../integrating/using/configuring-triggers-in-experience-cloud.md#configuring-solutions-and-services) e [Criação de um acionador mapeado na Campanha](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign).

As principais etapas do processo do usuário, no Adobe Campaign, são:

1. Crie um evento de disparo vinculado a um acionador da Adobe Experience Cloud existente.
1. Publique o evento de disparo.
1. Defina o conteúdo do template de mensagem transacional.
1. Teste o modelo (crie um perfil de teste e envie uma prova).
1. Publique o template de mensagem transacional.

Casos de uso completos estão descritos na [presente seção](../../integrating/using/abandonment-triggers-use-cases.md).

## Observações importantes {#important-notes}

Estas são algumas observações importantes a serem levadas em conta antes de usar os Acionadores - integração Campanha:

* Notificações por push não são suportadas para acionadores. Somente Email e SMS são suportados.
* Você pode enriquecer o acionador com metadados capturados pela Analytics, como ID de e-mail, nome de página etc.
* É possível reconciliar o acionador com um perfil armazenado no Campaign Standard e usar os campos perfil para personalizar a mensagem.
* Assim que um acionador é recebido, é processado e reconciliado e enviado. Leva cerca de 5 a 15 minutos dependendo do volume de acionadores recebidos, o número de campos de personalização usados no modelo.

>[!NOTE]
>
>Para obter mais informações sobre práticas recomendadas e limitações técnicas, consulte Práticas recomendadas e limitações [do](../../integrating/using/configuring-triggers-in-experience-cloud.md#triggers-best-practices-and-limitations)Acionador.

