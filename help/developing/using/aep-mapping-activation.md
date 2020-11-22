---
solution: Campaign Standard
product: campaign
title: Ativação de mapeamento
description: Saiba como ativar o mapeamento de dados
audience: administration
content-type: reference
topic-tags: configuring-channels
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 1%

---


# Ativação de mapeamento {#mapping-activation}

>[!IMPORTANT]
>
>O Adobe Experience Platform Data Connector está atualmente em beta, o que pode estar sujeito a atualizações frequentes sem aviso prévio. Os clientes precisam estar hospedados no Azure (atualmente em beta somente para a América do Norte) para acessar esses recursos. Entre em contato com o Atendimento ao cliente do Adobe se desejar acessá-lo.

Quando a definição de mapeamento for concluída, você poderá publicar o mapeamento. Após a etapa de implantação, a replicação de dados entre o Campaign Standard e o Adobe Experience Platform é iniciada automaticamente. A qualquer momento, você pode interromper a replicação clicando no **[!UICONTROL Stop]** botão.

Dependendo das modificações de mapeamento, você pode optar por reenviar todos os registros para a Adobe Experience Platform.

![](assets/aep_publishmapping.png)

No bloco de implantação, você pode acessar o log de publicação e os logs de exportação.

![](assets/aep_publog.png)

Na **[!UICONTROL Export jobs]** guia, é possível monitorar a tarefa de exportação para o mapeamento publicado.

![](assets/aep_jobstatus.png)

Se você quiser monitorar todas as tarefas de exportação de dados, vá para **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Platform]** > **[!UICONTROL Status of data export to platform]** menu.

![](assets/aep_statusmapping.png)

Status do trabalho de ingestão de dados:

* **[!UICONTROL Created]**: Um trabalho de ingestão de dados é criado e a ingestão de dados está em andamento.
* **[!UICONTROL Failed]**: Falha em um trabalho de ingestão de dados. O campo reason descreve o motivo da falha. A falha pode ser transitória ou permanente. Em caso de falhas transitórias, um novo trabalho de ingestão é criado após um intervalo configurado. Como primeira etapa para a solução de problemas, o usuário pode verificar o campo do motivo da falha. Se o motivo redirecionar um usuário para a interface do usuário do Adobe Experience Platform, o usuário poderá fazer logon no Adobe Experience Platform e verificar o status do lote no conjunto de dados para determinar o motivo exato da falha.
* **[!UICONTROL Uploaded]**: Um lote é criado primeiro no Adobe Experience Platform e os dados são ingeridos no lote. O campo ID do lote mostra a ID do lote para o lote no Adobe Experience Platform. A Adobe Experience Platform também executa uma validação de postagem no lote. O lote é marcado primeiro como carregado até que a Adobe Experience Platform conclua a etapa de validação posterior. Uma tarefa continua pesquisando o status do lote no Adobe Experience Platform após o upload. Um lote pode ir na validação de publicação em estado de falha ou de sucesso no Adobe Experience Platform.
* **[!UICONTROL Success]**: Depois que um lote é carregado no Adobe Experience Platform, o status do trabalho (validação de publicação na plataforma) é verificado após um intervalo configurado. Um status &quot;Êxito&quot; identificou uma ingestão bem-sucedida de dados no Adobe Experience Platform.
