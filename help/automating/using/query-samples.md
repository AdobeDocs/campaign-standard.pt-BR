---
title: Amostras de consulta
description: Esta seção apresenta o caso de uso ao usar uma atividade de Query.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: query,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 0a71e3a7-60e6-49ec-af2e-099ad0d69a15
TQID: https://experienceleague.adobe.com/65HKTwwETEWkW1P6c1pfYBIJQDYwqC-DPmq7JQiye7s
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: d095671a-1355-40aa-8b5f-06c33c68080bid: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 339
ht-degree: 76%

---

# Amostras de consulta {#query-samples}

Esta seção apresenta o caso de uso ao usar uma atividade **[!UICONTROL Query]**. Para obter mais informações sobre como usar uma atividade **[!UICONTROL Query]**, consulte [esta seção](../../automating/using/query.md).

## Direcionamento em atributos simples de perfil {#targeting-on-simple-profile-attributes}

O exemplo a seguir mostra uma atividade de consulta configurada para direcionar homens entre 18 e 30 anos, que moram em Londres.

![](assets/query_sample_1.png)

## Direcionamento em atributos de email {#targeting-on-email-attributes}

O exemplo a seguir mostra uma atividade de consulta configurada para direcionar perfis com o domínio de endereço de email “orange.co.uk”.

![](assets/query_sample_emaildomain.png)

O exemplo a seguir mostra uma atividade de consulta configurada para direcionar perfis cujo endereço de email foi fornecido.

![](assets/query_sample_emailnotempty.png)

## Direcionamento de perfis cuja data de nascimento é hoje {#targeting-profiles-whose-birthday-is-today}

O exemplo a seguir mostra uma atividade de consulta configurada para direcionar perfis cuja data de nascimento é hoje.

1. Arraste o filtro **[!UICONTROL Birthday]** na sua consulta.

   ![](assets/query_sample_birthday.png)

1. Defina **[!UICONTROL Filter type]** como **[!UICONTROL Relative]** e selecione **[!UICONTROL Today]**.

   ![](assets/query_sample_birthday2.png)

## Direcionamento de perfis que abriram um delivery específico {#targeting-profiles-who-opened-a-specific-delivery}

O exemplo a seguir mostra uma atividade de consulta configurada para filtrar perfis que abriram a entrega com o rótulo “Hora de verão”.

1. Arraste o filtro **[!UICONTROL Opened]** na sua consulta.

   ![](assets/query_sample_opened.png)

1. Selecione a entrega e clique em **[!UICONTROL Confirm]**.

   ![](assets/query_sample_opened2.png)

## Direcionamento de perfis com falha de deliveries por um motivo específico {#targeting-profiles-for-whom-deliveries-failed-for-a-specific-reason}

O exemplo a seguir mostra uma atividade de consulta configurada para filtrar perfis com falha de entregas porque a caixa de entrada estava cheia. Essa consulta só está disponível para usuários com direitos administrativos e pertencentes a unidades organizacionais **[!UICONTROL All (all)]** (consulte [esta seção](../../administration/using/organizational-units.md)).

1. Selecione o recurso **[!UICONTROL Delivery logs]** para filtrar diretamente na tabela de logs da entrega (consulte [Uso de recursos diferentes das dimensões de direcionamento](../../automating/using/using-resources-different-from-targeting-dimensions.md)).

   ![](assets/query_sample_failure1.png)

1. Arraste o filtro **[!UICONTROL Nature of failure]** na sua consulta.

   ![](assets/query_sample_failure2.png)

1. Selecione o tipo de falha que deseja direcionar. No nosso caso, o tipo de falha é **[!UICONTROL Mailbox full]**.

   ![](assets/query_sample_failure3.png)

## Direcionamento de perfis não contatados nos últimos sete dias {#targeting-profiles-not-contacted-during-the-last-7-days}

O exemplo a seguir mostra uma atividade de consulta configurada para filtrar perfis que não foram contatados nos últimos sete dias.

1. Arraste o filtro **[!UICONTROL Delivery logs (logs)]** na sua consulta.

   ![](assets/query_sample_7days.png)

   Selecione **[!UICONTROL Does not exist]** na lista suspensa e arraste o filtro **[!UICONTROL Delivery]**.

   ![](assets/query_sample_7days1.png)

1. Configure o filtro como abaixo.

   ![](assets/query_sample_7days2.png)

## Direcionamento de perfis que clicaram em um link específico {#targeting-profiles-who-clicked-a-specific-link-}

1. Arraste o filtro **[!UICONTROL Tracking logs (tracking)]** no sua consulta.

   ![](assets/query_sample_trackinglogs.png)

1. Arraste o filtro **[!UICONTROL Label (urlLabel)]**.

   ![](assets/query_sample_trackinglogs2.png)

1. No campo **[!UICONTROL Value]**, digite o rótulo que foi definido na inserção do link na entrega e, em seguida, confirme.

   ![](assets/query_sample_trackinglogs3.png)
