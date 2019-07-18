---
title: Sobre a mala direta
seo-title: Sobre a mala direta
description: Sobre a mala direta
seo-description: Descubra as principais especificidades do canal de mala direta no Adobe Campaign.
page-status-flag: nunca ativado
uuid: 24 add 992-2 efe -4 b 73-81 c 9-cda 3 e 921 ab 16
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canais
content-type: reference
topic-tags: direta
discoiquuid: e 1 fbf 39 c -9 c 30-493 c -8322-9 c 71 e 18 ce 98 c
context-tags: entrega, directmailcontent, back; Deliverycreation, assistente
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b0cf437ec97153b53bd4502171b24286abb25731

---


# About direct mail{#about-direct-mail}

Mala direta é um canal offline que permite personalizar e gerar o arquivo exigido pelos provedores de mala direta. Oferece a possibilidade de combinar canais online e offline nas jornadas do cliente.

>[!NOTE]
>
>Esse recurso é opcional. Verifique seu contrato de licença. The **[!UICONTROL Export]** role is required to use direct mail. Entre em contato com o administrador.

Os canais online permitem que você crie suas mensagens (email, SMS, entrega de aplicativos móveis etc.) e envie-os para o seu público-alvo diretamente do Adobe Campaign. Com canais offline, é diferente. Ao preparar uma entrega de mala direta, o Adobe Campaign gera um arquivo que inclui todos os perfis direcionados e as informações de contato escolhidas (endereço postal por exemplo). Você poderá enviar esse arquivo para o seu provedor de mala direta, que cuidará do envio real.

A seção a seguir explica como criar e gerar uma entrega de email direta de uma captura. Você também tem a possibilidade de incluir uma atividade de mala direta em um fluxo de trabalho para orquestrar campanhas que combinam canais online e offline. For more on this, refer to the [Workflows](../../automating/using/workflow-data-and-processes.md) guide.

O processo de usuário no Adobe Campaign é o seguinte:

1. Criação da entrega
1. Como escolher o público-alvo
1. Definição do conteúdo
1. Definição da data de contato
1. Geração do arquivo

## Recommendations {#recommendations}

### Direct mail providers {#direct-mail-providers}

Primeiro, você precisa entrar em contato com seu provedor de mala direta e coletar suas recomendações. Identifique as informações de perfil que devem ser incluídas no arquivo de extração para que possam personalizar a comunicação e enviá-la ao público-alvo. Por exemplo, o nome e o sobrenome, o endereço postal, um código promocional etc. These fields are the ones that you will add in the [Defining the extraction](../../channels/using/defining-the-direct-mail-content.md#defining-the-extraction) tab of the direct mail's content.

Make sure you have checked the **[!UICONTROL Address specified]** box in your profiles' information. Se essa opção for ativada, o perfil será adicionado à meta. It is not, it will excluded by a typology rule during the preparation phase (see [Creating the direct mail](../../channels/using/creating-the-direct-mail.md)). Durante a importação de perfil, não esqueça de atualizar esse campo.

![](assets/direct_mail_22.png)

### Postal addresses {#postal-addresses}

When you add the fields to include in the extraction file, the postal address fields are available in the **[!UICONTROL Location]** node.

O Adobe Campaign oferece um conjunto de campos calculados predefinidos que seguem as normalizações de endereços postais mais comuns. The fields are available in the **[!UICONTROL Postal address]** node.

An address can contain up to six lines by default: the first calculated field ( **[!UICONTROL Line 1]** contains the first name and last name, the next lines contain the postal address (road etc.), and the last line contains the ZIP/Postal code and town or city.

![](assets/direct_mail_23.png)

