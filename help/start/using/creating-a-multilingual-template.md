---
title: Criação de um modelo multilíngue
seo-title: Criação de um modelo multilíngue
description: Criação de um modelo multilíngue
seo-description: Saiba como definir e executar entregas de email/SMS multilíngues por meio de uma única entrega com base no idioma preferencial do cliente segmentado automaticamente. Informe o desempenho de cada entrega para o idioma e níveis individuais.
page-status-flag: nunca ativado
uuid: 7 a 2 cd 5 f 7-c 0 fc -4825-a 770-a 62816 c 66 b 3 f
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: gerenciando modelos
discoiquuid: 064 c 5 c 4 a-f 579-4 bab-adf 3-51 c 92 eb 4518 f
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Creating a multilingual template{#creating-a-multilingual-template}

Um modelo multilíngue é um modelo específico para gerenciar mensagens multilíngues.

This kind of template is available for **Email and SMS messages** and useable in standalone mode, within a workflow or in a recurring delivery.

Nos modelos de recursos multilíngues, o gerenciamento de idiomas é baseado em variantes. **Cada variação representa um idioma.**

O Adobe Campaign Standard é capaz de configurar no máximo 40 variantes.

O Adobe Campaign vem com um idioma padrão definido como EN. O idioma padrão pode ser alterado para outra variante, mas nunca deve ser excluído.

Durante a criação do modelo, é possível adicionar o número de variantes que correspondem ao número de idiomas necessários na mensagem.

Para executar a criação de SMS ou modelo de e-mail, siga as etapas:

1. Duplicar um modelo multilíngue existente (SMS ou Email).

   ![](assets/multi_template_duplicate.png)

   >[!NOTE]
   >
   >You can also modify an existing standard template in a multilingual template by clicking on the **[!UICONTROL Initialize content variant]** button in the template properties.

1. Modifique as propriedades para personalizar rótulos, rastreamento etc.
1. Modifique o número de variantes desejados clicando no bloco variante. A janela variantes é exibida

   ![](assets/multi_template_variants.png)

   Você pode adicionar ou remover variantes. To add a variant, complete the **[!UICONTROL New content variant]** window.

   ![](assets/multi_template_newvariant.png)

   >[!NOTE]
   >
   >Não exclua a variante "padrão", pois é a variante enviada para perfis sem um parâmetro de idioma preferencial concluído.

1. Personalize a variante de rótulo se necessário e clique em confirmar.
1. Você também pode adicionar diretamente o conteúdo para cada variação.

Agora você está pronto para criar um email ou uma mensagem SMS com base neste modelo multilíngue.

**Tópicos relacionados:**

* [Criação de um email multilíngue](../../channels/using/creating-a-multilingual-email.md)
* [Criação de perfis](../../audiences/using/creating-profiles.md)

