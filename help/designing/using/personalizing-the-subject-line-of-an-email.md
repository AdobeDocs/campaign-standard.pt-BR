---
title: Personalização da linha de assunto de um email
seo-title: Personalização da linha de assunto de um email
description: Personalização da linha de assunto de um email
seo-description: Você pode personalizar o assunto de um email, mas também testar linhas de assunto diferentes e obter uma estimativa de sua taxa aberta.
page-status-flag: nunca ativado
uuid: 345 b 5 f 4 b -8 e 2 c -4 f 8 e-bce 7-0 e 9 b 40 a 44932
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: personalização-conteúdo
discoiquuid: f 7 a 5 e 935-54 cf -422 e -8459-27221409 a 200
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 782a5f89b0361f1cbe59c9b353ca90dec90c3906

---


# Personalização da linha de assunto de um email{#personalizing-the-subject-line-of-an-email}

## Personalização de um assunto de email {#personalizing-an-email-subject}

O assunto da mensagem é obrigatório para preparar e enviar a mensagem.

>[!NOTE]
>
>Se a linha de assunto estiver vazia, um aviso será exibido no painel de mensagens e no Designer de e-mail.

Para configurar o assunto do e-mail, vá para **[!UICONTROL Properties]** a guia inicial do Designer de email (acessível através do ícone inicial) e preencha a **[!UICONTROL Subject]** seção.

![](assets/email_designer_subject.png)

Você também pode adicionar campos de personalização, blocos de conteúdo e conteúdo dinâmico à linha de assunto clicando nos ícones correspondentes.

**Tópicos relacionados:**

* [Inserir um campo de personalização](../../designing/using/inserting-a-personalization-field.md)
* [Adicionar um bloco de conteúdo](../../designing/using/adding-a-content-block.md)
* [Definição de conteúdo dinâmico em um email](../../designing/using/defining-dynamic-content-in-an-email.md)

## Linha de assunto preditiva {#predictive-subject-line}

Ao editar um e-mail, você pode testar linhas de assunto diferentes e obter uma estimativa de sua taxa aberta antes de enviá-la.

Esse recurso está desativado por padrão. Ele é ativado quando o primeiro modelo é importado. Um modelo é o resultado dos conjuntos de dados de treinamento específicos para um determinado setor. Os modelos permitem que o sistema preveja a taxa aberta do email quando uma nova linha de assunto é enviada.

>[!NOTE]
>
>Esse recurso está disponível para mensagens de email e para bancos de dados que contenham apenas conteúdo em inglês. O modelo treinados será inconsistente e resultará em resultados errôneos se sua instância contiver emails em outros idiomas. A opção que permite testar um assunto é visível somente se um modelo já estiver disponível na sua instância.

### Teste de um assunto {#testing-a-subject}

Para testar a linha de assunto:

1. Crie ou abra seu e-mail.
1. Abra o conteúdo e digite o assunto do email no campo de entrada correspondente.
1. Clique no **[!UICONTROL Test subject]** botão para acessar a **[!UICONTROL Test your subject line]** janela. Você ainda pode editar o assunto desta janela.
1. Selecione o modelo correto a ser considerado para a previsão de taxa aberta. Vários modelos estão disponíveis, cada um correspondendo a um setor específico.
1. Click **[!UICONTROL Test]**.

Em seguida, seu assunto é analisado.

>[!NOTE]
>
>Se a linha de assunto for muito curta, ela não poderá ser analisada e uma mensagem de erro será exibida.

Vários indicadores são calculados e um conjunto de ferramentas é exibido para ajudá-lo a:

* **Taxa de abertura prevista**: Este gráfico fornece uma ideia da taxa aberta que pode ser esperada para o email com o assunto atual.
* **Extensão do assunto**: Esse indicador permite ver se o comprimento atual do assunto está correto ou se deve ser maior ou menor.
* **Palavras coloridas**: Ao testar o assunto, palavras destacadas em verde são as palavras que mais contribuem para aumentar a previsão de taxa aberta. Palavras destacadas em vermelho são as palavras que contribuem para aumentar a previsão de taxa aberta. Se você adicionar ou remover palavras no assunto, palavras destacadas serão alteradas.
* **Categorias e sugestões de palavras**: Na parte inferior da janela, são exibidas várias categorias relevantes para o modelo selecionado. Essas categorias são classificadas por ordem de importância e permitem que você veja se o assunto contém palavras associadas a ele através de um símbolo de verificação. Cada categoria contém um conjunto de palavras sugeridas que podem ser usadas em seu assunto para torná-lo mais relevante e aumentar a taxa aberta. Essas palavras são usadas com mais frequência em uma categoria específica.

