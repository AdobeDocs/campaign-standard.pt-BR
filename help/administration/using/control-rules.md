---
title: Regras de controle
seo-title: Regras de controle
description: Regras de controle
seo-description: Saiba como reforçar a verificação de qualidade das mensagens com as regras de controle.
page-status-flag: nunca ativado
uuid: 33 a 1 c 90 c -534 e -4 fe 1-982 c-f 4 e 1858 d 4 d 2 d
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: regras de trabalho com informações de typologia
discoiquuid: 305 cadde -6424-4 c 6 f-b 11 b -1 e 8 bdbad 6 ef 1
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6a877d878f01fa1e541dc20b8b0941602113d15b

---


# Control rules{#control-rules}

As regras de controle permitem que o usuário verifique a validade e a qualidade das mensagens antes de serem enviadas, como a exibição de caracteres, tamanho de mensagem SMS, formato de endereço etc.

Um conjunto de regras padrão disponíveis no Adobe Campaign garante os controles padrão:

* **[!UICONTROL Check subject]** (email): verifica se o assunto e o endereço do remetente não contêm caracteres especiais que podem causar problemas em determinados agentes de transferência de email e verifica se o assunto da mensagem foi concluído.
* **[!UICONTROL Check URL labels]** (email): verifica se cada URL de rastreamento tem um rótulo.
* **[!UICONTROL Check URLs]** (email): verifica os urls de rastreamento (presença do caractere " &amp;").
* **[!UICONTROL Check proof size]** (todos os canais): gera uma mensagem de erro se a população alvo de prova exceder 100 destinatários.
* **Verificar link de cancelamento de assinatura** (email): verifica a presença de pelo menos um URL cancelado de assinatura em cada conteúdo (HTML e Texto).
* **[!UICONTROL Check delivery size]** (todos os canais): verifica o tamanho das mensagens.
* **[!UICONTROL Check social network sharing link]** (email): verifica a presença de um link para uma página espelhada ao incluir um link de compartilhamento de rede social (virallinks) no conteúdo.
* **[!UICONTROL A/B Test]**: extrai o preenchimento do teste de uma entrega com um teste A/B.

Você pode escolher o momento em que a regra será aplicada a partir de uma das fases do ciclo de vida da entrega. Select the value to apply in the drop-down list from the **[!UICONTROL Phase]** field of the typology rule.

![](assets/typology_phase.png)

Os valores possíveis são:

* **No início da definição de metas**

   A regra de controle pode ser aplicada nessa fase para que a etapa de personalização não seja executada em caso de erro.

* **Após o direcionamento**

   Se você precisar saber o volume da meta para aplicar a regra de controle, selecione essa fase.

   For example, the **Check proof size** control rule applies after the targeting stage: this rule prevents the preparation of message personalization if there are too many proof recipients.

* **No início da personalização**

   Essa fase deve ser selecionada se a verificação estiver relacionada à aprovação da personalização da mensagem. A personalização de mensagens é realizada durante a fase de análise.

* **No fim da análise**

   Quando uma verificação exigir que a personalização de mensagem seja concluída, selecione essa fase.

