---
title: Modelos de mensagens multilíngues
description: Saiba como definir e executar entregas de email/SMS multilíngues por meio de uma única entrega com base no idioma preferencial de seus clientes segmentados automaticamente. Relatório sobre o desempenho de cada entrega até os níveis de idioma e individual.
page-status-flag: never-activated
uuid: 7a2cd5f7-c0fc-4825-a770-a62816c66b3f
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: managing-templates
discoiquuid: 064c5c4a-f579-4bab-adf3-51c92eb4518f
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ff3b41589f47e7697a69bb68824aefd4d9036793

---


# Modelos de mensagens multilíngues {#multilingual-messages-template}

Um modelo multilíngue é um modelo específico para gerenciar mensagens multilíngues. Este tipo de modelo está disponível para mensagens **de **** Email **e** SMS e é utilizável no modo independente, em um fluxo de trabalho ou em uma entrega recorrente.

Nos modelos de recursos multilíngues, o gerenciamento de idiomas é baseado em variantes. **Cada variante representa um idioma**. O Adobe Campaign Standard pode configurar no máximo 40 variantes.

O Adobe Campaign vem com um idioma padrão, definido como **EN**. O idioma padrão pode ser alterado para outra variante, mas nunca deve ser excluído.

Durante a criação do modelo, é possível adicionar o número de variantes correspondente ao número de idiomas necessários na mensagem.

Para executar a criação de SMS ou modelo de email, siga estas etapas:

1. Duplique um modelo multilíngue existente (SMS ou Email).

   ![](assets/multi_template_duplicate.png)

   >[!NOTE]
   >
   >Você também pode modificar um modelo padrão existente em um modelo multilíngue clicando no **[!UICONTROL Initialize content variant]**botão nas propriedades do modelo.

1. Modifique as propriedades para personalizar rótulos, rastreamento etc.
1. Modifique o número de variantes desejadas clicando no bloco variantes. A janela de variantes é exibida

   ![](assets/multi_template_variants.png)

   É possível adicionar ou remover variantes. Para adicionar uma variante, preencha a **[!UICONTROL New content variant]**janela.

   ![](assets/multi_template_newvariant.png)

   >[!NOTE]
   >
   >Não exclua a variante &quot;padrão&quot;, pois é a variante enviada para perfis sem um parâmetro de idioma preferencial concluído.

1. Personalize a variante do rótulo, se necessário, e clique em **[!UICONTROL Confirm]**.
1. Também é possível adicionar diretamente o conteúdo para cada variante.

Agora você está pronto para criar um email ou uma mensagem SMS com base nesse modelo multilíngue.

**Tópicos relacionados:**

* [Criação de um email multilíngue](../../channels/using/creating-a-multilingual-email.md)
* [Criar perfis](../../audiences/using/creating-profiles.md)
