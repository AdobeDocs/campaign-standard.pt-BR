---
solution: Campaign Standard
product: campaign
title: Sobre correspondência direta
description: Descubra as principais especificidades do canal de correspondência direta no Adobe Campaign.
audience: channels
content-type: reference
topic-tags: direct-mail
context-tags: delivery,directMailContent,back;deliveryCreation,wizard
feature: Direct Mail
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 97%

---


# Sobre correspondência direta{#about-direct-mail}

Correspondência direta é um canal offline com o qual é possível personalizar e gerar o arquivo exigido por provedores de correspondência direta. Ela oferece a possibilidade de misturar canais online e offline nas jornadas do seu cliente.

>[!NOTE]
>
>Este recurso é opcional. Verifique o contrato de licença. A função **[!UICONTROL Export]** é necessária para usar a correspondência direta. Entre em contato com o administrador.

Os canais online permitem que você crie mensagens (email, SMS, delivery de aplicativo móvel, etc.) e envie-as para seu público diretamente do Adobe Campaign. Com canais offline, é diferente. Quando você prepara um delivery direto de correspondência direta, o Adobe Campaign gera um arquivo incluindo todos os perfis do target e as informações de contato escolhidas (endereço postal por exemplo). Você poderá enviar esse arquivo para seu provedor de correspondência direta que irá cuidar realmente do envio.

A seção a seguir explica como criar e gerar um delivery de correspondência direta de uma só vez. Você também pode incluir uma atividade de correspondência direta em um fluxo de trabalho para orquestrar campanhas combinando canais online e offline. Para mais informações, consulte o guia [Fluxos de trabalho](../../automating/using/get-started-workflows.md).

O processo do usuário no Adobe Campaign é o seguinte:

1. Criação de delivery
1. Escolha do público
1. Definição do conteúdo
1. Definição da data de contato
1. Geração do arquivo

**Tópicos relacionados:**

* [Caso de uso: Junção de deliveries de email e de correspondência direta](../../automating/using/coupling-email-direct-mail.md)

## Recomendações {#recommendations}

### Provedores de correspondência direta {#direct-mail-providers}

Primeiro, você precisa entrar em contato com o provedor de correspondência direta e coletar as recomendações desse provedor. Identifique quais informações de perfil precisam ser incluídas no arquivo de extração para que o provedor possa personalizar a comunicação e enviá-la para o público. Por exemplo, nome e sobrenome, endereço postal, um código promocional etc. Esses são os campos que você adicionará na guia [Definição da extração](../../channels/using/defining-the-direct-mail-content.md#defining-the-extraction) do conteúdo da correspondência direta.

Confirme que você marcou a caixa **[!UICONTROL Address specified]** nas informações dos perfis. Se essa opção estiver ativada, o perfil será adicionado ao público alvo. Se não estiver, o perfil será excluído por uma regra de tipologia durante a fase de preparação (consulte [Criação da correspondência direta](../../channels/using/creating-the-direct-mail.md)). Durante a importação do perfil, não se esqueça de atualizar este campo.

![](assets/direct_mail_22.png)

### Endereços postais {#postal-addresses}

Ao adicionar os campos que serão incluídos no arquivo de extração, os campos de endereço postal ficam disponíveis no nó **[!UICONTROL Location]**.

O Adobe Campaign oferece um conjunto de campos calculados predefinidos que seguem as normalizações mais comuns de endereço postal. Os campos estão disponíveis no nó **[!UICONTROL Postal address]**.

Um endereço pode conter até seis linhas por padrão: o primeiro campo calculado (**[!UICONTROL Line 1]**) contém o nome e o sobrenome; as linhas seguintes contêm o endereço postal (rua etc.); e a última linha contém o CEP e a cidade.

![](assets/direct_mail_23.png)
