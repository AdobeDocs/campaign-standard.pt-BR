---
solution: Campaign Standard
product: campaign
title: Teste da linha de assunto de um email
description: Descubra como definir a linha de assunto de um email no Designer de email.
audience: sending
content-type: reference
topic-tags: editing-email-content
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '1095'
ht-degree: 2%

---

# Teste da linha de assunto de um email {#testing-a-subject}


## Sobre a linha de assunto preditiva {#about-predictive-subject-line}

Ao editar um email, você pode tentar diferentes linhas de assunto e obter uma estimativa de sua taxa de abertura antes de enviá-lo.

Esse recurso é desativado por padrão. Ela é ativada quando o primeiro modelo é importado. Um modelo é o resultado de conjuntos de dados de treinamento específicos para um determinado setor. Os modelos permitem que o sistema preveja a taxa de abertura do email quando uma nova linha de assunto for enviada.

>[!NOTE]
>
>Este recurso está disponível para mensagens de email e bancos de dados que contêm apenas conteúdo em inglês. O modelo treinado será inconsistente e resultará em resultados incorretos se sua instância contiver emails em outros idiomas. A opção que permite testar um assunto só estará visível se um modelo já estiver disponível em sua instância.

For more on importing models, see this [section](#importing-models).

## Teste da linha de assunto {#testing-subject-line}

Para testar sua linha de assunto, siga as etapas abaixo:

1. Crie ou abra seu email.
1. Abra o conteúdo e insira o assunto do email no campo de entrada correspondente.
1. Click the **[!UICONTROL Test subject]** button to access the **[!UICONTROL Test your subject line]** window. Você ainda pode editar o assunto desta janela.
1. Selecione o modelo correto a ser considerado para a previsão de taxa aberta. Estão disponíveis vários modelos, cada um correspondente a um setor específico. For more on using models, see this [section](#importing-models).
1. Clique em **[!UICONTROL Test]**.

Seu assunto é então analisado.

>[!NOTE]
>
>Se a linha de assunto for muito curta, ela não poderá ser analisada e uma mensagem de erro será exibida.

Vários indicadores são calculados e um conjunto de ferramentas é exibido para ajudá-lo a:

* **Taxa** de abertura prevista: Este gráfico fornece uma ideia da taxa de abertura que você pode esperar para o email com seu assunto atual.
* **Duração** do assunto: Esse indicador permite que você veja se o comprimento atual do assunto está correto ou se ele precisaria ser maior ou menor.
* **Palavras** coloridas: Ao testar o assunto, as palavras destacadas em verde são as que mais contribuem para aumentar a previsão de taxa aberta. Palavras destacadas em vermelho são as que menos contribuem para aumentar a previsão de taxa aberta. Se você adicionar ou remover palavras no assunto, as palavras destacadas serão alteradas.
* **Categorias e sugestões** de palavras: Na parte inferior da janela, são exibidas várias categorias relevantes para o modelo selecionado. Essas categorias são classificadas por ordem de importância e permitem que você veja se o assunto contém palavras que estão associadas a ele por meio de um símbolo de verificação. Cada categoria contém um conjunto de palavras sugeridas que podem ser usadas no seu assunto para torná-lo mais relevante e aumentar a taxa de abertura. Essas palavras são as que são usadas com mais frequência em uma determinada categoria.

>[!NOTE]
>
>Campos de personalização e sinais de pontuação são retirados da análise do assunto. No caso de texto dinâmico/condicional, todas as variantes são consideradas como uma única linha de assunto.

![](assets/predictive_subject_line_example.png)

## Importação de modelos {#importing-models}

Por padrão, não há modelo em execução no servidor Adobe Campaign. Há duas maneiras de obter um modelo e ativar o recurso:

* Você pode treinar um modelo local a partir dos dados de suas mensagens de email anteriores.
* Você pode importar modelos pré-treinados específicos para certas indústrias (médica, etc.) usando o recurso de importação [de](../../automating/using/managing-packages.md) pacote.

### Treinamento de um modelo local {#training-local-model}

* Se você já estiver usando o Adobe Campaign, o modelo local será treinado automaticamente nas mensagens que você já enviou.
* Se você for novo no Adobe Campaign, poderá extrair um arquivo CSV do seu sistema anterior/ESP que contém 4 colunas: data, assunto, abre, enviado. Para fazer isso, vá até **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Email]** > **[!UICONTROL Subject Line Import]** e siga as instruções fornecidas nas telas sucessivas. Quando o upload do assunto estiver concluído, importe um modelo local conforme descrito abaixo. O modelo local é treinado automaticamente com os dados carregados.
* Se você for novo na Adobe Campaign e não conseguir obter um arquivo CSV conforme descrito acima, poderá usar um modelo [](#pre-trained-models) pré-treinado ou aguardar até que tenha dados suficientes do delivery no sistema para treinar um modelo local. O sistema determinará automaticamente se seu conjunto de dados atual contém dados suficientes para reconhecer padrões e treinar o modelo.

>[!NOTE]
>
>Não há um número definido de linhas de assunto necessárias para treinar seu próprio modelo. For more on this, see [Troubleshooting](#troubleshooting).
>
>Você só pode ter um modelo treinado em sua instância.

Para treinar um modelo local:
1. Baixe o subjectLineTraining.xml [aqui](https://experience.adobe.com/#/downloads/content/software-distribution/en/campaign.html) e use o recurso de importação [de](../../automating/using/managing-packages.md) pacote para fazer upload para sua instância do Adobe Campaign. Um fluxo de trabalho técnico fará automaticamente o treinamento para você.
1. Na primeira vez que você deseja treinar um modelo, um administrador pode forçar o start **[!UICONTROL SubjectLine Training workflow]** a partir do menu **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Workflows]** .
1. Depois que um modelo é carregado e treinado, o recurso é ativado automaticamente e uma nova opção é exibida ao lado do campo de linha de assunto das mensagens.
1. Em seguida, o fluxo de trabalho técnico continuará automaticamente treinando seu modelo toda semana.

### Importação de modelos pré-treinados {#pre-trained-models}

Para acessar esses modelos, clique [aqui](https://experience.adobe.com/#/downloads/content/software-distribution/en/campaign.html). Use o recurso de importação [de](../../automating/using/managing-packages.md) pacote para fazer upload de um modelo para sua instância do Adobe Campaign.

Os modelos disponíveis para uso são:

* Indústria cosmética: subjectInsightCosmetic.xml
* Indústria de supermercados: subjectInsightSupermarket.xml
* Indústria médica: subjectInsightMedical.xml
* Modelo de comboio: subjettlineTraining.xml.

Estes modelos não podem ser treinados.

Depois que um modelo é carregado, o recurso é ativado automaticamente e uma nova opção é exibida ao lado do campo de linha de assunto das mensagens.

>[!NOTE]
>
>Importar e gerar modelos treinados só podem ser executados por um administrador.

## Solução de problemas {#troubleshooting}

A linha de assunto previsível é um processo de aprendizado por computador que leva em conta todas as linhas de assunto que você carregou com suas taxas abertas. Isso permite que o sistema preveja a taxa de abertura de um email quando uma nova linha de assunto for enviada.

Para que você possa treinar seu próprio modelo, as linhas de assunto precisam ser variadas e não devem ter duplicados, não importa o número de linhas de assunto usadas para treinar seu modelo.

A qualidade das rubricas é essencial. Se não houver dados de qualidade suficientes para processar, ou se todas as linhas de assunto anteriores forem muito semelhantes, o sistema não conseguirá treinar o modelo e você poderá receber uma mensagem de erro. Isso significa que seu conjunto de registros existente não permite fornecer uma sugestão preditiva confiável.

Nesse caso, você deve revisar os dados que está carregando e verificar se as linhas de assunto são variadas o suficiente para treinar seu modelo com eficiência.

<!--Some clients have reported this issue: I have had the subject line training workflow running for about a year now.  It has trained on 883 records and I am still seeing the message "The existing dataset is not enough to generate a model."  I do get an error in the workflow every time it runs "XML-110009 Unable to find the element 'runwf' of path '/' (document with schema 'serverConf')".

For this, campaign takes the subject line as training data and tries to come up with significant enough model to predict open rate with 95% confidence.

The 400 subject line number is mention with at least and is only indicative, model generation will also depend on quality of these lines.

It may happen that even 10k subject lines don't lead to model generation if they are too similar.

It means that it can be case that you don't have enough subject lines to generate the model and it is giving this error.

If you are getting an error/warning message, it means that your existing set of records is not enough for the predictive subject module to give a high confidence suggestion.

Adobe recommends reviewing the data you are uploading as the similarity of the subject lines might be the issue.-->
