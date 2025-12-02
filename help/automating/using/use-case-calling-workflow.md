---
title: Caso de uso para chamar fluxo de trabalho
description: Esta seção detalha como chamar um workflow com parâmetros externos.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 7a21f4f6-316f-4f3d-9d53-37d406a46aae
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '1006'
ht-degree: 1%

---

# Caso de uso {#use-case}

O caso de uso abaixo mostra como chamar o workflow com parâmetros dentro dos workflows.

O objetivo é acionar um workflow a partir de uma chamada à API com parâmetros externos. Esse fluxo de trabalho carregará dados em seu banco de dados a partir de um arquivo e criará um público-alvo associado. Depois que o público-alvo for criado, um segundo workflow será acionado para enviar uma mensagem personalizada com os parâmetros externos definidos na chamada de API.

Para executar esse caso de uso, é necessário executar as ações abaixo:

1. **Fazer uma chamada de API** para acionar o Fluxo de Trabalho 1 com parâmetros externos. Consulte [Etapa 1: configuração da chamada de API](../../automating/using/use-case-calling-workflow.md#step-1--configuring-the-api-call).
1. **Fluxo de trabalho de compilação 1**: o fluxo de trabalho transferirá um arquivo e o carregará no banco de dados. Em seguida, ele testará se os dados estão vazios ou não e eventualmente salvará os perfis em um público-alvo. Por fim, ele acionará o Workflow 2. Consulte [Etapa 2: Configuração do Fluxo de Trabalho 1](../../automating/using/use-case-calling-workflow.md#step-2--configuring-workflow-1).
1. **Criar Fluxo de Trabalho 2**: o fluxo de trabalho lerá o público-alvo criado no Fluxo de Trabalho 1 e enviará uma mensagem personalizada para os perfis, com um código de segmento personalizado com os parâmetros. Consulte [Etapa 3: Configuração do Fluxo de Trabalho 2](../../automating/using/use-case-calling-workflow.md#step-3--configuring-workflow-2).

![](assets/extsignal_uc_process.png)

## Pré-requisitos {#prerequisites}

Antes de configurar os fluxos de trabalho, é necessário criar o Fluxo de trabalho 1 e 2 com uma atividade **[!UICONTROL External signal]** em cada um deles. Dessa forma, você poderá direcionar essas atividades de sinal ao chamar os workflows.

## Etapa 1: configuração da chamada de API {#step-1--configuring-the-api-call}

Faça uma chamada de API para acionar o Fluxo de trabalho 1 com parâmetros. Para obter mais informações sobre a sintaxe de chamada da API, consulte a [documentação das APIs REST do Campaign Standard](../../api/using/triggering-a-signal-activity.md).

No nosso caso, queremos chamar o workflow com os parâmetros abaixo:

* **fileToTarget**: o nome do arquivo que queremos importar para o banco de dados.
* **discountDesc**: a descrição que queremos exibir na entrega do desconto.

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/<TRIGGER_URL>
-H 'Authorization: Bearer <ACCESS_TOKEN>' 
-H 'Cache-Control: no-cache' 
-H 'X-Api-Key: <API_KEY>' 
-H 'Content-Type: application/json;charset=utf-8' 
-H 'Content-Length:79' 
-i
-d {
-d "source:":"API",
-d "parameters":{
-d "fileToTarget":"profile.txt",
-d "discountDesc":"Running shoes"
-d } 
```

## Etapa 2: configuração do workflow 1 {#step-2--configuring-workflow-1}

O fluxo de trabalho 1 será criado conforme abaixo:

* Atividade **[!UICONTROL External signal]**: onde os parâmetros externos devem ser declarados para serem usados dentro do fluxo de trabalho.
* Atividade **[!UICONTROL Transfer file]**: importa o arquivo com o nome definido nos parâmetros.
* Atividade **[!UICONTROL Load file]**: carrega dados do arquivo importado no banco de dados.
* Atividade **[!UICONTROL Update data]**: inserir ou atualizar o banco de dados com dados do arquivo importado.
* Atividade **[!UICONTROL Test]**: verifica se há dados importados.
* Atividade **[!UICONTROL Save audience]**: se o arquivo contiver dados, salva os perfis em uma audiência.
* Atividade **[!UICONTROL End activity]**: chama o Fluxo de Trabalho 2 com os parâmetros que você deseja usar dentro dele.

![](assets/extsignal_uc_wkf1.png)

Siga as etapas abaixo para configurar o workflow:

1. Declarar os parâmetros que foram definidos na chamada à API. Para fazer isso, abra a atividade **[!UICONTROL External signal]** e adicione os nomes e tipos dos parâmetros.

   ![](assets/extsignal_uc1.png)

1. Adicione uma atividade **[!UICONTROL Transfer file]** para importar dados para o banco de dados.Para fazer isso, arraste e solte a atividade, abra-a e selecione a guia **[!UICONTROL Protocol]**.
1. Selecione a opção **[!UICONTROL Use a dynamic file path]** e use o parâmetro **fileToTarget** como o arquivo a ser transferido:

   ```
   $(vars/@fileToTarget)
   ```

   ![](assets/extsignal_uc2.png)

1. Carregue os dados do arquivo no banco de dados.

   Para fazer isso, arraste e solte uma atividade **[!UICONTROL Load file]** no fluxo de trabalho e configure-a de acordo com suas necessidades.

1. Insira e atualize o banco de dados com os dados do arquivo importado.

   Para fazer isso, arraste e solte uma atividade **[!UICONTROL Update data]** e selecione a guia **[!UICONTROL Identification]** para adicionar um critério de reconciliação (neste caso, o campo **email**).

   ![](assets/extsignal_uc3.png)

1. Selecione a guia **[!UICONTROL Fields to update]** e especifique os campos a serem atualizados no banco de dados (neste caso, os campos **firstname** e **email**).

   ![](assets/extsignal_uc4.png)

1. Verifique se os dados foram recuperados do arquivo. Para fazer isso, arraste e solte uma atividade **[!UICONTROL Test]** no fluxo de trabalho e clique no botão **[!UICONTROL Add an element]** para adicionar uma condição.
1. Nomeie e defina a condição. Em nosso caso, queremos testar se a transição de saída contém dados com a sintaxe abaixo:

   ```
   $long(vars/@recCount)>0
   ```

   ![](assets/extsignal_uc5.png)

1. Se os dados forem recuperados, salve-os em um público-alvo. Para fazer isso, adicione uma atividade **[!UICONTROL Save audience]** à transição **Target not empty** e, em seguida, abra-a.
1. Selecione a opção **[!UICONTROL Use a dynamic label]** e use o parâmetro **fileToTarget** como o rótulo do público-alvo:

   ```
   $(vars/@fileToTarget)
   ```

   ![](assets/extsignal_uc6.png)

1. Arraste e solte uma atividade **[!UICONTROL End]** que chamará o Fluxo de Trabalho 2 com parâmetros e, em seguida, a abra.
1. Selecione a guia **[!UICONTROL External signal]** e especifique o fluxo de trabalho a ser acionado e sua atividade de sinal associada.
1. Defina os parâmetros que deseja usar no Workflow 2 e seus valores associados.

   Em nosso caso, queremos passar os parâmetros originalmente definidos na chamada de API (**fileToTarget** e **discountDesc**) e um parâmetro **segmentCode** adicional com um valor constante (&quot;20% de desconto&quot;).

   ![](assets/extsignal_uc7.png)

O fluxo de trabalho 1 está configurado, agora é possível criar o Fluxo de trabalho 2. Para obter mais informações, consulte [esta seção](../../automating/using/use-case-calling-workflow.md#step-3--configuring-workflow-2).

## Etapa 3: configuração do workflow 2 {#step-3--configuring-workflow-2}

O fluxo de trabalho 2 será criado conforme abaixo:

* Atividade **[!UICONTROL External signal]**: onde os parâmetros devem ser declarados para serem usados dentro do fluxo de trabalho.
* Atividade **[!UICONTROL Read audience]**: lê o público salvo no Fluxo de trabalho 1.
* Atividade **[!UICONTROL Email delivery]**: envia uma mensagem recorrente para o público alvo, personalizada com parâmetros.

![](assets/extsignal_uc_wkf2.png)

Siga as etapas abaixo para configurar o workflow:

1. Declare os parâmetros que foram definidos no Workflow 1.

   Para fazer isso, abra a atividade **[!UICONTROL External signal]** e adicione o nome e o tipo de cada parâmetro definido na atividade **[!UICONTROL End]** do Fluxo de Trabalho 1.

   ![](assets/extsignal_uc8.png)

1. Use o público que foi salvo no Fluxo de trabalho 1. Para fazer isso, arraste e solte uma atividade **[!UICONTROL Read audience]** no fluxo de trabalho e depois a abra.
1. Selecione a opção **[!UICONTROL Use a dynamic audience]** e use o parâmetro **fileToTarget** como o nome do público-alvo a ser lido:

   ```
   $(vars/@fileToTarget)
   ```

   ![](assets/extsignal_uc9.png)

1. Nomeie a transição de saída de acordo com o parâmetro **segmentCode**.

   Para fazer isso, selecione a guia **[!UICONTROL Transition]** e depois a opção **[!UICONTROL Use a dynamic segment code]**.

1. Use o parâmetro **segmentCode** como o nome da transição de saída:

   ```
   $(vars/@segmentCode)
   ```

   ![](assets/extsignal_uc10.png)

1. Arraste e solte uma atividade **[!UICONTROL Email delivery]** para enviar uma mensagem ao público-alvo.
1. Identifique os parâmetros a serem usados na mensagem para personalizá-la com o parâmetro **discountDesc**. Para fazer isso, abra as opções avançadas da atividade e adicione o nome e o valor do parâmetro.

   ![](assets/extsignal_uc10b.png)

1. Agora você pode configurar a mensagem. Abra a atividade e selecione **[!UICONTROL Recurring email]**.

   ![](assets/extsignal_uc11.png)

1. Selecione o template a ser usado e defina as propriedades do email de acordo com suas necessidades.
1. Use o parâmetro **discountDesc** como um campo de personalização. Para fazer isso, selecione-o na lista de campos de personalização.

   ![](assets/extsignal_uc13.png)

1. Agora você pode concluir a configuração da mensagem e enviá-la como de costume.

   ![](assets/extsignal_uc14.png)

## Execução de workflows {#executing-the-workflows}

Depois que os workflows forem criados, você poderá executá-los. Verifique se os dois workflows foram iniciados antes de executar a chamada de API.
