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
source-git-commit: 4fe36a1747aca69e8857cf415593086781947a47

---


# Transferir arquivo{#transfer-file}

## Descrição {#description}

![](assets/file_transfer.png)

A **[!UICONTROL Transfer file]** atividade permite receber ou enviar arquivos, testar se há arquivos presentes ou listar arquivos no Adobe Campaign.

## Contexto de uso {#context-of-use}

A maneira como os dados serão extraídos é definida quando a atividade é configurada. O arquivo a ser carregado pode ser uma lista de contatos, por exemplo.

Você pode usar essa atividade para recuperar dados que serão estruturados com a **[!UICONTROL Load file]** atividade.

## Configuração {#configuration}

1. Solte uma **[!UICONTROL Transfer file]** atividade no seu fluxo de trabalho.
1. Selecione a atividade e abra-a usando o ![](assets/edit_darkgrey-24px.png) botão das ações rápidas que aparecem.
1. Use a lista suspensa no **[!UICONTROL Action]** campo para selecionar uma das seguintes ações de atividade:

   ![](assets/wkf_file_transfer_01.png)

   * **Download de arquivo**: permite baixar um arquivo.
   * **Carregamento de arquivo**: permite carregar um arquivo. Carregar um arquivo do arquivo Adobe Campaign gera uma entrada de log no **[!UICONTROL Export audits]** menu. Para obter mais informações sobre auditorias de exportação, consulte [a](../../administration/using/auditing-export-logs.md) seção Auditoria de exportações.
   * **Teste para verificar se existe um arquivo**: permite verificar se há um arquivo.
   * **Lista de arquivos**: permite listar os arquivos presentes no Adobe Campaign.
   Dependendo da ação selecionada, um ou vários protocolos estão disponíveis:

   * **HTTP**: este protocolo permite que você comece a baixar um arquivo de uma conta externa ou de um URL.

      * Clique na **[!UICONTROL Use connection parameters defined in an external account]** opção e selecione a conta que deseja e especifique o caminho do arquivo para download.

         ![](assets/wkf_file_transfer_03.png)

      * Clique na **[!UICONTROL Quick configuration]** opção e insira o URL no campo que aparece.

         ![](assets/wkf_file_transfer_04.png)
   * **S 3**: este protocolo permite que você comece a baixar um arquivo de um URL ou de uma conta externa via Amazon Simple Storage Service (S 3).

      * Selecione a conta externa e especifique o caminho do arquivo a ser baixado.

         ![](assets/wkf_file_transfer_08.png)
   * **SFTP**: este protocolo permite que você comece a baixar um arquivo de um URL ou de uma conta externa.

      * Clique na **[!UICONTROL Use connection parameters defined in an external account]** opção e selecione a conta que deseja e especifique o caminho do arquivo para download.

         ![](assets/wkf_file_transfer_07.png)

         >[!CAUTION]
         >
         >Os curingas são suportados.

      * Clique na **[!UICONTROL Quick configuration]** opção e insira o URL no campo que aparece.
      * Se desejar classificar os arquivos importados, selecione a **[!UICONTROL Sort alphanumerically]** opção na **[!UICONTROL Additional options]** seção. Os arquivos serão processados em ordem sequencial.

         ![](assets/wkf_file_transfer_sort.png)
   * **Arquivo (s) presente (s) no servidor do Adobe Campaign**: este protocolo corresponde ao repositório que contém os arquivos a serem recuperados.

      Metacaracteres ou curingas (por exemplo * ou?) pode ser usado para filtrar arquivos.

      Preencha este campo e confirme sua atividade para usar esse protocolo.

      >[!NOTE]
      >
      >O caminho deve ser relativo ao diretório de espaço de armazenamento do servidor do Adobe Campaign. Os arquivos estão localizados no **sftp &lt; yourinstancename &gt;/** diretório. Você também não pode navegar pelos diretórios acima do espaço de armazenamento. Por exemplo: **user &lt; yourinstancename &gt;/my_ recipients. csv** está correto. **../hello/my_recipients.csv** está incorreto. **//myserver/hello/myrecipients.csv** está incorreto.
   Selecione o protocolo e preencha os campos associados.

   A **[!UICONTROL Use a dynamic file path]** opção, disponível para cada protocolo, permite que você use uma expressão padrão e variáveis de eventos para personalizar o nome do arquivo a ser transferido. Para obter mais informações sobre isso, consulte a [seção Personalizar atividades com variáveis](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) de eventos.

