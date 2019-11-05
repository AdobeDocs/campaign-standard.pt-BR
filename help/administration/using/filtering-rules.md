---
title: Regras de filtragem
description: Use as regras de filtragem para refinar o público-alvo das mensagens.
page-status-flag: nunca ativado
uuid: ed3eea62-3a47-4318-ae22-d82aa857448f
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: administração
content-type: referência
topic-tags: regras de trabalho com tipologia
discoiquuid: 7ddaf36c-74e6-4501-b3eb-3d03f005aaa6
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Regras de filtragem{#filtering-rules}

As regras de filtragem permitem que você exclua uma parte do destino da mensagem de acordo com critérios definidos em uma consulta, como perfis em quarentena ou perfis que já receberam um determinado número de emails.

Por exemplo, você pode filtrar os assinantes de boletins informativos para que os assinantes com menos de 18 anos nunca recebam comunicações.

## Criando uma regra de filtragem {#creating-a-filtering-rule}

1. Crie uma regra de **tipologia de filtragem** , que pode ser aplicada em todos os canais de comunicação.

   ![](assets/typology_create-rule.png)

1. Na **[!UICONTROL Filtering criteria]** guia, selecione as assinaturas na **[!UICONTROL Subscription]** categoria.

   ![](assets/typology_create-rule-subscription.png)

1. Na **[!UICONTROL Explorer]** guia do editor de consultas, arraste e solte o **[!UICONTROL Subscriber]** nó na parte principal da tela.

   ![](assets/typology_create-rule-subscriber.png)

1. Selecione o **[!UICONTROL Age]** campo e defina as condições de filtragem para que a idade dos assinantes seja 18 ou superior.

   ![](assets/typology_create-rule-age.png)

1. Na **[!UICONTROL Typologies]** guia, vincule essa regra a uma tipologia.

   ![](assets/typology_create-rule-typology.png)

1. Verifique se a tipologia em questão está selecionada no modelo de entrega que você deseja usar.

   ![](assets/typology_template.png)

   >[!NOTE]
   >
   >Para acessar os modelos de entrega, selecione **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** no menu de navegação, que pode ser acessado pelo logotipo do Adobe Campaign.

Sempre que esta regra for usada em uma mensagem, os assinantes considerados menores serão automaticamente excluídos.

## Restrição da aplicabilidade de uma regra de filtragem {#restricting-the-applicability-of-a-filtering-rule}

Você pode restringir a aplicabilidade de uma regra de filtragem de acordo com a mensagem a ser enviada.

1. Na **[!UICONTROL Application criteria]** guia da regra de tipologia, desmarque a opção **[!UICONTROL Apply the rule on all deliveries]** , que está ativada por padrão.

   ![](assets/typology_limit.png)

1. Use o editor de consultas para definir um filtro. Por exemplo, você pode aplicar a regra somente em mensagens cujo rótulo comece com uma determinada palavra ou cuja ID contenha certas letras.

   ![](assets/typology_limit-rule.png)

Nesse caso, a regra é aplicada somente às mensagens que correspondem aos critérios definidos.

## Regras padrão de exclusão de entrega {#default-deliverability-exclusion-rules}

Two filtering rules are available by default: **[!UICONTROL Exclusion of addresses]** ( **[!UICONTROL addressExclusions]** ) and **[!UICONTROL Exclusion of domains]** ( **[!UICONTROL domainExclusions]** ). Durante a análise de e-mail, essas regras comparam os endereços de e-mail do recipient com os endereços proibidos ou nomes de domínio contidos em uma lista de supressão global criptografada gerenciada na instância de entrega. Se houver algum positivo, a mensagem não será enviada para esse recipient.

Isso é para evitar a inclusão na blacklist devido a atividades mal-intencionadas, especialmente o uso de um Spamtrap. Por exemplo, se um Spamtrap for usado para se inscrever em um dos seus formulários Web, um e-mail de confirmação será enviado automaticamente para esse Spamtrap e isso resultará no endereço utilizado sendo automaticamente incluído na blacklist.

>[!NOTE]
>
>Os endereços e os nomes de domínio contidos na lista de supressão global estão ocultos. Somente o número de recipients excluídos é indicado nos logs de análise de delivery.

