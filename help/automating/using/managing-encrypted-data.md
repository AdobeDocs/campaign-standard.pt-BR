---
title: Gerenciamento de dados criptografados
description: Saiba como gerenciar dados criptografados.
page-status-flag: never-activated
uuid: d909d26a-cf50-46af-ae09-f0fd7258ca27
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 75b83165-dcbd-4bb7-b703-ed769f489b16
translation-type: tm+mt
source-git-commit: 4e338fb9399f85127e1d8e5f7f178a8d3d0a47cc
workflow-type: tm+mt
source-wordcount: '938'
ht-degree: 53%

---


# Gerenciamento de dados criptografados {#managing-encrypted-data}

## Sobre os estágios de pré-processamento {#about-preprocessing-stages}

Em alguns casos, os dados que você deseja importar Servidores de Campanha podem precisar ser criptografados, por exemplo, se contiverem dados de PII.

Para poder criptografar dados de saída ou descriptografar dados de entrada, é necessário gerenciar chaves GPG usando o [Painel de controle do Campaign](https://docs.adobe.com/content/help/pt-BR/control-panel/using/instances-settings/gpg-keys-management.html).

>[!NOTE]
>
>O Painel de controle do Campaign está disponível para todos os clientes hospedados no AWS (exceto para clientes que hospedam suas instâncias de marketing no local).

Se você não estiver qualificado para usar o Painel de controle do Campaign, entre em contato com o Atendimento ao cliente do Adobe para que ele forneça à instância os comandos de criptografia/descriptografia necessários. Para fazer isso, envie uma solicitação indicando:

* O **rótulo** que será exibido na interface de Campanha para usar o comando. Por exemplo, &quot;Criptografar arquivo&quot;.
* O **comando** a ser instalado em sua instância.

Depois que a solicitação for processada, os comandos de criptografia/descriptografia estarão disponíveis no **[!UICONTROL Pre-processing stage]** campo nas **[!UICONTROL Load file]** atividades **[!UICONTROL Extract file]** e . Você pode usá-los para descriptografar ou criptografar os arquivos que deseja importar ou exportar.

![](assets/preprocessing-encryption.png)

**Tópicos relacionados:**

* [Carregar arquivo](../../automating/using/load-file.md)
* [Extrair arquivo](../../automating/using/extract-file.md)

## Caso de uso: importação de dados criptografados usando uma chave gerada pelo Painel de controle do Campaign {#use-case-gpg-decrypt}

Nesse caso de uso, criaremos um workflow para importar dados que foram criptografados em um sistema externo usando uma chave gerada no Painel de controle do Campaign.

Um vídeo tutorial sobre como usar uma chave GPG para descriptografar dados também está disponível [nesta seção](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/administrating/control-panel/gpg-key-management/decrypting-data.html).

As etapas para executar esse caso de uso são as seguintes:

1. Use o Painel de controle do Campaign para gerar um par de chaves (público/privado). As etapas detalhadas estão disponíveis na [documentação do Painel de controle do Campaign](https://docs.adobe.com/content/help/pt-BR/control-panel/using/instances-settings/gpg-keys-management.html#decrypting-data).

   * A chave pública será compartilhada com o sistema externo, que a usará para criptografar os dados que serão enviados para o Campaign.
   * A chave privada será usada pelo Campaign para descriptografar os dados criptografados recebidos.

   ![](assets/gpg_generate.png)

1. No sistema externo, use a chave pública baixada do Painel de controle do Campaign para criptografar os dados a serem importados para o Campaign Standard.

1. No Campaign Standard, crie um fluxo de trabalho para importar os dados criptografados e descriptografá-los usando a chave privada que foi instalada por meio do Painel de controle do Campaign. Para fazer isso, criaremos um workflow da seguinte maneira:

   ![](assets/gpg_workflow.png)

   * **[!UICONTROL Transfer file]** atividade: Transfere o arquivo de uma fonte externa para a Campanha. Neste exemplo, queremos transferir o arquivo de um servidor SFTP.
   * Atividade **[!UICONTROL Load file]**: carrega os dados do arquivo no banco de dados e os decodifica usando a chave privada gerada no Painel de controle do Campaign.

1. Abra a atividade **[!UICONTROL Transfer file]** e configure-a de acordo com suas necessidades. Os conceitos globais sobre como configurar a atividade estão disponíveis [nesta seção](../../automating/using/load-file.md).

   Na **[!UICONTROL Protocol]** guia, especifique detalhes sobre o servidor sftp e o arquivo .gpg criptografado que você deseja transferir.

   ![](assets/gpg_transfer.png)

1. Abra a atividade **[!UICONTROL Load file]** e configure-a de acordo com suas necessidades. Os conceitos globais sobre como configurar a atividade estão disponíveis [nesta seção](../../automating/using/load-file.md).

   Adicione um estágio de pré-processamento à atividade para descriptografar os dados recebidos. Para fazer isso, selecione a **[!UICONTROL Decryption GPG]** opção na lista.

   >[!NOTE]
   >
   >Observe que não é necessário especificar a chave privada a ser usada para descriptografar os dados. A chave privada é armazenada no Painel de controle do Campaign, o que detectará automaticamente a chave a ser usada para descriptografar o arquivo.

   ![](assets/gpg_load.png)

1. Clique em **[!UICONTROL OK]** para confirmar a configuração da atividade.

1. Agora você pode executar o workflow.

## Caso de uso: criptografar e exportar dados usando uma chave instalada no Painel de controle do Campaign {#use-case-gpg-encrypt}

Nesse caso de uso, criaremos um workflow para criptografar e exportar dados usando uma chave instalada no Painel de controle do Campaign.

Um vídeo tutorial sobre como usar uma chave GPG para criptografar dados também está disponível [nesta seção](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/administrating/control-panel/gpg-key-management/using-a-gpg-key-to-encrypt-data.html).

As etapas para executar esse caso de uso são as seguintes:

1. Gere um par de chaves GPG (público/privado) usando um utilitário GPG e, em seguida, instale a chave pública no Painel de controle do Campaign. As etapas detalhadas estão disponíveis na [documentação do Painel de controle do Campaign](https://docs.adobe.com/content/help/pt-BR/control-panel/using/instances-settings/gpg-keys-management.html#encrypting-data).

   ![](assets/gpg_install.png)

1. No Campaign Standard, crie um fluxo de trabalho para exportar os dados e criptografá-los usando a chave privada que foi instalada por meio do Painel de controle do Campaign. Para fazer isso, criaremos um workflow da seguinte maneira:

   ![](assets/gpg-workflow-export.png)

   * Atividade **[!UICONTROL Query]**: neste exemplo, queremos executar um query para direcionar os dados do banco de dados que queremos exportar.
   * **[!UICONTROL Extract file]** atividade: Criptografa e extrai os dados em um arquivo.
   * **[!UICONTROL Transfer file]** atividade: Transfere o arquivo que contém os dados criptografados para um servidor SFTP.

1. Configure a atividade **[!UICONTROL Query]** para direcionar os dados desejados a partir do banco de dados. Para obter mais informações, consulte [esta seção](../../automating/using/query.md).

1. Abra a **[!UICONTROL Extract file]** atividade e configure-a de acordo com suas necessidades (arquivo de saída, colunas, formato etc.). Os conceitos globais sobre como configurar a atividade estão disponíveis [nesta seção](../../automating/using/extract-file.md).

   Adicione um estágio de pré-processamento à atividade para criptografar os dados a serem extraídos. Para fazer isso, selecione a chave GPG de criptografia a ser usada para criptografar os dados.

   ![](assets/gpg-extract-stage.png)

   >[!NOTE]
   >
   >O valor entre parênteses é o **comentário** que você definiu ao gerar o par de chaves usando a ferramenta de criptografia GPG. Certifique-se de selecionar a chave correspondente correta; caso contrário, o recipient não conseguirá descriptografar o arquivo.

1. Abra a atividade **[!UICONTROL Transfer file]** e especifique o servidor SFTP para o qual deseja enviar o arquivo. Os conceitos globais sobre como configurar a atividade estão disponíveis [nesta seção](../../automating/using/transfer-file.md).

   ![](assets/gpg-transfer-encrypt.png)

1. Agora você pode executar o workflow. Após a execução, o direcionamento de dados pelo query será exportado para o servidor SFTP em um arquivo .gpg criptografado.
