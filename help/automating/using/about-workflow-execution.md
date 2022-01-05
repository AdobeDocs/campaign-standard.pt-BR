---
title: Sobre a execução de fluxo de trabalho
description: Saiba mais sobre a execução do workflow.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 3b95fc66-d6f4-44b2-be33-925c1109a57f
source-git-commit: 6ca3ffe3ba2cf7629e511e4ba035b170b25ad79e
workflow-type: tm+mt
source-wordcount: '353'
ht-degree: 10%

---

# Sobre a execução de fluxo de trabalho {#about-workflow-execution}

Um workflow é sempre iniciado manualmente. No entanto, uma vez iniciado, ele pode permanecer inativo, dependendo das informações especificadas em um [Scheduler](../../automating/using/scheduler.md) atividade .

>[!IMPORTANT]
>
> O Adobe recomenda que os clientes não executem mais de 20 workflows ativos simultaneamente e priorizem e distribuam a execução do workflow ao longo do tempo. Para obter mais informações, consulte as práticas recomendadas fornecidas em [esta página](../../automating/using/best-practices-workflows.md).

Ações relacionadas à execução (iniciar, parar, pausar etc.) são **assíncrono** processos: o comando é salvo e entrará em vigor assim que o servidor estiver disponível para aplicá-lo.

Em um workflow, o resultado de cada atividade geralmente é enviado para a atividade seguinte por meio de uma transição, representada por uma seta.

Uma transição não é finalizada se não estiver vinculada a uma atividade de destino.

![](assets/wkf_execution_1.png)

>[!NOTE]
>
>Um workflow contendo transições não finalizadas ainda pode ser executado: uma mensagem de aviso será gerada e o workflow será pausado assim que atingir a transição, mas isso não gerará um erro. Você também pode iniciar um fluxo de trabalho sem ter concluído completamente o design e pode concluí-lo conforme avança.

Depois que uma atividade é executada, o número de registros enviados na transição é exibido acima dela.

![](assets/wkf_transition_count.png)

É possível abrir transições para verificar se os dados enviados estão corretos durante ou após a execução do workflow. É possível exibir os dados e a estrutura dos dados.

Por padrão, somente os detalhes da última transição do workflow podem ser acessados. Para acessar os resultados das atividades anteriores, é necessário verificar a variável **[!UICONTROL Keep interim results]** na **[!UICONTROL Execution]** seção das propriedades do workflow, antes de iniciar o workflow.

>[!NOTE]
>
>Essa opção consome muita memória e foi projetada para ajudar a construir um fluxo de trabalho e garantir que ele esteja configurado e funcionando corretamente. Deixe-a desmarcada nas instâncias de produção.

Quando uma transição estiver aberta, você poderá editar sua **[!UICONTROL Label]** ou vincular um **[!UICONTROL Segment code]** a ela. Para fazer isso, edite os campos correspondentes e confirme suas modificações.

Com as APIs REST do Campaign Standard, é possível **start**, **pause**, **resume** e **stop** um fluxo de trabalho. Você pode encontrar mais detalhes e exemplos de chamadas REST no [Documentação da API.](../../api/using/controlling-a-workflow.md)
