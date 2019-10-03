---
title: Testing the subject line of an email
seo-title: Testing the subject line of an email
description: Teste da linha de assunto de um email
seo-description: Descubra como definir a linha de assunto de um email no Designer de email.
page-status-flag: nunca ativado
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: envio
content-type: referência
topic-tags: edição-email-conteúdo
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 3fc0d9d7e90a31ffb34efc33d6f5c148ba5aac90

---

# Teste da linha de assunto de um email {#testing-a-subject}

Para testar sua linha de assunto, siga as etapas abaixo:

1. Create or open your email.
1. Abra o conteúdo e digite o assunto do email no campo de entrada correspondente.
1. Click the  button to access the  window. **[!UICONTROL Test subject]****[!UICONTROL Test your subject line]** You can still edit the subject from this window.
1. Select the correct model to be taken into account for the open rate prediction. Several models are available, each corresponding to a specific industry.
1. Click **[!UICONTROL Test]**.

Your subject is then analyzed.

>[!NOTE]
>
>Se a linha de assunto for muito curta, ela não poderá ser analisada e uma mensagem de erro será exibida.

Vários indicadores são calculados e um conjunto de ferramentas é exibido para ajudá-lo a:

* **Predicted open rate: This chart gives you an idea of the open rate you can expect for the email with its current subject.**
* **Subject length: This indicator lets you see if the current length of the subject is correct or whether it would need to be longer or shorter.**
* **Colored words: When testing the subject, words highlighted in green are the words that contribute the most to increasing the open rate prediction.** Palavras destacadas em vermelho são as que menos contribuem para aumentar a previsão de taxa aberta. If you add or remove words in the subject, highlighted words will change.
* **Categorias e sugestões** de palavras: Na parte inferior da janela, são exibidas várias categorias relevantes para o modelo selecionado. Essas categorias são classificadas por ordem de importância e permitem que você veja se o assunto contém palavras associadas a ele por meio de um símbolo de verificação. Cada categoria contém um conjunto de palavras sugeridas que podem ser usadas em seu assunto para torná-lo mais relevante e aumentar a taxa aberta. Essas palavras são as palavras mais usadas em uma determinada categoria.

>[!NOTE]
>
>Os campos de personalização e os sinais de pontuação são retirados da análise de assunto. No caso de texto dinâmico/condicional, todas as variantes são consideradas como uma única linha de assunto.

![](assets/predictive_subject_line_example.png)

## Importação de modelos {#importing-models}

Por padrão, não há modelo em execução no servidor do Adobe Campaign. Há duas maneiras de obter um modelo e ativar o recurso:

* You can train a local model from the data of your previous email messages:

   * Se você já estiver usando o Adobe Campaign, o modelo local será treinado automaticamente nas mensagens que você já enviou.
   * Se você for novo no Adobe Campaign, poderá extrair um arquivo CSV do seu sistema anterior/ESP que contém 4 colunas: data, assunto, enviado, abre. Para fazer isso, vá até **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Email]** &gt; **[!UICONTROL Subject Line Import]** e siga as instruções fornecidas nas telas sucessivas. When the subject upload is complete, import a local model as described below. The local model is automatically trained with the data you uploaded.
   * If you are new to Adobe Campaign and cannot get a CSV file as described above, you can use a pre-trained model or wait until you have enough delivery data in your system to train a local model. The system will automatically determine whether your current data set contains enough data to recognize patterns and to train the model.

      >[!NOTE]
      >
      >Não há um número definido de linhas de assunto necessárias para treinar seu próprio modelo. Para a treinar, as linhas temáticas têm de ser variadas e não têm duplicações. Se não houver dados suficientes para processar, o sistema não poderá treinar o modelo. Você só pode ter um modelo treinado em sua instância.
   Para treinar um modelo local, baixe o subjectLineTraining.xml [aqui](https://support.neolane.net/webApp/downloadCenter?__userConfig=psaDownloadCenter) e use o recurso de importação [de](../../automating/using/managing-packages.md) pacote para carregá-lo para a instância do Adobe Campaign. Um fluxo de trabalho técnico fará automaticamente o treinamento para você.

   Na primeira vez que você deseja treinar um modelo, um administrador pode forçar o usuário a **[!UICONTROL SubjectLine Training workflow]** iniciar no menu **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Workflows]** .

   Depois que um modelo é carregado e treinado, o recurso é ativado automaticamente e uma nova opção é exibida ao lado do campo de linha de assunto das mensagens.

   Em seguida, o fluxo de trabalho técnico continuará automaticamente treinando seu modelo toda semana.

* Você pode importar modelos pré-treinados específicos para certas indústrias (médica, etc.) usando o recurso de importação [de](../../automating/using/managing-packages.md) pacote. These models are available here and cannot be trained.[](https://support.neolane.net/webApp/downloadCenter?__userConfig=psaDownloadCenter)

   Depois que um modelo é carregado, o recurso é ativado automaticamente e uma nova opção é exibida ao lado do campo de linha de assunto das mensagens.

>[!NOTE]
>
>Importar e gerar modelos treinados só podem ser executados por um administrador.

Os modelos disponíveis para uso são:

* Indústria cosmética: subjectInsightCosmetic.xml
* Supermarket industry: subjectInsightSupermarket.xml
* Medical industry: subjectInsightMedical.xml
* Model to train: subjectlineTraining.xml.
