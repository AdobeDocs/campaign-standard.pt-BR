---
title: Sobre modelos
description: 'Os templates do Adobe Campaign permitem pré-configurar parâmetros dependendo das necessidades: eles podem conter uma configuração completa ou parcial da atividade de marketing para simplificar o uso do Adobe Campaign para usuários finais não técnicos.'
audience: start
content-type: reference
topic-tags: managing-templates
feature: Campaigns
role: User
level: Beginner
exl-id: a0f02f69-d72d-48ca-8b38-aaab8d1acfad
TQID: https://experienceleague.adobe.com/kZTyOD8tL-C3HzPpUhVohvr7dM0WZ-EdNNQA1S1iB6k
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 417
ht-degree: 79%

---

# Modelos de atividades de marketing {#marketing-activity-templates}

## Sobre modelos {#about-templates}

Ao criar uma nova atividade de marketing, a primeira tela do assistente solicita que você selecione um tipo ou modelo. Os modelos permitem pré-configurar parâmetros específicos de acordo com as necessidades. O modelo pode conter uma configuração completa ou parcial da atividade de marketing. O gerenciamento de modelos é feito pelo administrador funcional.

O usuário final tem uma interface simplificada. Ao criar uma nova atividade de marketing, basta selecionar o modelo que quer usar. Você não precisa se preocupar com configurações técnicas. Ele já foi pré-configurado pelo administrador funcional no modelo.

Por exemplo, no caso de um template de email, você pode preencher previamente o conteúdo do HTML, o público-alvo e qualquer outro parâmetro do delivery: programação, perfis de teste, as propriedades gerais do delivery, os parâmetros avançados etc. Isso permite economizar tempo ao criar uma nova atividade.

![](assets/template_1.png)

Para cada tipo de atividade de marketing, um ou vários modelos prontos para uso estão disponíveis com configuração mínima. Esses modelos prontos para uso não podem ser modificados ou excluídos.

Os modelos estão disponíveis para as seguintes atividades de marketing:

* Programas
* Campanhas
* Entregas de email
* Entregas por SMS
* Notificações por push
* Páginas de destino
* Fluxos de trabalho
* Serviços
* Importação
* Mensagens transacionais

## Criação de um novo modelo {#creating-a-new-template}

Os modelos de mensagem podem ser gerenciados pelo administrador funcional da plataforma, no menu **[!UICONTROL Resources > Templates]**. Os modelos prontos para uso não podem ser modificados ou excluídos. Para criar um novo modelo, você deve duplicar um modelo existente.

1. Selecione um modelo. Neste exemplo, escolhemos um **[!UICONTROL Delivery template]**.

   ![](assets/template_2.png)

1. Passe o mouse sobre ele e selecione a opção **[!UICONTROL Duplicate element]**.

   ![](assets/template_3.png)

1. Defina as configurações desejadas, da mesma forma que faria ao [criar uma nova atividade de marketing](../../start/using/marketing-activities.md#creating-a-marketing-activity) do zero.

   ![](assets/template_4.png)

Os modelos criados podem ser selecionados pelo usuário padrão na primeira tela do assistente ao criar uma atividade de marketing.

## Uso de um template {#using-a-template}

Agora vamos analisar como usar um modelo criado na seção anterior.

>[!NOTE]
>
>A criação de uma atividade de marketing com base em um modelo é geralmente feita por um perfil padrão de tipo de usuário.

1. Crie uma nova atividade de marketing.

   ![](assets/template_5.png)

1. Na primeira tela do assistente, selecione o modelo que deseja usar.

   ![](assets/template_6.png)

   A atividade de marketing é pré-configurada com os parâmetros definidos no modelo.

   ![](assets/template_7.png)
