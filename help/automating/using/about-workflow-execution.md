---
solution: Campaign Standard
product: campaign
title: Monitoramento da execução de workflows
description: Saiba mais sobre a execução do workflow.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Fluxos de trabalho
role: Arquiteto de dados
level: Intermediário
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 9%

---


# Monitoramento da execução de workflows {#about-workflow-execution}

Um workflow é sempre iniciado manualmente. No entanto, uma vez iniciado, ele pode permanecer inativo, dependendo das informações especificadas em uma atividade [Scheduler](../../automating/using/scheduler.md).

>[!CAUTION]
>
> O Adobe recomenda que os clientes priorizem execuções de workflow e executem até vinte execuções de workflow simultâneas para alcançar consistentemente o máximo de desempenho em sua instância. Mais de vinte execuções simultâneas de workflow podem ser planejadas e serão executadas sequencialmente por padrão. Você pode ajustar as configurações padrão para o número máximo de execuções simultâneas de fluxo de trabalho enviando um ticket para o Atendimento ao cliente.

Ações relacionadas à execução (iniciar, parar, pausar etc.) são processos **assíncronos**: o comando é salvo e entrará em vigor assim que o servidor estiver disponível para aplicá-lo.

Em um workflow, o resultado de cada atividade geralmente é enviado para a atividade seguinte por meio de uma transição, representada por uma seta.

Uma transição não é finalizada se não estiver vinculada a uma atividade de destino.

![](assets/wkf_execution_1.png)

>[!NOTE]
>
>Um workflow contendo transições não finalizadas ainda pode ser executado: uma mensagem de aviso será gerada e o workflow será pausado assim que atingir a transição, mas isso não gerará um erro. Você também pode iniciar um fluxo de trabalho sem ter concluído completamente o design e pode concluí-lo conforme avança.

Depois que uma atividade é executada, o número de registros enviados na transição é exibido acima dela.

![](assets/wkf_transition_count.png)

É possível abrir transições para verificar se os dados enviados estão corretos durante ou após a execução do workflow. É possível exibir os dados e a estrutura dos dados.

Por padrão, somente os detalhes da última transição do workflow podem ser acessados. Para acessar os resultados das atividades anteriores, é necessário marcar a opção **[!UICONTROL Keep interim results]** na seção **[!UICONTROL Execution]** das propriedades do workflow, antes de iniciar o workflow.

>[!NOTE]
>
>Essa opção consome muita memória e foi projetada para ajudar a construir um fluxo de trabalho e garantir que ele esteja configurado e funcionando corretamente. Deixe-a desmarcada nas instâncias de produção.

Quando uma transição é aberta, você pode editar seu **[!UICONTROL Label]** ou vincular um **[!UICONTROL Segment code]** a ela. Para fazer isso, edite os campos correspondentes e confirme suas modificações.

Usando as APIs REST do Campaign Standard, você pode **iniciar**, **pausar**, **retomar** e **parar** um fluxo de trabalho. Você pode encontrar mais detalhes e exemplos de chamadas REST na documentação [API.](../../api/using/controlling-a-workflow.md)
