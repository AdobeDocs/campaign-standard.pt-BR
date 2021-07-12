---
solution: Campaign Standard
product: campaign
title: Regras de filtragem
description: Use as regras de filtragem para refinar o público das mensagens.
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
feature: Regras de tipologia
role: User
level: Intermediate
exl-id: 43e97f3c-ed82-4fcc-ac0d-fcee6a22da35
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '655'
ht-degree: 22%

---

# Regras de filtragem {#filtering-rules}

As regras de filtragem permitem excluir uma parte do público-alvo da mensagem de acordo com critérios definidos em uma consulta, como perfis em quarentena ou perfis que já receberam um determinado número de emails.

## Regras padrão de tipologia de filtragem {#default-filtering-typology-rules}

A tabela abaixo fornece informações sobre regras de filtragem prontas para uso, bem como seus canais relacionados.

| Rótulo | Canal  | Descrição |
| ---------|----------|---------|
| **[!UICONTROL Address not specified]** | Todos | Exclui o público-alvo sem endereço especificado (email, endereço postal etc.) de acordo com o canal selecionado). |
| **[!UICONTROL Address on denylist]** | Todos | Exclui endereços que estão na lista de bloqueios. |
| **[!UICONTROL Duplicate]** | Todos | Exclui duplicatas com base no campo **[!UICONTROL Address]** da população do target. |
| **[!UICONTROL Exclude mobile applications]** | Aplicativo móvel | Exclui assinaturas de aplicativo que não correspondem ao aplicativo móvel definido na mensagem. |
| **[!UICONTROL Exclude mobile applications for In-App]** | No aplicativo | Exclui assinaturas de aplicativo que não correspondem ao aplicativo móvel definido na mensagem (modelo no aplicativo). |
| **[!UICONTROL Exclude mobile applications for In-App broadcast]** | No aplicativo | Exclui assinaturas de aplicativo que não correspondem ao aplicativo móvel definido na mensagem (modelo de transmissão no aplicativo) |
| **[!UICONTROL Exclude mobile applications for Push]** | Aplicativo móvel | Exclui assinaturas de aplicativo que não correspondem ao aplicativo móvel definido na mensagem (para Push) |
| **[!UICONTROL Quarantined address]** | Todos | Exclui endereços em quarentena. |
| **[!UICONTROL Target limited in size]** | Todos | Verifica se o tamanho máximo de delivery foi atingido para o target. Aplica-se a deliveries de correspondência direta com a opção &quot;limite de delivery&quot; ativada. |

Além dessas regras de filtragem padrão, duas regras de exclusão estão disponíveis:

* **[!UICONTROL Exclusion of addresses]** ( **[!UICONTROL addressExclusions]** )
* **[!UICONTROL Exclusion of domains]** ( **[!UICONTROL domainExclusions]** ).

Durante a análise de e-mail, essas regras comparam os endereços de e-mail do recipient com os endereços proibidos ou nomes de domínio contidos em uma lista de supressão global criptografada gerenciada na instância de entrega. Se houver algum positivo, a mensagem não será enviada para esse recipient.

Isso evita a inclusão na lista de bloqueios devido a atividades mal-intencionadas, especialmente o uso de um Spamtrap. Por exemplo, se um Spamtrap for usado para se inscrever em um dos seus formulários web, um email de confirmação será enviado automaticamente para esse Spamtrap e resultará na inclusão automática do endereço utilizado à lista de bloqueios.

>[!NOTE]
>
>Os endereços e os nomes de domínio contidos na lista de supressão global estão ocultos. Somente o número de recipients excluídos é indicado nos logs de análise de delivery.

## Criando uma regra de filtragem {#creating-a-filtering-rule}

Você pode criar suas próprias regras de filtragem de acordo com suas necessidades. Por exemplo, você pode filtrar o público-alvo dos informativos para que os assinantes com menos de 18 anos nunca recebam comunicações.

Para criar uma regra de tipologia de filtragem, siga estas etapas:

1. Crie uma nova regra de tipologia. As principais etapas para criar regras de tipologia são detalhadas em [this section](../../sending/using/managing-typology-rules.md).

1. Selecione o tipo de regra **[!UICONTROL Filtering]** e especifique o canal desejado.

1. Na guia **[!UICONTROL Filtering criteria]**, selecione as assinaturas na categoria **[!UICONTROL Subscription]**.

   ![](assets/typology_create-rule-subscription.png)

1. Na guia **[!UICONTROL Explorer]** do editor de consultas, arraste e solte o nó **[!UICONTROL Subscriber]** na parte principal da tela.

   ![](assets/typology_create-rule-subscriber.png)

1. Selecione o campo **[!UICONTROL Age]** e defina as condições de filtragem para que a idade dos assinantes seja 18 ou superior.

   ![](assets/typology_create-rule-age.png)

1. Na guia **[!UICONTROL Typologies]** , vincule essa regra a uma tipologia.

   ![](assets/typology_create-rule-typology.png)

1. Certifique-se de que a tipologia esteja selecionada no delivery ou template do delivery que deseja usar. Para obter mais informações, consulte [esta seção](../../sending/using/managing-typologies.md#applying-typologies-to-messages).

   ![](assets/typology_template.png)

Sempre que essa regra for usada em uma mensagem, os assinantes considerados menores serão excluídos automaticamente.

## Configuração do contexto de direcionamento das regras de filtragem {#configuring-filtering-rules-targeting-context}

O Campaign Standard permite configurar as dimensões **Direcionamento** e **Filtragem** para usar, dependendo dos dados que deseja direcionar.

Para fazer isso, abra as propriedades da regra de tipologia e acesse a seção **[!UICONTROL Advanced information]** .

Por padrão, a filtragem é realizada no **[!UICONTROL Profiles]**. Por exemplo, se a regra for direcionada a um aplicativo móvel, **[!UICONTROL Filtering dimension]** poderá ser alterado para **[!UICONTROL Subscriptions to an application]**.

![](assets/typology_rule-order_2.png)

## Restrição da aplicabilidade de uma regra de filtragem {#restricting-the-applicability-of-a-filtering-rule}

Você pode restringir a aplicabilidade de uma regra de filtragem de acordo com a mensagem a ser enviada.

1. Na guia **[!UICONTROL Application criteria]** da regra de tipologia, desmarque a opção **[!UICONTROL Apply the rule on all deliveries]**, que está habilitada por padrão.

   ![](assets/typology_limit.png)

1. Use o editor de consultas para definir um filtro. Por exemplo, você pode aplicar a regra somente em mensagens cujo rótulo começa com uma determinada palavra ou cuja ID contém certas letras.

   ![](assets/typology_limit-rule.png)

Nesse caso, a regra é aplicada apenas nas mensagens que correspondem aos critérios definidos.
