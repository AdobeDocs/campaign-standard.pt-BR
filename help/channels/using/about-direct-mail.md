---
title: Sobre o correio direto
description: Descubra as principais especificidades do canal de mala direta no Adobe Campaign.
page-status-flag: nunca ativado
uuid: 24add992-2efe-4b73-81c9-cda3e921ab16
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: canais
content-type: referência
topic-tags: correio direto
discoiquuid: e1fbf39c-9c30-493c-8322-9c71e18ce98c
context-tags: entrega,directMailContent,back;delivery,assistente
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Sobre o correio direto{#about-direct-mail}

A mala direta  é um canal offline que permite personalizar e gerar o arquivo exigido por provedores de mala direta. Ela oferece a possibilidade de misturar canais online e offline nas jornadas do cliente.

>[!NOTE]
>
>Este recurso é opcional. Verifique o contrato de licença. A função **[!UICONTROL Export]** é necessária para usar a mala direta. Entre em contato com o administrador.

Os canais online permitem que você crie mensagens (email, SMS, delivery de aplicativo móvel, etc.) e envie-as para seu público diretamente do Adobe Campaign. Com canais offline, é diferente. Quando você prepara um delivery direto de mala direta, o Adobe Campaign gera um arquivo incluindo todos os perfis do target e as informações de contato escolhidas (endereço postal por exemplo). Você poderá enviar esse arquivo para seu provedor de mala direta que irá cuidar realmente do envio.

A seção a seguir explica como criar e gerar uma entrega única de mala direta. Você também tem a possibilidade de incluir uma atividade de mala direta em um fluxo de trabalho para orquestrar campanhas que combinam canais online e offline. For more on this, refer to the [Workflows](../../automating/using/workflow-data-and-processes.md) guide.

O processo do usuário no Adobe Campaign é o seguinte:

1. Criação de delivery
1. Escolhendo o público-alvo
1. Definição do conteúdo
1. Definição da data de contato
1. Gerando o arquivo

## Recomendações {#recommendations}

### Provedores de mala direta {#direct-mail-providers}

Primeiro, você precisa alcançar seu provedor de mala direta e coletar suas recomendações. Identifique quais informações de perfil devem ser incluídas no arquivo de extração para que possam personalizar a comunicação e enviá-la para o público-alvo. Por exemplo, o nome e sobrenome, o endereço postal, um código promocional etc. Esses campos são os que você adicionará na guia [Definição da extração](../../channels/using/defining-the-direct-mail-content.md#defining-the-extraction) do conteúdo da mala direta.

Verifique se você marcou a **[!UICONTROL Address specified]** caixa nas informações de seus perfis. Se essa opção estiver ativada, o perfil será adicionado ao destino. Não está, será excluído por uma regra de tipologia durante a fase de preparação (consulte [Criação da correspondência](../../channels/using/creating-the-direct-mail.md)direta). Durante a importação do perfil, não se esqueça de atualizar este campo.

![](assets/direct_mail_22.png)

### Endereços postais {#postal-addresses}

Quando você adiciona os campos a serem incluídos no arquivo de extração, os campos de endereço postal estão disponíveis no **[!UICONTROL Location]** nó.

O Adobe Campaign oferece um conjunto de campos calculados predefinidos que seguem as normalizações mais comuns de endereço postal. Os campos estão disponíveis no **[!UICONTROL Postal address]** nó.

An address can contain up to six lines by default: the first calculated field ( **[!UICONTROL Line 1]** contains the first name and last name, the next lines contain the postal address (road etc.), and the last line contains the ZIP/Postal code and town or city.

![](assets/direct_mail_23.png)

