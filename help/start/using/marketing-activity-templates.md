---
title: Sobre templates
description: “Os templates do Adobe Campaign permitem pré-configurar parâmetros dependendo das necessidades. Eles podem conter uma configuração completa ou parcial da atividade de marketing para simplificar o Adobe Campaign para os usuários finais não técnicos.”
page-status-flag: never-activated
uuid: 018534b6-61a3-433e-bb60-49883c8b9386
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: managing-templates
discoiquuid: 95218ebe-5430-42a2-b900-1dadbbc92d99
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 100%

---


# Templates de atividades de marketing {#marketing-activity-templates}

## Sobre templates {#about-templates}

Ao criar uma nova atividade de marketing, a primeira tela do assistente solicita que você selecione um tipo ou template. Os templates permitem pré-configurar parâmetros específicos de acordo com as necessidades. O template pode conter uma configuração completa ou parcial da atividade de marketing. O gerenciamento de templates é feito pelo administrador funcional.

O usuário final tem uma interface simplificada. Ao criar uma nova atividade de marketing, basta selecionar o template que quer usar. Você não precisa se preocupar com configurações técnicas. Ele já foi pré-configurado pelo administrador funcional no template.

Por exemplo, no caso de um template de email, você pode preencher previamente o conteúdo HTML, o público-alvo e qualquer outro parâmetro do delivery, como programação, perfis de teste, as propriedades gerais do delivery, os parâmetros avançados etc. Assim, você economiza tempo ao criar uma nova atividade.

![](assets/template_1.png)

Para cada tipo de atividade de marketing, um ou vários templates prontos para uso estão disponíveis com configuração mínima. Esses templates prontos para uso não podem ser modificados ou excluídos.

Os templates estão disponíveis para as seguintes atividades de marketing:

* Programas
* Campanhas
* Deliveries de email
* Deliveries por SMS
* Notificações por push
* Landing pages
* Fluxos de trabalho
* Serviços
* Importação
* Mensagens transacionais

## Criação de um novo template {#creating-a-new-template}

Os templates de mensagem podem ser gerenciados pelo administrador funcional da plataforma, no menu **[!UICONTROL Resources > Templates]**. Os templates prontos para uso não podem ser modificados ou excluídos. Para criar um novo template, você deve duplicar um template existente.

1. Selecione um template. Neste exemplo, escolhemos um **[!UICONTROL Delivery template]**.

   ![](assets/template_2.png)

1. Passe o mouse sobre ele e selecione a opção **[!UICONTROL Duplicate element]**.

   ![](assets/template_3.png)

1. Defina as configurações desejadas, da mesma forma que faria ao [criar uma nova atividade de marketing](../../start/using/marketing-activities.md#creating-a-marketing-activity) do zero.

   ![](assets/template_4.png)

Os templates criados podem ser selecionados pelo usuário padrão na primeira tela do assistente ao criar uma atividade de marketing.

## Uso de um template {#using-a-template}

Agora vamos analisar como usar um template criado na seção anterior.

>[!NOTE]
>
>A criação de uma atividade de marketing com base em um template é geralmente feita por um perfil padrão de tipo de usuário.

1. Crie uma nova atividade de marketing.

   ![](assets/template_5.png)

1. Na primeira tela do assistente, selecione o template que deseja usar.

   ![](assets/template_6.png)

   A atividade de marketing é pré-configurada com os parâmetros definidos no template.

   ![](assets/template_7.png)
