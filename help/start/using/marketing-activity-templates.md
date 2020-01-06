---
title: Sobre os modelos
description: '"Os modelos do Adobe Campaign permitem pré-configurar parâmetros dependendo de suas necessidades: os modelos podem conter uma configuração completa ou parcial da atividade de marketing, para simplificar o uso do Adobe Campaign para usuários finais não técnicos."'
page-status-flag: never-activated
uuid: 018534b6-61a3-433e-bb60-49883c8b9386
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: managing-templates
discoiquuid: 95218ebe-5430-42a2-b900-1dadbbc92d99
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: cb5cc55c431cbe6050699a35ef2fff270f869dee

---


# Modelos de atividades de marketing {#marketing-activity-templates}

## Sobre os modelos {#about-templates}

Quando você cria uma nova atividade de marketing, a primeira tela do assistente solicita que você selecione um tipo ou modelo. Os modelos permitem pré-configurar certos parâmetros de acordo com suas necessidades. O modelo pode conter uma configuração total ou parcial da atividade de marketing. O gerenciamento de modelos é executado pelo administrador funcional.

O usuário final tem uma interface simplificada. Ao criar uma nova atividade de marketing, basta selecionar o modelo que deseja usar. Não há necessidade de se preocupar com configurações técnicas. Isso já foi pré-configurado pelo administrador funcional no modelo.

Por exemplo, no caso de um modelo de email, você pode preencher previamente o conteúdo HTML, o público-alvo e qualquer outro parâmetro da entrega: agendamento, perfis de teste, as propriedades gerais da entrega, os parâmetros avançados etc. Isso permite economizar tempo ao criar uma nova atividade.

![](assets/template_1.png)

Para cada tipo de atividade de marketing, um ou vários modelos prontos para uso estão disponíveis com configuração mínima. Esses modelos predefinidos não podem ser modificados ou excluídos.

Os modelos estão disponíveis para as seguintes atividades de marketing:

* Programas
* Campanhas
* Deliveries de email
* Entregas SMS
* Notificações por push
* Páginas de aterrissagem
* Fluxos de trabalho
* Serviços
* Importar
* Mensagens transacionais

## Criação de um novo modelo {#creating-a-new-template}

Os modelos de mensagem podem ser gerenciados pelo administrador funcional da plataforma, sob o **[!UICONTROL Resources > Templates]**menu. Os modelos predefinidos não podem ser modificados ou excluídos. Para criar um novo modelo, você deve duplicar um existente.

1. Selecione um modelo existente. No nosso exemplo, escolhemos um **[!UICONTROL Delivery template]**.

   ![](assets/template_2.png)

1. Passe o mouse sobre ele e selecione a **[!UICONTROL Duplicate element]**opção.

   ![](assets/template_3.png)

1. Defina as configurações desejadas, da mesma forma que faria ao [criar uma nova atividade](../../start/using/marketing-activities.md#creating-a-marketing-activity) de marketing do zero.

   ![](assets/template_4.png)

Modelos criados podem ser selecionados pelo usuário padrão na primeira tela do assistente ao criar uma atividade de marketing.

## Uso de um modelo {#using-a-template}

Agora vamos investigar como usar um modelo criado na seção anterior.

>[!NOTE]
>
>A criação de uma atividade de marketing com base em um modelo é geralmente realizada por um perfil de tipo de usuário padrão.

1. Crie uma nova atividade de marketing.

   ![](assets/template_5.png)

1. Na primeira tela do assistente, selecione o modelo que deseja usar.

   ![](assets/template_6.png)

   A atividade de marketing é pré-configurada com os parâmetros definidos no modelo.

   ![](assets/template_7.png)
