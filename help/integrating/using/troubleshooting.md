---
title: Solução de problemas de integração
description: Saiba como solucionar problemas ao compartilhar recursos.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 5882ada6-dff4-4fd1-a433-0eb31570f73c
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 18%

---

# Solução de problemas{#troubleshooting}

Podem ser encontrados erros ao usar a integração com o Audience Manager ou o Serviço principal de pessoas.

Nesse caso, verifique se os seguintes elementos estão configurados corretamente:

* **Contas externas**

  Entrada **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL External accounts]**, verifique se as contas externas S3 a seguir estão configuradas corretamente. Os servidores S3 mencionados devem ter sido configurados durante o provisionamento.

   * **[!UICONTROL importSharedAudience]**: conta S3 dedicada à importação de públicos.
   * **[!UICONTROL exportSharedAudience]**: conta S3 dedicada à exportação de públicos.

* **Fontes de dados compartilhadas**

  Entrada **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]**, verifique se a fonte de dados compartilhada está definida corretamente.

  **[!UICONTROL Priority]** é usada quando você tem várias fontes de dados definidas. A prioridade decide qual fonte de dados será usada para corresponder ao alias recebido na ordem definida. **[!UICONTROL Priority]** é necessário somente para a implementação de Acionadores.

  Verifique se a chave de reconciliação está correta. É o valor com hash/criptografado desse campo usado para exportar e importar públicos.

  Em caso de hash ou criptografia da ID declarada, verifique se os mesmos parâmetros/algoritmos de criptografia são usados em seu site.

  Somente um algoritmo de criptografia é suportado: AES no modo CBC com um tamanho de chave de 128, 192 ou 256 bits, com preenchimento PKCS.

  Se o algoritmo de criptografia AES for selecionado, os seguintes campos adicionais deverão ser definidos corretamente:

   * **Chave de criptografia** para AES
   * **Encryption IV** (Vetor de inicialização) para AES
   * **Canal** (Email/SMS/Outro): esse campo permite descriptografar endereços de email e números SMS diretamente. Verifique se a chave de reconciliação corresponde à configuração da **Canal** campo. Se você selecionar &quot;Outros&quot;, essa descriptografia específica não ocorrerá e a chave de reconciliação será usada para reconciliar os dados.

  Os públicos-alvo do Experience Cloud podem não ser compartilhados porque o fluxo de trabalho técnico foi interrompido ou pausado. Acesse o **[!UICONTROL Import shared audience]** fluxo de trabalho clicando diretamente no link **[!UICONTROL Show ImportShared Audience workflow]** na sua fonte de dados.

Alguns dados podem faltar ao compartilhar um público através do Serviço principal de pessoas ou ao importar um público. Somente registros dos quais a ID (&#39;ID do visitante&#39; ou &#39;ID declarada&#39;) podem ser reconciliadas com a dimensão de perfil são transferidas. Os IDs dos segmentos de Serviço principal de pessoas que não são reconhecidos pelo Adobe Campaign não são importados.
