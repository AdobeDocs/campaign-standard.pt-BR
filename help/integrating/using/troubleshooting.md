---
solution: Campaign Standard
product: campaign
title: Solução de problemas
description: Saiba como solucionar problemas ao compartilhar recursos.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 18%

---


# Solução de problemas{#troubleshooting}

Erros podem ser encontrados ao usar a integração com o Audience Manager ou o serviço principal de Pessoas.

Nesse caso, verifique se os seguintes elementos estão configurados corretamente:

* **Contas externas**

   In **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL External accounts]**, make sure that the following external S3 accounts are correctly configured. Os servidores S3 mencionados devem ter sido configurados durante o provisionamento.

   * **[!UICONTROL importSharedAudience]**: Conta S3 dedicada à importação de audiências.
   * **[!UICONTROL exportSharedAudience]**: Conta S3 dedicada à exportação de audiências.

* **Fontes de dados compartilhadas**

   In **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]**, check that the shared data source is set properly.

   **[!UICONTROL Priority]** é usada quando você tem várias fontes de dados definidas. A prioridade decide qual fonte de dados será usada para corresponder ao alias recebido na ordem definida. **[!UICONTROL Priority]** só é necessário para a implementação de Acionadores.

   Verifique se a chave de reconciliação está correta. É o valor com hash/criptografado desse campo que é usado para exportar e importar audiências.

   Em caso de hash ou criptografia da ID declarada, verifique se os mesmos parâmetros/algoritmos de criptografia são usados em seu site.

   Somente um algoritmo de criptografia é suportado: AES no modo CBC com um tamanho de chave de 128, 192 ou 256 bits, com preenchimento PKCS.

   Se o algoritmo de criptografia AES for selecionado, os seguintes campos adicionais devem ser definidos corretamente:

   * **Chave** de criptografia para AES
   * **Criptografia IV** (vetor de inicialização) para AES
   * **Canal** (Email/SMS/Outro): Este campo permite descriptografar diretamente endereços de email e números de SMS. Verifique se a chave de reconciliação corresponde à configuração do campo **Canal** . Se você selecionar &quot;Outro&quot;, essa descriptografia específica não ocorrerá e a chave de reconciliação será usada para reconciliar os dados.

   audiências Experience Cloud podem não ser compartilhadas porque o fluxo de trabalho técnico foi interrompido ou pausado. Acesse o **[!UICONTROL Import shared audience]** fluxo de trabalho clicando diretamente na opção **[!UICONTROL Show ImportShared Audience workflow]** na sua Fonte de dados.

Alguns dados podem faltar ao compartilhar um público através do Serviço principal de pessoas ou ao importar um público. Somente registros dos quais a ID (&#39;ID do visitante&#39; ou &#39;ID declarada&#39;) podem ser reconciliadas com a dimensão de perfil são transferidas. Os IDs dos segmentos de Serviço principal de pessoas que não são reconhecidos pelo Adobe Campaign não são importados.
