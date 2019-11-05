---
title: Criação de um modelo multilíngue
description: Saiba como definir e executar entregas de email/SMS multilíngues por meio de uma única entrega com base no idioma preferencial de seus clientes segmentados automaticamente. Relatório sobre o desempenho de cada entrega até os níveis de idioma e individual.
page-status-flag: nunca ativado
uuid: 7a2cd5f7-c0fc-4825-a770-a62816c66b3f
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: referência
topic-tags: gerenciar modelos
discoiquuid: 064c5c4a-f579-4bab-adf3-51c92eb4518f
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Criação de um modelo multilíngue{#creating-a-multilingual-template}

Um modelo multilíngue é um modelo específico para gerenciar mensagens multilíngues.

Esse tipo de modelo está disponível para mensagens **de** email e SMS e pode ser usado no modo independente, em um fluxo de trabalho ou em uma entrega recorrente.

Nos modelos de recursos multilíngues, o gerenciamento de idiomas é baseado em variantes. **Cada variante representa um idioma.**

O Adobe Campaign Standard pode configurar no máximo 40 variantes.

O Adobe Campaign vem com um idioma padrão definido como EN. O idioma padrão pode ser alterado para outra variante, mas nunca deve ser excluído.

Durante a criação do modelo, é possível adicionar o número de variantes correspondente ao número de idiomas necessários na mensagem.

Para executar a criação de SMS ou modelo de email, siga as etapas:

1. Duplique um modelo multilíngue existente (SMS ou Email).

   ![](assets/multi_template_duplicate.png)

   >[!NOTE]
   >
   >Você também pode modificar um modelo padrão existente em um modelo multilíngue clicando no **[!UICONTROL Initialize content variant]** botão nas propriedades do modelo.

1. Modifique as propriedades para personalizar rótulos, rastreamento etc.
1. Modifique o número de variantes desejadas clicando no bloco variantes. A janela de variantes é exibida

   ![](assets/multi_template_variants.png)

   É possível adicionar ou remover variantes. Para adicionar uma variante, preencha a **[!UICONTROL New content variant]** janela.

   ![](assets/multi_template_newvariant.png)

   >[!NOTE]
   >
   >Não exclua a variante "padrão", pois é a variante enviada para perfis sem um parâmetro de idioma preferencial concluído.

1. Personalize a variante do rótulo, se necessário, e clique em confirmar.
1. Também é possível adicionar diretamente o conteúdo para cada variante.

Agora você está pronto para criar um email ou uma mensagem SMS com base nesse modelo multilíngue.

**Tópicos relacionados:**

* [Criação de um email multilíngue](../../channels/using/creating-a-multilingual-email.md)
* [Criar perfis](../../audiences/using/creating-profiles.md)