1. A **[!UICONTROL Additional options]** seção, disponível dependendo do protocolo selecionado, permite adicionar parâmetros ao protocolo. Você pode:

   * **[!UICONTROL Delete the source files after transfer]**
   * **[!UICONTROL Disable passive mode]**
   * **[!UICONTROL List all files]**: essa opção está disponível ao selecionar **[!UICONTROL File listing]** a ação. Permite indexar todos os arquivos presentes no servidor na variável de evento **vars. filenames** na qual os nomes de arquivo são separados **pelos** caracteres'n '.

1. A **[!UICONTROL If no files are found]** seção da **[!UICONTROL Advanced options]** guia permite que você configure ações específicas se qualquer erro ou arquivo inexistente for detectado quando a atividade for iniciada.

   Você também pode definir tentativas. As diferentes tentativas aparecem no log de execução do fluxo de trabalho.

   ![](assets/wkf_file_transfer_09.png)

1. Confirme a configuração da atividade e salve seu fluxo de trabalho.

## Configurações de gramatização {#historization-settings}

Toda vez que uma **[!UICONTROL Transfer file]** atividade é executada, ele armazena os arquivos carregados ou baixados em uma pasta dedicada. Uma pasta é criada para cada **[!UICONTROL Transfer file]** atividade de um fluxo de trabalho. Portanto, é importante poder limitar o tamanho dessa pasta para preservar o espaço físico no servidor.

Para fazer isso, você pode definir **[!UICONTROL Historization settings]****[!UICONTROL Advanced options]** na **[!UICONTROL Transfer File]** atividade.

**[!UICONTROL Historization settings]** permitir a definição de um número máximo de arquivos ou tamanho total para a pasta da atividade. Por padrão, 100 arquivos e 50 MB são autorizados.

Toda vez que a atividade é executada, a pasta é verificada da seguinte maneira:

* Somente arquivos criados mais de 24 horas antes da execução da atividade são considerados.
* Se o número de arquivos considerados for maior que o valor do **[!UICONTROL Maximum number of files]** parâmetro, os arquivos mais antigos serão excluídos até que o **[!UICONTROL Maximum number of files]** permitido seja atingido.
* Se o tamanho total dos arquivos considerados for maior que o valor do **[!UICONTROL Maximum size (in MB)]** parâmetro, os arquivos mais antigos serão excluídos até que o **[!UICONTROL Maximum size (in MB)]** permitido seja atingido.

>[!NOTE]
Se a atividade não for executada novamente, sua pasta não será verificada nem eliminada. Tendo isso em mente, tenha cuidado ao transferir arquivos grandes.

## Exemplo {#example}

O exemplo a seguir mostra a configuração de uma **atividade de transferência** de arquivo que será seguida por uma atividade **de arquivo** Carregar e uma **atividade de dados** Atualizar. O objetivo deste fluxo de trabalho é adicionar ou atualizar os perfis de banco de dados do Adobe Campaign com os dados recuperados pelo fluxo de trabalho.

1. Arraste e solte uma **atividade de arquivo** Transferir no seu fluxo de trabalho.
1. Selecione a atividade e abra-a usando o ![](assets/edit_darkgrey-24px.png) botão das ações rápidas que aparecem.
1. Na **[!UICONTROL Protocol]** guia, selecione **SFTP**.
1. Selecione **Usar parâmetros de conexão definidos em uma opção de conta** externa.
1. Digite o nome da conta externa.
1. Insira o caminho **Arquivo no servidor remoto**.

   ![](assets/wkf_file_transfer_07.png)

1. Confirme sua atividade e salve seu fluxo de trabalho.

