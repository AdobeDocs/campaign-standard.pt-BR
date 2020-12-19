---
solution: Campaign Standard
product: campaign
title: Amostras de queries
description: Esta seção apresenta o caso de uso ao usar uma atividade de Query.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: query,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 90%

---


# Amostras de queries {#query-samples}

Esta seção apresenta um caso de uso ao usar uma atividade **[!UICONTROL Query]**. Para obter mais informações sobre como usar uma atividade **[!UICONTROL Query]**, consulte [esta seção](../../automating/using/query.md).

## Direcionamento em atributos simples de perfil {#targeting-on-simple-profile-attributes}

O exemplo a seguir mostra uma atividade de query configurada para direcionar homens entre 18 e 30 anos, que moram em Londres.

![](assets/query_sample_1.png)

## Direcionamento em atributos de email {#targeting-on-email-attributes}

O exemplo a seguir mostra uma atividade de query configurada para direcionar perfis com o domínio de endereço de email “orange.co.uk”.

![](assets/query_sample_emaildomain.png)

O exemplo a seguir mostra uma atividade de query configurada direcionar perfis cujo endereço de email foi fornecido.

![](assets/query_sample_emailnotempty.png)

## Direcionamento de perfis cuja data de nascimento é hoje {#targeting-profiles-whose-birthday-is-today}

O exemplo a seguir mostra uma atividade de query configurada para direcionar perfis cuja data de nascimento é hoje.

1. Arraste o filtro **[!UICONTROL Birthday]** no seu query.

   ![](assets/query_sample_birthday.png)

1. Defina **[!UICONTROL Filter type]** como **[!UICONTROL Relative]** e selecione **[!UICONTROL Today]**.

   ![](assets/query_sample_birthday2.png)

## Direcionamento de perfis que abriram um delivery específico {#targeting-profiles-who-opened-a-specific-delivery}

O exemplo a seguir mostra uma atividade de query configurada para filtrar perfis que abriram o delivery com o rótulo “Hora de verão”.

1. Arraste o filtro **[!UICONTROL Opened]** no seu query.

   ![](assets/query_sample_opened.png)

1. Selecione o delivery e clique em **[!UICONTROL Confirm]**.

   ![](assets/query_sample_opened2.png)

## Direcionamento de perfis com falha de deliveries por um motivo específico {#targeting-profiles-for-whom-deliveries-failed-for-a-specific-reason}

O exemplo a seguir mostra uma atividade de query configurada para filtrar perfis com falha de deliveries porque a caixa de entrada estava cheia. Esse query só está disponível para usuários com direitos administrativos e pertencentes a unidades organizacionais **[!UICONTROL All (all)]** (consulte [esta seção](../../administration/using/organizational-units.md)).

1. Selecione o recurso **[!UICONTROL Delivery logs]** para filtrar diretamente na tabela de logs do delivery (consulte [Uso de recursos diferentes dos targeting dimensions](../../automating/using/using-resources-different-from-targeting-dimensions.md)).

   ![](assets/query_sample_failure1.png)

1. Arraste o filtro **[!UICONTROL Nature of failure]** no seu query.

   ![](assets/query_sample_failure2.png)

1. Selecione o tipo de falha que deseja direcionar. No nosso caso, o tipo de falha é **[!UICONTROL Mailbox full]**.

   ![](assets/query_sample_failure3.png)

## Direcionamento de perfis não contatados nos últimos sete dias {#targeting-profiles-not-contacted-during-the-last-7-days}

O exemplo a seguir mostra uma atividade de query configurada para filtrar perfis que não foram contatados nos últimos sete dias.

1. Arraste o filtro **[!UICONTROL Delivery logs (logs)]** no seu query.

   ![](assets/query_sample_7days.png)

   Selecione **[!UICONTROL Does not exist]** na lista suspensa e arraste o filtro **[!UICONTROL Delivery]**.

   ![](assets/query_sample_7days1.png)

1. Configure o filtro como abaixo.

   ![](assets/query_sample_7days2.png)

## Direcionamento de perfis que clicaram em um link específico {#targeting-profiles-who-clicked-a-specific-link-}

1. Arraste o filtro **[!UICONTROL Tracking logs (tracking)]** no seu query.

   ![](assets/query_sample_trackinglogs.png)

1. Arraste o filtro **[!UICONTROL Label (urlLabel)]**.

   ![](assets/query_sample_trackinglogs2.png)

1. No campo **[!UICONTROL Value]**, digite o rótulo que foi definido na inserção do link no delivery e, em seguida, confirme.

   ![](assets/query_sample_trackinglogs3.png)
