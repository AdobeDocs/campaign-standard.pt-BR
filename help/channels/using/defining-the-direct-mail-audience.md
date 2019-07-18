---
title: Definição do público-alvo de mala direta
seo-title: Definição do público-alvo de mala direta
description: Definição do público-alvo de mala direta
seo-description: Saiba como definir a meta para sua entrega de mala direta.
page-status-flag: nunca ativado
uuid: f 843 e 368-5 c 07-4 b 53-8943-46 f 7 bf 45 b 62 b
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canais
content-type: reference
topic-tags: direta
discoiquuid: f 993 d 1 b 6-4 b 9 a -4 f 95-81 fc -60 c 126211 bd 2
context-tags: entrega, directmailcontent, back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b0cf437ec97153b53bd4502171b24286abb25731

---


# Defining the direct mail audience{#defining-the-direct-mail-audience}

You can either define the audience in the creation wizard or by clicking on the **Audience** section of the delivery dashboard.

![](assets/direct_mail_15.png)

## Defining the main target {#defining-the-main-target}

Para mala direta, os perfis direcionados são aqueles que serão incluídos no arquivo de extração que você enviará para o seu provedor de mala direta.

Para cada perfil direcionado, uma nova linha é adicionada no arquivo de extração. The amount of profile information that will be included for each recipient is defined in the [Defining the extraction](../../channels/using/defining-the-direct-mail-content.md#defining-the-extraction) screen.

>[!CAUTION]
>
>Verifique se os perfis incluem um endereço postal, pois essas informações são essenciais para o provedor de mala direta. Also make sure you have checked the **[!UICONTROL Address specified]** box in your profiles' information. See [Recommendations](../../channels/using/about-direct-mail.md#recommendations).

## Adding test and trap profiles {#adding-test-and-trap-profiles}

Adicione perfis de teste para testar seu arquivo com um pequeno número de perfis. Isso permite criar rapidamente uma amostra de arquivo para testar e validar a estrutura antes de preparar o arquivo real. Refer to [Managing test profiles and sending proofs](../../sending/using/managing-test-profiles-and-sending-proofs.md).

O uso de capturas é essencial para o envio de entregas por email. Por exemplo, eles permitem que você verifique se seu provedor de mala direta está enviando a comunicação e que não está enviando sua lista de clientes para outro provedor.

Para entregas de mala direta, as capturas são adicionadas durante a extração e misturadas no documento de saída. By default, they are inserted in the sorting order of the output file, but you can choose to insert them at the end or the beginning of the file ( **[!UICONTROL Trap insertion mode]** tab).
