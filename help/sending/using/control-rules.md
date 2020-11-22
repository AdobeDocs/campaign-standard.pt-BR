---
solution: Campaign Standard
product: campaign
title: Regras de controle
description: Saiba como reforçar a verificação de qualidade de suas mensagens com regras de controle.
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 17%

---


# Regras de controle {#control-rules}

As regras de controle permitem que você verifique a validade e a qualidade das mensagens antes de serem enviadas, como exibição de caracteres, tamanho da mensagem SMS, formato de endereço, etc.

>[!NOTE]
>
>Por motivos de segurança, as regras de controle são somente leitura e não podem ser modificadas.

## Regras de controle padrão {#default-control-rules}

Um conjunto de regras padrão garante os controles padrão. A tabela abaixo fornece informações sobre essas regras, bem como sobre as respectivas fases [de canal e](#control-rules-execution-phases)execução.

| Rótulo | Canal  | Fase de execução | Descrição |
---------|----------|---------|---------
| **[!UICONTROL A/B Test]** | Email | At the start of personalization | Extrai a população de teste para um delivery com um teste A/B. |
| **[!UICONTROL Check delivery size]** | Todos | After targeting | Verifica o tamanho das mensagens. |
| **[!UICONTROL Check email content is not empty]** | Email | After targeting | Gera um erro se o conteúdo da mensagem estiver vazio. |
| **[!UICONTROL Check In-App content for broadcast template]** | No aplicativo | Na personalização do start | Verifica se o conteúdo/acionadores no aplicativo não estão vazios para o modelo de transmissão. |
| **[!UICONTROL Check In-App content for profile template]** | No aplicativo | At the start of personalization | Verifica se o conteúdo / acionadores no aplicativo não estão vazios para o modelo de perfil. |
| **[!UICONTROL Check In-App content for subscriber template]** | No aplicativo | At the start of personalization | Verifica se o conteúdo/acionadores no aplicativo não estão vazios para o modelo do assinante. |
| **[!UICONTROL Check proof size]** | Todos | After targeting | Gera uma mensagem de erro se a população do público alvo da prova exceder 100 recipient. |
| **[!UICONTROL Check social network sharing link]** | Email | At the start of personalization | Verifica a presença de um link para um mirror page ao incluir um link de compartilhamento de rede social (ViralLinks) no conteúdo. |
| **[!UICONTROL Check subject]** | Email | At the start of personalization | Verifica se o assunto e o endereço do remetente não contêm caracteres especiais que possam causar problemas em determinados agentes de transferência de email e verifica se o assunto da mensagem foi preenchido. |
| **[!UICONTROL Check unsubscription link]** | Email | At the start of personalization | Verifica a presença de pelo menos um URL de unsubscription (opção de não participação) em cada conteúdo (HTML e Texto). |
| **[!UICONTROL Check URL labels]** | Email | At the start of personalization | Verifica se cada URL de rastreamento tem um rótulo. |
| **[!UICONTROL Check URLs]** | Email | At the start of personalization | Verifica os URLs de rastreamento (presença do caractere &quot;&amp;&quot;). |

## Fases de execução das regras de controle {#control-rules-execution-phases}

As regras de controlo podem ser aplicadas em diferentes fases do ciclo de vida do delivery:

* **No start da definição de metas**: A regra de controle pode ser aplicada nesta fase para que a etapa de personalização não seja executada no evento de um erro.

* **Após a definição de metas**: Executar após a definição de metas permite que você saiba o volume do público alvo para aplicar a regra de controle.

   For example, the **Check proof size** control rule applies after the targeting stage: this rule prevents the preparation of message personalization if there are too many proof recipients.

* **No start da personalização**: Aplica-se quando a verificação está relacionada à aprovação da personalização da mensagem. A personalização da mensagem é realizada durante a fase de análise.

* **At the end of the analysis**: Quando uma verificação exigir que a personalização da mensagem seja concluída.
