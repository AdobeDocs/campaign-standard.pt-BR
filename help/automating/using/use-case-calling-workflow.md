---
title: Caso de uso para chamar fluxo de trabalho
description: Esta seção detalha como chamar um workflow com parâmetros externos.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 7a21f4f6-316f-4f3d-9d53-37d406a46aae
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '1006'
ht-degree: 1%

---

# Caso de uso {#use-case}

O caso de uso abaixo mostra como chamar o workflow com parâmetros dentro dos workflows.

O objetivo é acionar um workflow a partir de uma chamada à API com parâmetros externos. Esse fluxo de trabalho carregará dados em seu banco de dados a partir de um arquivo e criará um público-alvo associado. Depois que o público-alvo for criado, um segundo workflow será acionado para enviar uma mensagem personalizada com os parâmetros externos definidos na chamada de API.

Para executar esse caso de uso, é necessário executar as ações abaixo:

1. **Fazer uma chamada de API** para acionar o Workflow 1 com parâmetros externos. Consulte [Etapa 1: configuração da chamada de API](../../automating/using/use-case-calling-workflow.md#step-1--configuring-the-api-call).
1. **Fluxo de trabalho de compilação 1**: o workflow transferirá um arquivo e o carregará no banco de dados. Em seguida, ele testará se os dados estão vazios ou não e eventualmente salvará os perfis em um público-alvo. Por fim, ele acionará o Workflow 2. Consulte [Etapa 2: configuração do workflow 1](../../automating/using/use-case-calling-workflow.md#step-2--configuring-workflow-1).
1. **Fluxo de trabalho de compilação 2**: o fluxo de trabalho lerá o público-alvo criado no Fluxo de trabalho 1 e enviará uma mensagem personalizada para os perfis, com um código de segmento personalizado com os parâmetros. Consulte [Etapa 3: configuração do workflow 2](../../automating/using/use-case-calling-workflow.md#step-3--configuring-workflow-2).

![](assets/extsignal_uc_process.png)

## Pré-requisitos {#prerequisites}

Antes de configurar os workflows, é necessário criar o Workflow 1 e 2 com um **[!UICONTROL External signal]** atividade em cada um deles. Dessa forma, você poderá direcionar essas atividades de sinal ao chamar os workflows.

## Etapa 1: configuração da chamada de API {#step-1--configuring-the-api-call}

Faça uma chamada de API para acionar o Fluxo de trabalho 1 com parâmetros. Para obter mais informações sobre a sintaxe de chamada da API, consulte a [Documentação das APIs REST do Campaign Standard](../../api/using/triggering-a-signal-activity.md).

No nosso caso, queremos chamar o workflow com os parâmetros abaixo:

* **fileToTarget**: o nome do arquivo que queremos importar para o banco de dados.
* **descDesc**: a descrição que queremos exibir no delivery do desconto.

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

* **[!UICONTROL External signal]** activity: onde os parâmetros externos devem ser declarados para serem usados no workflow.
* **[!UICONTROL Transfer file]** atividade: importa o arquivo com o nome definido nos parâmetros.
* **[!UICONTROL Load file]** atividade: carrega dados do arquivo importado no banco de dados.
* **[!UICONTROL Update data]** Atividade: inserir ou atualizar o banco de dados com dados do arquivo importado.
* **[!UICONTROL Test]** activity: verifica se há dados importados.
* **[!UICONTROL Save audience]** Atividade: se o arquivo contiver dados, salva os perfis em um público-alvo.
* **[!UICONTROL End activity]** Atividade: chama o Workflow 2 com os parâmetros que você deseja usar dentro dele.

![](assets/extsignal_uc_wkf1.png)

Siga as etapas abaixo para configurar o workflow:

1. Declarar os parâmetros que foram definidos na chamada à API. Para fazer isso, abra a variável **[!UICONTROL External signal]** e, em seguida, adicione os nomes e tipos dos parâmetros.

   ![](assets/extsignal_uc1.png)

1. Adicionar um **[!UICONTROL Transfer file]** atividade para importar dados para o banco de dados.Para fazer isso, arraste e solte a atividade, abra-a e selecione a **[!UICONTROL Protocol]** guia.
1. Selecione o **[!UICONTROL Use a dynamic file path]** e, em seguida, use a **fileToTarget** como o arquivo a ser transferido:

   ```
   $(vars/@fileToTarget)
   ```

   ![](assets/extsignal_uc2.png)

1. Carregue os dados do arquivo no banco de dados.

   Para fazer isso, arraste e solte uma **[!UICONTROL Load file]** atividade no workflow e, em seguida, configure-a de acordo com suas necessidades.

1. Insira e atualize o banco de dados com os dados do arquivo importado.

   Para fazer isso, arraste e solte um **[!UICONTROL Update data]** e selecione a **[!UICONTROL Identification]** para adicionar um critério de reconciliação (neste caso, o **email** campo).

   ![](assets/extsignal_uc3.png)

1. Selecione o **[!UICONTROL Fields to update]** e especifique os campos que serão atualizados no banco de dados (neste caso, o **firstname** e **email** campos).

   ![](assets/extsignal_uc4.png)

1. Verifique se os dados foram recuperados do arquivo. Para fazer isso, arraste e solte uma **[!UICONTROL Test]** atividade no workflow e, em seguida, clique na guia **[!UICONTROL Add an element]** botão para adicionar uma condição.
1. Nomeie e defina a condição. Em nosso caso, queremos testar se a transição de saída contém dados com a sintaxe abaixo:

   ```
   $long(vars/@recCount)>0
   ```

   ![](assets/extsignal_uc5.png)

1. Se os dados forem recuperados, salve-os em um público-alvo. Para fazer isso, adicione um **[!UICONTROL Save audience]** atividade para o **O público alvo não está vazio** e, em seguida, abra-a.
1. Selecione o **[!UICONTROL Use a dynamic label]** e, em seguida, use a **fileToTarget** como o rótulo do público-alvo:

   ```
   $(vars/@fileToTarget)
   ```

   ![](assets/extsignal_uc6.png)

1. Arraste e solte um **[!UICONTROL End]** atividade que chamará o Fluxo de trabalho 2 com parâmetros, e depois o abrirá.
1. Selecione o **[!UICONTROL External signal]** e especifique o workflow a ser acionado e a atividade de sinal associada.
1. Defina os parâmetros que deseja usar no Workflow 2 e seus valores associados.

   Em nosso caso, queremos transmitir os parâmetros originalmente definidos na chamada de API (**fileToTarget** e **descDesc**), e um adicional **segmentCode** com um valor constante (&quot;desconto de 20%&quot;).

   ![](assets/extsignal_uc7.png)

O fluxo de trabalho 1 está configurado, agora é possível criar o Fluxo de trabalho 2. Para obter mais informações, consulte [esta seção](../../automating/using/use-case-calling-workflow.md#step-3--configuring-workflow-2).

## Etapa 3: configuração do workflow 2 {#step-3--configuring-workflow-2}

O fluxo de trabalho 2 será criado conforme abaixo:

* **[!UICONTROL External signal]** activity: onde os parâmetros devem ser declarados para serem usados no workflow.
* **[!UICONTROL Read audience]** Atividade: lê o público-alvo salvo no Fluxo de trabalho 1.
* **[!UICONTROL Email delivery]** atividade: envia uma mensagem recorrente ao público-alvo direcionado, personalizada com parâmetros.

![](assets/extsignal_uc_wkf2.png)

Siga as etapas abaixo para configurar o workflow:

1. Declare os parâmetros que foram definidos no Workflow 1.

   Para fazer isso, abra a variável **[!UICONTROL External signal]** e adicione o nome e o tipo de cada parâmetro definido na variável **[!UICONTROL End]** atividade do Workflow 1.

   ![](assets/extsignal_uc8.png)

1. Use o público que foi salvo no Fluxo de trabalho 1. Para fazer isso, arraste e solte uma **[!UICONTROL Read audience]** atividade no workflow e, em seguida, abra-a.
1. Selecione o **[!UICONTROL Use a dynamic audience]** e, em seguida, use a **fileToTarget** como o nome do público-alvo a ser lido:

   ```
   $(vars/@fileToTarget)
   ```

   ![](assets/extsignal_uc9.png)

1. Nomeie a transição de saída de acordo com o **segmentCode** parâmetro.

   Para fazer isso, selecione a variável **[!UICONTROL Transition]** e, em seguida, **[!UICONTROL Use a dynamic segment code]** opção.

1. Use o **segmentCode** como o nome da transição de saída:

   ```
   $(vars/@segmentCode)
   ```

   ![](assets/extsignal_uc10.png)

1. Arraste e solte um **[!UICONTROL Email delivery]** atividade para enviar uma mensagem ao público-alvo.
1. Identifique os parâmetros a serem usados na mensagem para personalizá-la com o **descDesc** parâmetro. Para fazer isso, abra as opções avançadas da atividade e adicione o nome e o valor do parâmetro.

   ![](assets/extsignal_uc10b.png)

1. Agora você pode configurar a mensagem. Abra a atividade e selecione **[!UICONTROL Recurring email]**.

   ![](assets/extsignal_uc11.png)

1. Selecione o template a ser usado e defina as propriedades do email de acordo com suas necessidades.
1. Use o **descDesc** como um campo de personalização. Para fazer isso, selecione-o na lista de campos de personalização.

   ![](assets/extsignal_uc13.png)

1. Agora você pode concluir a configuração da mensagem e enviá-la como de costume.

   ![](assets/extsignal_uc14.png)

## Execução de workflows {#executing-the-workflows}

Depois que os workflows forem criados, você poderá executá-los. Verifique se os dois workflows foram iniciados antes de executar a chamada de API.
