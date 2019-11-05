---
title: Regras de controle
description: Saiba como reforçar a verificação de qualidade de suas mensagens com regras de controle.
page-status-flag: nunca ativado
uuid: 33a1c90c-534e-4fe1-982c-f4e1858d4d2d
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: administração
content-type: referência
topic-tags: regras de trabalho com tipologia
discoiquuid: 305cadde-6424-4c6f-b11b-1e8bdbad6ef1
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Regras de controle{#control-rules}

As regras de controle permitem que o usuário verifique a validade e a qualidade das mensagens antes de serem enviadas, como exibição de caracteres, tamanho da mensagem SMS, formato de endereço, etc.

Um conjunto de regras padrão disponível no Adobe Campaign garante os controles padrão:

* **[!UICONTROL Check subject]** (email): verifica se o assunto e o endereço do remetente não contêm caracteres especiais que possam causar problemas em determinados agentes de transferência de correio e verifica se o assunto da mensagem foi preenchido.
* **[!UICONTROL Check URL labels]** (email): verifica se cada URL de rastreamento tem um rótulo.
* **[!UICONTROL Check URLs]** (email): verifica os URLs de rastreamento (presença do caractere "&amp;").
* **[!UICONTROL Check proof size]** (todos os canais): gera uma mensagem de erro se o público-alvo da prova exceder 100 destinatários.
* **Verifique o link** de cancelamento de assinatura (email): verifica se há pelo menos um URL de cancelamento de assinatura (opção de não participação) em cada conteúdo (HTML e Texto).
* **[!UICONTROL Check delivery size]** (todos os canais): verifica o tamanho das mensagens.
* **[!UICONTROL Check social network sharing link]** (email): verifica a presença de um link para uma página espelhada ao incluir um link de compartilhamento de rede social (ViralLinks) no conteúdo.
* **[!UICONTROL A/B Test]**: extrai a população de teste para uma entrega com um teste A/B.

Você pode escolher o momento em que a regra será aplicada de uma das fases do ciclo de vida da entrega. Selecione o valor a ser aplicado na lista suspensa no **[!UICONTROL Phase]** campo da regra de tipologia.

![](assets/typology_phase.png)

Os valores possíveis são:

* **No início da definição de metas**

   A regra de controle pode ser aplicada nesta fase para que a etapa de personalização não seja executada em caso de erro.

* **Após a definição de metas**

   Se é necessário saber o target para aplicar a regra de controle, selecione essa fase.

   For example, the **Check proof size** control rule applies after the targeting stage: this rule prevents the preparation of message personalization if there are too many proof recipients.

* **No início da personalização**

   Essa fase deve ser selecionada se a verificação disser respeito à aprovação da personalização da mensagem. A personalização da mensagem é realizada durante a fase de análise.

* **No final da análise**

   Quando uma verificação exige a personalização da mensagem para ser concluída, selecione essa fase.

>[!NOTE]
>
>Por motivos de segurança, o conteúdo das regras de controle não pode ser modificado. O **[!UICONTROL Code]** campo é somente leitura.
