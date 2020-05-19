---
title: Sobre a execução do fluxo de trabalho
description: Saiba mais sobre a execução do fluxo de trabalho.
page-status-flag: never-activated
uuid: ff02b74e-53e8-49c6-bf8e-0c729eaa7d25
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 906c85ea-83b7-4268-86da-cd353f1dc591
context-tags: workflow,overview;workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 3ed78fd610b0d134cd1e60f34c93161cb1e5c50f
workflow-type: tm+mt
source-wordcount: '374'
ht-degree: 1%

---


# Sobre a execução do fluxo de trabalho {#about-workflow-execution}

Um workflow é sempre iniciado manualmente. No entanto, uma vez iniciado, ele pode permanecer inativo, dependendo das informações especificadas em uma atividade de [Scheduler](../../automating/using/scheduler.md) .

>[!CAUTION]
>
> A Adobe recomenda que os clientes priorizem execuções de fluxo de trabalho e executem até 20 execuções simultâneas de fluxo de trabalho para atingir de forma consistente o desempenho máximo em sua instância. Mais de vinte execuções de fluxo de trabalho simultâneas podem ser planejadas e serão executadas sequencialmente por padrão. Você pode ajustar as configurações padrão para o número máximo de execuções simultâneas de fluxo de trabalho enviando um ticket para o Atendimento ao cliente.

Ações relacionadas à execução (start, parada, pausa etc.) são processos **assíncronos** : o comando é salvo e entrará em vigor assim que o servidor estiver disponível para aplicá-lo.

Em um fluxo de trabalho, o resultado de cada atividade geralmente é enviado para a seguinte atividade por meio de uma transição, representada por uma seta.

Uma transição não será terminada se não estiver vinculada a uma atividade de destino.

![](assets/wkf_execution_1.png)

>[!NOTE]
>
>Um fluxo de trabalho contendo transições não finalizadas ainda pode ser executado: uma mensagem de aviso será gerada e o fluxo de trabalho pausará assim que chegar à transição, mas isso não gerará um erro. Você também pode start um fluxo de trabalho sem ter concluído completamente o design e pode concluí-lo conforme progride.

Depois que uma atividade é executada, o número de registros enviados na transição é exibido acima dela.

![](assets/wkf_transition_count.png)

Você pode abrir o transição para verificar se os dados enviados estão corretos durante ou após a execução do fluxo de trabalho. Você pode visualização os dados e a estrutura de dados.

Por padrão, somente os detalhes da última transição do fluxo de trabalho podem ser acessados. Para poder acessar os resultados das atividades anteriores, é necessário verificar a opção **[!UICONTROL Keep interim results]** na seção **[!UICONTROL Execution]** das propriedades do fluxo de trabalho antes de iniciar o fluxo de trabalho.

>[!NOTE]
>
>Essa opção consome muita memória e foi projetada para ajudar a construir um fluxo de trabalho e garantir que ele esteja configurado e se comportando corretamente. Deixe-o desmarcado em instâncias de produção.

Quando uma transição é aberta, você pode editá-la **[!UICONTROL Label]** ou vincular uma **[!UICONTROL Segment code]** a ela. Para fazer isso, edite os campos correspondentes e confirme suas modificações.

Usando APIs Campaign Standard REST, você pode **start**, **pausar**, **retomar** e **parar** um fluxo de trabalho. Você pode encontrar mais detalhes e exemplos de chamadas REST na documentação da [API.](../../api/using/controlling-a-workflow.md)
