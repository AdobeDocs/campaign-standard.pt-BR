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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 44d6126023e9411477ccd7ffc07ecde806e7976d
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 4%

---


# Gerenciamento de dados criptografados {#managing-encrypted-data}

Em alguns casos, os dados que você deseja importar Servidores de Campanha podem precisar ser criptografados, por exemplo, se contiverem dados de PII.

Para importar ou exportar arquivos criptografados, primeiro é necessário entrar em contato com o Atendimento ao cliente da Adobe para que ele forneça à sua instância os comandos de criptografia/descriptografia necessários.

Para fazer isso, envie uma solicitação indicando:

* O **rótulo** que será exibido na interface de Campanha para usar o comando. Por exemplo, &quot;Criptografar arquivo&quot;.
* O **comando** a ser instalado em sua instância.
Por exemplo, para descriptografar um arquivo usando PGP, o comando será:

   ```
   <path-to_pgp_if-not_global_or_server/>pgp.exe --decrypt --input nl6/var/vp/import/filename.pgp --passphrase "your password" --recipient recipient @email.com --verbose --output nl6/var/vp/import/filename
   ```

Depois que a solicitação for processada, os comandos de criptografia/descriptografia estarão disponíveis no **[!UICONTROL Pre-processing stage]** campo nas **[!UICONTROL Load file]** atividades **[!UICONTROL Extract file]** e . Você pode usá-los para descriptografar ou criptografar os arquivos que deseja importar ou exportar.

![](assets/preprocessing-encryption.png)

**Tópicos relacionados:**

* [Carregar arquivo](../../automating/using/load-file.md)
* [Extrair arquivo](../../automating/using/extract-file.md)
