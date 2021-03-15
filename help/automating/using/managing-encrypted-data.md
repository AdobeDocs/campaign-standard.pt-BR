---
solution: Campaign Standard
product: campaign
title: Gerenciamento de dados criptografados
description: Saiba como gerenciar dados criptografados.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Fluxos de trabalho
role: Arquiteto de dados
level: Experienciado
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '934'
ht-degree: 53%

---


# Gerenciamento de dados criptografados {#managing-encrypted-data}

## Sobre os estágios de pré-processamento {#about-preprocessing-stages}

Em alguns casos, os dados que você deseja importar Servidores do Campaign podem precisar ser criptografados, por exemplo, se contiverem dados PII.

Para poder criptografar dados de saída ou descriptografar dados de entrada, você precisa gerenciar chaves GPG usando o [Painel de controle](https://docs.adobe.com/content/help/pt-BR/control-panel/using/instances-settings/gpg-keys-management.html).

>[!NOTE]
>
>O Painel de controle do Campaign está disponível para todos os clientes hospedados no AWS (exceto para clientes que hospedam suas instâncias de marketing no local).

Se você não estiver qualificado para usar o Painel de controle do Campaign, será necessário entrar em contato com o Atendimento ao Cliente do Adobe para que ele forneça à sua instância os comandos de criptografia/descriptografia necessários. Para fazer isso, envie uma solicitação indicando:

* O **label** que será exibido na interface do Campaign para usar o comando. Por exemplo, &quot;Criptografar arquivo&quot;.
* O **comando** para instalar em sua instância.

Depois que a solicitação é processada, os comandos de criptografia / descriptografia estarão disponíveis no campo **[!UICONTROL Pre-processing stage]** das atividades **[!UICONTROL Load file]** e **[!UICONTROL Extract file]**. Você pode usá-los para descriptografar ou criptografar os arquivos que deseja importar ou exportar.

![](assets/preprocessing-encryption.png)

**Tópicos relacionados:**

* [Carregar arquivo](../../automating/using/load-file.md)
* [Extrair arquivo](../../automating/using/extract-file.md)

## Caso de uso: importação de dados criptografados usando uma chave gerada pelo Painel de controle do Campaign {#use-case-gpg-decrypt}

Nesse caso de uso, criaremos um workflow para importar dados que foram criptografados em um sistema externo usando uma chave gerada no Painel de controle do Campaign.

![](assets/do-not-localize/how-to-video.png) [Descubra este recurso no vídeo](#video)

As etapas para executar esse caso de uso são as seguintes:

1. Use o Painel de controle do Campaign para gerar um par de chaves (público/privado). As etapas detalhadas estão disponíveis na [documentação do Painel de controle do Campaign](https://docs.adobe.com/content/help/en/control-panel/using/instances-settings/gpg-keys-management.html#decrypting-data).

   * A chave pública será compartilhada com o sistema externo, que a usará para criptografar os dados que serão enviados para o Campaign.
   * A chave privada será usada pelo Campaign para descriptografar os dados criptografados recebidos.

   ![](assets/gpg_generate.png)

1. No sistema externo, use a chave pública baixada do Painel de controle do Campaign para criptografar os dados que serão importados para o Campaign Standard.

1. No Campaign Standard, crie um workflow para importar os dados criptografados e descriptografá-los usando a chave privada que foi instalada por meio do Painel de controle do Campaign. Para fazer isso, criaremos um workflow da seguinte maneira:

   ![](assets/gpg_workflow.png)

   * **[!UICONTROL Transfer file]** atividade : Transfere o arquivo de uma fonte externa para o Campaign. Neste exemplo, queremos transferir o arquivo de um servidor SFTP.
   * Atividade **[!UICONTROL Load file]**: carrega os dados do arquivo no banco de dados e os decodifica usando a chave privada gerada no Painel de controle do Campaign.

1. Abra a atividade **[!UICONTROL Transfer file]** e configure-a de acordo com suas necessidades. Os conceitos globais sobre como configurar a atividade estão disponíveis [nesta seção](../../automating/using/load-file.md).

   Na guia **[!UICONTROL Protocol]** , especifique os detalhes sobre o servidor sftp e o arquivo .gpg criptografado que deseja transferir.

   ![](assets/gpg_transfer.png)

1. Abra a atividade **[!UICONTROL Load file]** e configure-a de acordo com suas necessidades. Os conceitos globais sobre como configurar a atividade estão disponíveis [nesta seção](../../automating/using/load-file.md).

   Adicione um estágio de pré-processamento à atividade para descriptografar os dados recebidos. Para fazer isso, selecione a opção **[!UICONTROL Decryption GPG]** na lista.

   >[!NOTE]
   >
   >Observe que não é necessário especificar a chave privada a ser usada para descriptografar os dados. A chave privada é armazenada no Painel de controle do Campaign, que detecta automaticamente a chave a ser usada para descriptografar o arquivo.

   ![](assets/gpg_load.png)

1. Clique em **[!UICONTROL OK]** para confirmar a configuração da atividade.

1. Agora você pode executar o workflow.

## Caso de uso: criptografar e exportar dados usando uma chave instalada no Painel de controle do Campaign {#use-case-gpg-encrypt}

Nesse caso de uso, criaremos um workflow para criptografar e exportar dados usando uma chave instalada no Painel de controle do Campaign.

![](assets/do-not-localize/how-to-video.png) [Descubra este recurso no vídeo](#video)

As etapas para executar esse caso de uso são as seguintes:

1. Gere um par de chaves GPG (público/privado) usando um utilitário GPG e, em seguida, instale a chave pública no Painel de controle do Campaign. As etapas detalhadas estão disponíveis na [documentação do Painel de controle do Campaign](https://docs.adobe.com/content/help/en/control-panel/using/instances-settings/gpg-keys-management.html#encrypting-data).

   ![](assets/gpg_install.png)

1. No Campaign Standard, crie um workflow para exportar os dados e criptografá-los usando a chave privada que foi instalada por meio do Painel de controle do Campaign. Para fazer isso, criaremos um workflow da seguinte maneira:

   ![](assets/gpg-workflow-export.png)

   * Atividade **[!UICONTROL Query]**: neste exemplo, queremos executar um query para direcionar os dados do banco de dados que queremos exportar.
   * **[!UICONTROL Extract file]** atividade : Criptografa e extrai os dados em um arquivo.
   * **[!UICONTROL Transfer file]** atividade : Transfere o arquivo contendo os dados criptografados para um servidor SFTP.

1. Configure a atividade **[!UICONTROL Query]** para direcionar os dados desejados a partir do banco de dados. Para obter mais informações, consulte [esta seção](../../automating/using/query.md).

1. Abra a atividade **[!UICONTROL Extract file]** e a configure de acordo com suas necessidades (arquivo de saída, colunas, formato etc.). Os conceitos globais sobre como configurar a atividade estão disponíveis [nesta seção](../../automating/using/extract-file.md).

   Adicione um estágio de pré-processamento à atividade para criptografar os dados que serão extraídos. Para fazer isso, selecione a chave GPG de criptografia a ser usada para criptografar os dados.

   ![](assets/gpg-extract-stage.png)

   >[!NOTE]
   >
   >O valor entre parênteses é o **comentário** que você definiu ao gerar o par de chaves usando a ferramenta de criptografia GPG. Certifique-se de selecionar a chave correspondente correta; caso contrário, o recipient não poderá descriptografar o arquivo.

1. Abra a atividade **[!UICONTROL Transfer file]** e especifique o servidor SFTP para o qual deseja enviar o arquivo. Os conceitos globais sobre como configurar a atividade estão disponíveis [nesta seção](../../automating/using/transfer-file.md).

   ![](assets/gpg-transfer-encrypt.png)

1. Agora você pode executar o workflow. Após a execução, o direcionamento de dados pelo query será exportado para o servidor SFTP em um arquivo .gpg criptografado.

## Vídeos tutoriais {#video}

Este vídeo mostra como usar uma chave GPG para descriptografar dados.

>[!VIDEO](https://video.tv.adobe.com/v/35753?quality=12)

Este vídeo mostra como usar uma chave GPG para criptografar dados.

>[!VIDEO](https://video.tv.adobe.com/v/36380?quality=12)

Os vídeos de instruções adicionais do Campaign Standard estão disponíveis [aqui](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=pt-BR).