>[!NOTE]
>
>Os campos de personalização e marcas de pontuação são removidos da análise de assunto. No caso de texto dinâmico/condicional, todas as variantes são consideradas uma linha de assunto.

![](assets/predictive_subject_line_example.png)

### Importação de modelos {#importing-models}

Por padrão, não há modelo em execução no servidor do Adobe Campaign. Há duas maneiras de obter um modelo e ativar o recurso:

* É possível treinar um modelo local a partir dos dados de suas mensagens de email anteriores:

   * Se você já estiver usando o Adobe Campaign, o modelo local será treinado automaticamente nas mensagens que você já enviou.
   * Se você for novo no Adobe Campaign, poderá extrair um arquivo CSV do sistema/ESP anterior que contém 4 colunas: data, assunto, enviado, abre. Para fazer isso, vá **[!UICONTROL Administration]** para &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Email]** &gt; **[!UICONTROL Subject Line Import]** e siga as instruções fornecidas nas telas sucessivas. Quando o upload do assunto for concluído, importe um modelo local como descrito abaixo. O modelo local é treinado automaticamente com os dados carregados.
   * Se você for novo no Adobe Campaign e não puder obter um arquivo CSV como descrito acima, poderá usar um modelo pré-treinado ou aguardar até que você tenha dados de entrega suficientes em seu sistema para treinar um modelo local. O sistema determinará automaticamente se o conjunto de dados atual contém dados suficientes para reconhecer padrões e para formar o modelo.

      >[!NOTE]
      >
      >Não há um número definido de linhas de assunto necessárias para treinar seu próprio modelo. Para poder treinar, as linhas de assunto precisam ser variadas e não devem ser duplicadas. Se não houver dados suficientes para processar, o sistema não conseguirá treinar o modelo. Você pode ter apenas um modelo treinado na sua instância.
   Para treinar um modelo local, faça download do subjectLineTraining.xml [aqui](https://support.neolane.net/webApp/downloadCenter?__userConfig=psaDownloadCenter) e use o recurso [de importação](../../automating/using/managing-packages.md) do pacote para carregá-lo para a instância do Adobe Campaign. Um fluxo de trabalho técnico fará automaticamente o treinamento para você.

   Na primeira vez que você deseja treinar um modelo, um administrador pode **[!UICONTROL SubjectLine Training workflow]** forçar o início do menu **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Workflows]** .

   Depois que um modelo é carregado e treinado, o recurso é ativado automaticamente e uma nova opção aparece ao lado do campo de linha de assunto das suas mensagens.

   Em seguida, o fluxo de trabalho técnico continuará a treinar automaticamente seu modelo toda semana.

* É possível importar modelos pré-treinados específicos para certos setores (médicos etc.) usando o recurso [de importação](../../automating/using/managing-packages.md) do pacote. Esses modelos estão disponíveis [aqui](https://support.neolane.net/webApp/downloadCenter?__userConfig=psaDownloadCenter) e não podem ser treinados.

   Quando um modelo for carregado, o recurso será ativado automaticamente e uma nova opção será exibida ao lado do campo de linha de assunto das suas mensagens.

>[!NOTE]
>
>A importação e geração de modelos treinados pode ser executada somente por um administrador.

Os modelos disponíveis para uso são:

* Setor cosmético: subjectInsightCosmetic.xml
* Setor de supermercado: subjectInsightSupermarket.xml
* Setor médico: subjectInsightMedical.xml
* Modelo para treinar: Subjectlinetraining. xml.

**Tópico relacionado:**

* [Otimizar linhas de assunto com previsões do Adobe Sensei](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Createcompellingcontenttailoredtoeveryindividual)
