---
title: Definição de público-alvo de correspondência direta
description: Saiba como definir o público-alvo para a entrega de correspondência direta.
audience: channels
content-type: reference
topic-tags: direct-mail
context-tags: delivery,directMailContent,back
feature: Direct Mail
role: User
level: Intermediate
exl-id: ea167fec-d4df-4147-9dcd-33001d8a1c9b
TQID: 'https://experienceleague.adobe.com/iYqxhsfsz95pTh8V-sP-xwGSSQ39YyIov9OHHyfepDI'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
subfeature_v2:
  - id: ede6e1ec-9279-415e-b828-a09735018d48
    internal-label: Direct mail
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 96%
---
# Definição de público-alvo de correspondência direta{#defining-the-direct-mail-audience}

Você pode definir o público-alvo no assistente de criação ou clicando na seção **Audience** do painel da entrega.

![](assets/direct_mail_15.png)

## Definição do público-alvo principal {#defining-the-main-target}

Para correspondência direta, os perfis segmentados são aqueles que serão incluídos no arquivo de extração que deve ser enviado ao seu provedor de correspondência direta.

Para cada perfil segmentado, uma nova linha é adicionada ao arquivo de extração. A quantidade de informações de perfil que será incluída para cada destinatário é definida na tela [Definição da extração](../../channels/using/defining-the-direct-mail-content.md#defining-the-extraction).

>[!IMPORTANT]
>
>Verifique se os perfis incluem o CEP, pois essa informação é essencial para o provedor de correspondência direta. Verifique também se você marcou a caixa **[!UICONTROL Address specified]** nas informações dos perfis. Consulte [Recomendações](../../channels/using/about-direct-mail.md#recommendations).

## Adicionar perfis de teste e cobertura {#adding-test-and-trap-profiles}

Adicione perfis de teste para testar seu arquivo com um pequeno número de perfis. Assim, você pode criar rapidamente uma amostra de arquivo para testar e validar a estrutura antes de preparar o arquivo real. Consulte [Gerenciamento de perfis de teste](../../audiences/using/managing-test-profiles.md).

O uso de coberturas é essencial para entregas de correspondência direta. Elas permitem verificar se o provedor de correspondência direta está realmente enviando a comunicação e se ele não está enviando sua lista de clientes a outro provedor. Consulte [Uso de coberturas](../../sending/using/using-traps.md).

Para entregas de correspondência direta, as coberturas são adicionadas durante a extração e combinadas no documento de saída. Por padrão, elas são inseridas na ordem de classificação do arquivo de saída, mas é possível optar por inseri-las no final ou no início do arquivo. Ao definir o público-alvo, selecione a opção desejada na guia **[!UICONTROL Trap insertion mode]**.

![](assets/direct_mail_trap_insertion_mode.png)
