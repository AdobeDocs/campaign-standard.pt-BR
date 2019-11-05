---
title: Solução de problemas
description: Saiba como solucionar problemas ao compartilhar recursos.
page-status-flag: nunca ativado
uuid: 1c764dd8-e09f-4e8e-9ccd-88ab3d714284
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: integrando
content-type: referência
topic-tags: trabalhar com campanha e público-gerente-ou-público-principal-serviço
discoiquuid: c28e1d90-8074-4127-a6fc-ed39d69cdb19
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Solução de problemas{#troubleshooting}

Erros podem ser encontrados ao usar a integração com o Audience Manager ou o serviço principal de Pessoas.

Nesse caso, verifique se os seguintes elementos estão configurados corretamente:

* **Contas externas**

   Em **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL External accounts]**, verifique se as seguintes contas S3 externas estão configuradas corretamente. Os servidores S3 mencionados devem ter sido configurados durante o provisionamento.

   * **[!UICONTROL importSharedAudience]**: Conta S3 dedicada à importação de públicos.
   * **[!UICONTROL exportSharedAudience]**: Conta S3 dedicada à exportação de públicos-alvo.

* **Fontes de dados compartilhadas**

   Em **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Shared Data Sources]**, verifique se a fonte de dados compartilhada está definida corretamente.

   **[!UICONTROL Priority]** é usada quando você tem várias fontes de dados definidas. A prioridade decide qual fonte de dados será usada para corresponder ao alias recebido na ordem definida. **[!UICONTROL Priority]** só é necessário para a implementação de Acionadores.

   Verifique se a chave de reconciliação está correta. É o valor com hash/criptografado desse campo que é usado para exportar e importar públicos.

   Em caso de hash ou criptografia da ID declarada, verifique se os mesmos parâmetros/algoritmos de criptografia são usados no site.

   Somente um algoritmo de criptografia é suportado: AES no modo CBC com um tamanho de chave de 128, 192 ou 256 bits, com preenchimento PKCS.

   Se o algoritmo de criptografia AES for selecionado, os seguintes campos adicionais devem ser definidos corretamente:

   * **Chave** de criptografia para AES
   * **Criptografia IV** (vetor de inicialização) para AES
   * **Canal** (Email/SMS/Outro): Este campo permite descriptografar diretamente endereços de email e números de SMS. Verifique se a chave de reconciliação corresponde à configuração do campo **Canal** . Se você selecionar "Outro", essa descriptografia específica não ocorrerá e a chave de reconciliação será usada para reconciliar os dados.
   Os públicos-alvo da Experience Cloud podem não ser compartilhados porque o fluxo de trabalho técnico foi interrompido ou pausado. Acesse o **[!UICONTROL Import shared audience]** fluxo de trabalho clicando diretamente na opção **[!UICONTROL Show ImportShared Audience workflow]** na sua Fonte de dados.

Alguns dados podem faltar ao compartilhar um público através do Serviço principal de pessoas ou ao importar um público. Somente registros dos quais a ID ('ID do visitante' ou 'ID declarada') podem ser reconciliadas com a dimensão de perfil são transferidas. Os IDs dos segmentos de Serviço principal de pessoas que não são reconhecidos pelo Adobe Campaign não são importados.
