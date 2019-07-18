---
title: Transferir arquivo
seo-title: Transferir arquivo
description: Transferir arquivo
seo-description: A atividade do arquivo de transferência permite receber ou enviar arquivos, testar se há arquivos presentes ou listar arquivos no Adobe Campaign.
page-status-flag: nunca ativado
uuid: a 2 f 18118-b 681-4310-aee 0-9 e 82179 d 2032
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizando
content-type: reference
topic-tags: gerenciamento de dados-atividades
discoiquuid: 752 f 2 aed-f 897-485 e-b 329-f 3 cc 1756 ee 8 e
context-tags: Filetransfer, main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0fcedd464ae2074e7eda793bbf20cc53ce04f324

---


# Transfer file{#transfer-file}

## Description {#description}

![](assets/file_transfer.png)

The **[!UICONTROL Transfer file]** activity allows you to receive or send files, test whether there are files present, or list files in Adobe Campaign.

## Context of use {#context-of-use}

A maneira como os dados serão extraídos é definida quando a atividade é configurada. O arquivo a ser carregado pode ser uma lista de contatos, por exemplo.

You can use this activity to recover data that will then be structured with the **[!UICONTROL Load file]** activity.

## Configuration {#configuration}

1. Drop a **[!UICONTROL Transfer file]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Use the drop-down list in the **[!UICONTROL Action]** field to select one of the following activity actions:

   ![](assets/wkf_file_transfer_01.png)

   * **Download de arquivo**: permite baixar um arquivo.
   * **Carregamento de arquivo**: permite carregar um arquivo. Uploading a file from Adobe Campaign file generates a log entry in the **[!UICONTROL Export audits]** menu. For more information on export audits, refer to the [Auditing exports](../../administration/using/auditing-export-logs.md) section.
   * **Teste para verificar se existe um arquivo**: permite verificar se há um arquivo.
   * **Lista de arquivos**: permite listar os arquivos presentes no Adobe Campaign.
   Dependendo da ação selecionada, um ou vários protocolos estão disponíveis:

   * **HTTP**: este protocolo permite que você comece a baixar um arquivo de uma conta externa ou de um URL.

      * Click the **[!UICONTROL Use connection parameters defined in an external account]** option, then select the account you would like and specify the path of the file to download.

         ![](assets/wkf_file_transfer_03.png)

      * Click the **[!UICONTROL Quick configuration]** option, then enter the URL in the field that appears.

         ![](assets/wkf_file_transfer_04.png)
   * **S 3**: este protocolo permite que você comece a baixar um arquivo de um URL ou de uma conta externa via Amazon Simple Storage Service (S 3).

      * Selecione a conta externa e especifique o caminho do arquivo a ser baixado.

         ![](assets/wkf_file_transfer_08.png)
   * **SFTP**: este protocolo permite que você comece a baixar um arquivo de um URL ou de uma conta externa.

      * Click the **[!UICONTROL Use connection parameters defined in an external account]** option, then select the account you would like and specify the path of the file to download.

         ![](assets/wkf_file_transfer_07.png)

         >[!CAUTION]
         >
         >Os curingas são suportados.

      * Click the **[!UICONTROL Quick configuration]** option, then enter the URL in the field that appears.
      * If you want to sort the imported files, select the **[!UICONTROL Sort alphanumerically]** option from the **[!UICONTROL Additional options]** section. Os arquivos serão processados em ordem sequencial.

         ![](assets/wkf_file_transfer_sort.png)
   * **Arquivo (s) presente (s) no servidor do Adobe Campaign**: este protocolo corresponde ao repositório que contém os arquivos a serem recuperados.

      Metacaracteres ou curingas (por exemplo * ou?) pode ser usado para filtrar arquivos.

      Preencha este campo e confirme sua atividade para usar esse protocolo.

      >[!NOTE]
      >
      >O caminho deve ser relativo ao diretório de espaço de armazenamento do servidor do Adobe Campaign. Os arquivos estão localizados no diretório** sftp &lt; yourinstancename &gt;/**. Você também não pode navegar pelos diretórios acima do espaço de armazenamento. For example: **user&lt;yourinstancename&gt;/my_recipients.csv** is correct. **../hello/my_recipients.csv** está incorreto. **//myserver/hello/myrecipients.csv** está incorreto.
   Selecione o protocolo e preencha os campos associados.

   The **[!UICONTROL Use a dynamic file path]** option, available for each protocol, lets you use a standard expression and events variables to personalize the name of the file to transfer. For more on this, refer to the [Customizing activities with events variables](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) section.

1. The **[!UICONTROL Additional options]** section, available depending on the protocol selected, allows you to add parameters to your protocol. Você pode:

   * **[!UICONTROL Delete the source files after transfer]**
   * **[!UICONTROL Disable passive mode]**
   * **[!UICONTROL List all files]**: essa opção está disponível ao selecionar **[!UICONTROL File listing]** a ação. It allows you to index all the files present on the server in the **vars.filenames** event variable in which the file names are separated by the **'n'** characters.

1. The **[!UICONTROL If no files are found]** section of the **[!UICONTROL Advanced options]** tab allows you to configure specific actions if any errors or inexistent files are detected when the activity is started.

   Você também pode definir tentativas. As diferentes tentativas aparecem no log de execução do fluxo de trabalho.

   ![](assets/wkf_file_transfer_09.png)

1. Confirme a configuração da atividade e salve seu fluxo de trabalho.

## Historization settings {#historization-settings}

Every time a **[!UICONTROL Transfer file]** activity is executed, it stores the uploaded or downloaded files in a dedicated folder. One folder is created for each **[!UICONTROL Transfer file]** activity of a workflow. Portanto, é importante poder limitar o tamanho dessa pasta para preservar o espaço físico no servidor.

To do that, you can define **[!UICONTROL Historization settings]** in the **[!UICONTROL Advanced options]** of the **[!UICONTROL Transfer File]** activity.

**[!UICONTROL Historization settings]** permitir a definição de um número máximo de arquivos ou tamanho total para a pasta da atividade. Por padrão, 100 arquivos e 50 MB são autorizados.

Toda vez que a atividade é executada, a pasta é verificada da seguinte maneira:

* Somente arquivos criados mais de 24 horas antes da execução da atividade são considerados.
* If the number of files taken into account is greater than the value of the **[!UICONTROL Maximum number of files]** parameter, the oldest files are deleted until the **[!UICONTROL Maximum number of files]** allowed is reached.
* If the total size of files taken into account is greater than the value of the **[!UICONTROL Maximum size (in MB)]** parameter, the oldest files are deleted until the **[!UICONTROL Maximum size (in MB)]** allowed is reached.

>[!NOTE]
Se a atividade não for executada novamente, sua pasta não será verificada nem eliminada. Tendo isso em mente, tenha cuidado ao transferir arquivos grandes.

## Example {#example}

The following example shows the configuration of a **File transfer** activity which will then be followed by a **Load file** activity then an **Update data** activity. O objetivo deste fluxo de trabalho é adicionar ou atualizar os perfis de banco de dados do Adobe Campaign com os dados recuperados pelo fluxo de trabalho.

1. Drag and drop a **Transfer file** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. In the **[!UICONTROL Protocol]** tab, select **SFTP**.
1. Select the **Use connection parameters defined in an external account** option.
1. Digite o nome da conta externa.
1. Enter the **File path on the remote server**.

   ![](assets/wkf_file_transfer_07.png)

1. Confirme sua atividade e salve seu fluxo de trabalho.

