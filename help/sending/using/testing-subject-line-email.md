---
title: Teste da linha de assunto de um email
description: Descubra como definir a linha de assunto de um email no Designer de email.
page-status-flag: never-activated
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7e61796376a14c279d38107905275172be0dd12d

---

# Teste da linha de assunto de um email {#testing-a-subject}

Para testar sua linha de assunto, siga as etapas abaixo:

1. Crie ou abra seu email.
1. Abra o conteúdo e digite o assunto do email no campo de entrada correspondente.
1. Clique no **[!UICONTROL Test subject]** botão para acessar a **[!UICONTROL Test your subject line]** janela. Você ainda pode editar o assunto desta janela.
1. Selecione o modelo correto a ser considerado para a previsão de taxa aberta. Estão disponíveis vários modelos, cada um correspondente a um setor específico.
1. Clique em **[!UICONTROL Test]**.

Seu assunto é então analisado.

>[!NOTE]
>
>Se a linha de assunto for muito curta, ela não poderá ser analisada e uma mensagem de erro será exibida.

Vários indicadores são calculados e um conjunto de ferramentas é exibido para ajudá-lo a:

* **Taxa** de abertura prevista: Este gráfico fornece uma ideia da taxa de abertura que você pode esperar do email com seu assunto atual.
* **Duração** do assunto: Esse indicador permite que você veja se o comprimento atual do assunto está correto ou se ele precisaria ser maior ou menor.
* **Palavras** coloridas: Ao testar o assunto, palavras destacadas em verde são as que mais contribuem para aumentar a previsão de taxa aberta. Palavras destacadas em vermelho são as que menos contribuem para aumentar a previsão de taxa aberta. Se você adicionar ou remover palavras no assunto, as palavras destacadas serão alteradas.
* **Categorias e sugestões** de palavras: Na parte inferior da janela, são exibidas várias categorias relevantes para o modelo selecionado. Essas categorias são classificadas por ordem de importância e permitem que você veja se o assunto contém palavras associadas a ele por meio de um símbolo de verificação. Cada categoria contém um conjunto de palavras sugeridas que podem ser usadas em seu assunto para torná-lo mais relevante e aumentar a taxa aberta. Essas palavras são as palavras mais usadas em uma determinada categoria.

>[!NOTE]
>
>Os campos de personalização e os sinais de pontuação são retirados da análise de assunto. No caso de texto dinâmico/condicional, todas as variantes são consideradas como uma única linha de assunto.

![](assets/predictive_subject_line_example.png)

## Importação de modelos {#importing-models}

Por padrão, não há modelo em execução no servidor do Adobe Campaign. Há duas maneiras de obter um modelo e ativar o recurso:

* Você pode treinar um modelo local a partir dos dados de suas mensagens de email anteriores:

   * Se você já estiver usando o Adobe Campaign, o modelo local será treinado automaticamente nas mensagens que você já enviou.
   * Se você for novo no Adobe Campaign, poderá extrair um arquivo CSV do seu sistema anterior/ESP que contém 4 colunas: data, assunto, abre, enviado. Para fazer isso, vá até **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Email]** > **[!UICONTROL Subject Line Import]** e siga as instruções fornecidas nas telas sucessivas. Quando o upload do assunto estiver concluído, importe um modelo local conforme descrito abaixo. O modelo local é treinado automaticamente com os dados carregados.
   * Se você for novo no Adobe Campaign e não conseguir obter um arquivo CSV conforme descrito acima, poderá usar um modelo pré-treinado ou aguardar até que tenha dados de entrega suficientes no sistema para treinar um modelo local. O sistema determinará automaticamente se seu conjunto de dados atual contém dados suficientes para reconhecer padrões e treinar o modelo.

      >[!NOTE]
      >
      >Não há um número definido de linhas de assunto necessárias para treinar seu próprio modelo. Para a treinar, as linhas temáticas têm de ser variadas e não têm duplicações. Se não houver dados suficientes para processar, o sistema não poderá treinar o modelo. Você só pode ter um modelo treinado em sua instância.
   Para treinar um modelo local, baixe o subjectLineTraining.xml [aqui](https://support.neolane.net/webApp/downloadCenter?__userConfig=psaDownloadCenter) e use o recurso de importação [de](../../automating/using/managing-packages.md) pacote para carregá-lo para a instância do Adobe Campaign. Um fluxo de trabalho técnico fará automaticamente o treinamento para você.

   Na primeira vez que você deseja treinar um modelo, um administrador pode forçar o usuário a **[!UICONTROL SubjectLine Training workflow]** iniciar no menu **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Workflows]** .

   Depois que um modelo é carregado e treinado, o recurso é ativado automaticamente e uma nova opção é exibida ao lado do campo de linha de assunto das mensagens.

   Em seguida, o fluxo de trabalho técnico continuará automaticamente treinando seu modelo toda semana.

* Você pode importar modelos pré-treinados específicos para certas indústrias (médica, etc.) usando o recurso de importação [de](../../automating/using/managing-packages.md) pacote. Para acessar esses modelos, clique [aqui](https://support.neolane.net/webApp/extranetLogin) e vá para **[Centro]** de downloads. Esses modelos não podem ser treinados.

   Depois que um modelo é carregado, o recurso é ativado automaticamente e uma nova opção é exibida ao lado do campo de linha de assunto das mensagens.

>[!NOTE]
>
>Importar e gerar modelos treinados só podem ser executados por um administrador.

Os modelos disponíveis para uso são:

* Indústria cosmética: subjectInsightCosmetic.xml
* Indústria de supermercados: subjectInsightSupermarket.xml
* Indústria médica: subjectInsightMedical.xml
* Modelo de comboio: subjettlineTraining.xml.
