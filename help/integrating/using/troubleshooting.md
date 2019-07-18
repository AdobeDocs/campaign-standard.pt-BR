---
title: Solução de problemas
seo-title: Solução de problemas
description: Solução de problemas
seo-description: Saiba como solucionar problemas ao compartilhar recursos.
page-status-flag: nunca ativado
uuid: 1 c 764 dd 8-e 09 f -4 e 8 e -9 ccd -88 ab 3 d 714284
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
discoiquuid: c 28 e 1 d 90-8074-4127-a 6 fc-ed 39 d 69 cdb 19
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 698466596fdacd005dc4d72b8071208c8c39f77d

---


# Troubleshooting{#troubleshooting}

Podem ser encontrados erros ao usar a integração com o Audience Manager ou o serviço principal Pessoas.

Nesse caso, verifique se os seguintes elementos estão configurados corretamente:

* **Contas externas**

   In **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL External accounts]**, make sure that the following external S3 accounts are correctly configured. Os servidores S 3 mencionados devem ter sido configurados durante o provisionamento.

   * **[!UICONTROL importSharedAudience]**: S 3 account dedicada à importação de públicos-alvo.
   * **[!UICONTROL exportSharedAudience]**: S 3 account dedicada à exportação de públicos-alvo.

* **Fontes de dados compartilhadas**

   In **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Shared Data Sources]**, check that the shared data source is set properly.

   **[!UICONTROL Priority]** é usado quando há várias fontes de dados definidas. A prioridade determina qual fonte de dados será usada para corresponder com alias recebidos na ordem definida. **[!UICONTROL Priority]** é necessário apenas para a implementação Acionadores.

   Verifique se a tecla de reconciliação está correta. É o valor hash/criptografado desse campo que é usado para exportar e importar públicos-alvo.

   No caso de hash ou criptografia da ID declarada, verifique se os mesmos parâmetros de parâmetros/criptografia são usados em seu site.

   Apenas um algoritmo de criptografia é suportado: AES no modo CBC com tamanho de chave de 128, 192 ou 256 bits, com preenchimento PKCS.

   Se o algoritmo de criptografia AES estiver selecionado, os seguintes campos adicionais devem estar definidos corretamente:

   * **Chave de criptografia** para AES
   * **Criptografia IV** (Vetor de inicialização) para AES
   * **Canal** (Email/SMS/Outro): Este campo permite descriptografar diretamente endereços de email e números de SMS. Make sure that the reconciliation key matches the setting of the **Channel** field. Se você selecionar "Outro", essa decodificação específica não ocorrerá e a chave de reconciliação será usada para reconciliar os dados.
   Os públicos-alvo da Experience Cloud podem não ser compartilhados porque o fluxo de trabalho técnico foi interrompido ou pausado. Access the **[!UICONTROL Import shared audience]** workflow by clicking directly the **[!UICONTROL Show ImportShared Audience workflow]** option in your Data source.

Pode ocorrer que alguns dados estejam ausentes ao compartilhar um público-alvo por meio do serviço principal Pessoas ou ao importar um público-alvo. Somente registros de quais a ID (' ID do visitante'ou'ID declarada ') puderam ser conciliados com a dimensão do perfil são transferidos. As IDs dos segmentos de serviços principais de Pessoas não reconhecidas pelo Adobe Campaign não são importadas.
