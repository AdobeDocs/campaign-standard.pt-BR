---
title: Modelos de mensagens multilíngues
description: Saiba como definir e executar entregas de emails/SMS multilíngues em uma única entrega com base no idioma preferencial dos clientes segmentados automaticamente. Relate o desempenho de cada entrega até os níveis de idioma e pessoa.
audience: start
content-type: reference
topic-tags: managing-templates
feature: Multilingual Messages
role: User
level: Intermediate
exl-id: 3d869f31-7dfb-4546-aba5-80a2787e00be
TQID: 'https://experienceleague.adobe.com/TsDW-1w3j0-CvsR0R0V-KnUOc4VahG7iCg46bgCyBJ0'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: c858a28b-ea19-49b0-8d48-828717fad89c
    internal-label: Prepare and test messages
subfeature_v2:
  - id: fa669864-b1c7-4f0a-8d32-9480adcbe6a2
    internal-label: Multilingual messages
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '295'
ht-degree: 100%
---
# Modelos de mensagens multilíngues {#multilingual-messages-template}

Um modelo multilíngue é específico para gerenciar mensagens multilíngues. Esse tipo de modelo está disponível para mensagens de **email** e **SMS** e pode ser usado no modo independente, em um fluxo de trabalho ou em uma entrega recorrente.

Nos modelos de recursos multilíngues, o gerenciamento de idiomas é baseado em variantes. **Cada variante representa um idioma**. O Adobe Campaign Standard pode configurar, no máximo, 40 variantes.

O Adobe Campaign contém um idioma padrão, definido como **EN**. O idioma padrão pode ser alterado para outra variante, mas nunca deve ser excluído.

Durante a criação do modelo, é possível adicionar a quantidade de variantes correspondentes ao número de idiomas necessários na mensagem.

Para criar um modelo de SMS ou de email, siga estas etapas:

1. Duplique um modelo multilíngue (SMS ou Email).

   ![](assets/multi_template_duplicate.png)

   >[!NOTE]
   >
   >Você também pode modificar um modelo padrão em um modelo multilíngue clicando no botão **[!UICONTROL Initialize content variant]** nas propriedades do modelo.

1. Modifique as propriedades para personalizar o rótulo, o rastreamento etc.

1. Modifique o número de variantes desejadas clicando no bloco de variantes. A janela a seguir é exibida.

   ![](assets/multi_template_variants.png)

   É possível adicionar ou remover variantes. Para adicionar uma variante, preencha a janela **[!UICONTROL New content variant]**.

   ![](assets/multi_template_newvariant.png)

   >[!NOTE]
   >
   >Não exclua a variante “padrão”, pois ela é enviada para os perfis sem parâmetro de idioma preferencial preenchido.

1. Personalize a variante de rótulo, se necessário, e clique em **[!UICONTROL Confirm]**.

1. Você também pode adicionar diretamente o conteúdo de cada variante.

Agora você está pronto para criar uma mensagem de email ou SMS com base nesse modelo multilíngue.

**Tópicos relacionados:**

* [Criação de um email multilíngue](../../channels/using/creating-a-multilingual-email.md)
* [Criação de perfis](../../audiences/using/creating-profiles.md)
