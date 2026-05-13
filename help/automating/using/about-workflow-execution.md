---
title: Sobre a execução de fluxo de trabalho
description: Saiba mais sobre a execução de workflow.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 3b95fc66-d6f4-44b2-be33-925c1109a57f
TQID: https://experienceleague.adobe.com/Fgr5Fy5R3xAe5QUwkNFA3k1y-nHDC5uqeCIJeEx7axI
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: b12f6872-9271-4369-85e5-86969a0b99a2
subfeature_v2: id: bf97c196-a4d1-4fa3-a151-e68a114c8ac0
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 354
ht-degree: 10%

---

# Sobre a execução de fluxo de trabalho {#about-workflow-execution}

Um fluxo de trabalho é sempre iniciado manualmente. No entanto, uma vez iniciado, ele pode permanecer inativo, dependendo das informações especificadas em uma atividade [Scheduler](../../automating/using/scheduler.md).

>[!IMPORTANT]
>
> A Adobe recomenda que os clientes não executem mais de 20 fluxos de trabalho ativos simultaneamente e priorizem e distribuam a execução do fluxo de trabalho ao longo do tempo. Para obter mais informações, consulte as práticas recomendadas fornecidas em [esta página](../../automating/using/best-practices-workflows.md).

Ações relacionadas à execução (iniciar, parar, pausar etc.) são processos **assíncronos**: o comando é salvo e entrará em vigor assim que o servidor estiver disponível para aplicá-lo.

Em um workflow, o resultado de cada atividade é geralmente enviado para a atividade seguinte por meio de uma transição, representada por uma seta.

Uma transição não é finalizada se não estiver vinculada a uma atividade de destino.

![](assets/wkf_execution_1.png)

>[!NOTE]
>
>Um fluxo de trabalho que contém transições não finalizadas ainda pode ser executado: uma mensagem de aviso será gerada e o fluxo de trabalho será pausado assim que atingir a transição, mas isso não gerará um erro. Você também pode iniciar um fluxo de trabalho sem ter concluído completamente o design e pode concluí-lo conforme avança.

Depois que uma atividade é executada, o número de registros enviados na transição é exibido acima dela.

![](assets/wkf_transition_count.png)

É possível abrir transições para verificar se os dados enviados estão corretos durante ou após a execução do fluxo de trabalho. É possível visualizar os dados e a estrutura de dados.

Por padrão, somente os detalhes da última transição do workflow podem ser acessados. Para acessar os resultados das atividades anteriores, você precisa verificar a opção **[!UICONTROL Keep interim results]** na seção **[!UICONTROL Execution]** das propriedades do fluxo de trabalho, antes de iniciar o fluxo de trabalho.

>[!NOTE]
>
>Essa opção consome muita memória e foi projetada para ajudar a criar um workflow e garantir que ele esteja configurado e se comportando corretamente. Deixe-a desmarcada nas instâncias de produção.

Quando uma transição está aberta, você pode editar sua **[!UICONTROL Label]** ou vincular uma **[!UICONTROL Segment code]** a ela. Para fazer isso, edite os campos correspondentes e confirme as modificações.

Usando as APIs REST do Campaign Standard, você pode **iniciar**, **pausar**, **retomar** e **parar** um fluxo de trabalho. Você pode encontrar mais detalhes e exemplos de chamadas REST na [documentação sobre APIs.](../../api/using/controlling-a-workflow.md)
