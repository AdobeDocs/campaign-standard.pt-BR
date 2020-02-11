---
title: Definição do público-alvo do correio direto
description: Saiba como definir a meta para a entrega de mala direta.
page-status-flag: never-activated
uuid: f843e368-5c07-4b53-8943-46f7bf45b62b
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: direct-mail
discoiquuid: f993d1b6-4b9a-4f95-81fc-60c126211bd2
context-tags: delivery,directMailContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 07d68b5bf8d800ebd95919f491e98f1b7a015705

---


# Definição do público-alvo do correio direto{#defining-the-direct-mail-audience}

Você pode definir o público-alvo no assistente de criação ou clicando na seção **Público-alvo** do painel de entrega.

![](assets/direct_mail_15.png)

## Definição da meta principal {#defining-the-main-target}

Para mala direta, os perfis direcionados são aqueles que serão incluídos no arquivo de extração que você enviará ao seu provedor de mala direta.

Para cada perfil direcionado, uma nova linha é adicionada ao arquivo de extração. A quantidade de informações de perfil que serão incluídas para cada destinatário é definida na tela [Definindo a extração](../../channels/using/defining-the-direct-mail-content.md#defining-the-extraction) .

>[!CAUTION]
>
>Certifique-se de que seus perfis incluam um endereço postal, pois essas informações são essenciais para o provedor de mala direta. Verifique também se você marcou a **[!UICONTROL Address specified]** caixa nas informações de seus perfis. Consulte [Recomendações](../../channels/using/about-direct-mail.md#recommendations).

## Adicionar perfis de teste e trapping {#adding-test-and-trap-profiles}

Adicione perfis de teste para que você possa testar seu arquivo com um pequeno número de perfis. Permite criar rapidamente uma amostra de arquivo para testar e validar a estrutura antes de preparar o arquivo real. Consulte [Gerenciamento de perfis](../../audiences/using/managing-test-profiles.md)de teste.

A utilização de armadilhas é essencial para a entrega direta de correio. Eles permitem que você verifique se seu provedor de mala direta está realmente enviando a comunicação e se eles não estão enviando sua lista de clientes para outro provedor. Consulte [Uso de armadilhas](../../sending/using/using-traps.md).

Para entregas por mala direta, as armadilhas são adicionadas durante a extração e misturadas no documento de saída. Por padrão, eles são inseridos na ordem de classificação do arquivo de saída, mas você pode optar por inseri-los no final ou no início do arquivo. Ao definir o público-alvo, selecione a opção desejada na **[!UICONTROL Trap insertion mode]** guia.

![](assets/direct_mail_trap_insertion_mode.png)
