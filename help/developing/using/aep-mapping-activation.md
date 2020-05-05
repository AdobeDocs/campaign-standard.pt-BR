---
title: Ativação de mapeamento
description: Saiba como ativar o mapeamento de dados
page-status-flag: never-activated
uuid: 867b1c4b-4c79-4c52-9d0a-ef71993e50a2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 406c955a-b2d2-4099-9918-95f5fa966067
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c2ed4b3c85ceef3b604a8f68d924c7e5d9fad900

---


# Ativação de mapeamento {#mapping-activation}

>[!IMPORTANT]
>
>O Adobe Experience Platform Data Connector está atualmente em beta, que pode estar sujeito a atualizações frequentes sem aviso prévio. Os clientes precisam estar hospedados no Azure (atualmente em beta somente para a América do Norte) para acessar esses recursos. Entre em contato com o Atendimento ao cliente da Adobe se desejar acessar.

Quando a definição de mapeamento for concluída, você poderá publicar o mapeamento. Após a etapa de implantação, a replicação de dados entre o Campaign Standard e a Adobe Experience Platform é iniciada automaticamente. A qualquer momento, você pode interromper a replicação clicando no **[!UICONTROL Stop]** botão.

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
* **[!UICONTROL Failed]**: Falha em um trabalho de ingestão de dados. O campo reason descreve o motivo da falha. A falha pode ser transitória ou permanente. Em caso de falhas transitórias, um novo trabalho de ingestão é criado após um intervalo configurado. Como primeira etapa para a solução de problemas, o usuário pode verificar o campo do motivo da falha. Se o motivo redirecionar um usuário para a interface do usuário da Adobe Experience Platform, o usuário poderá fazer logon na Adobe Experience Platform e verificar o status do lote no conjunto de dados para determinar o motivo exato da falha.
* **[!UICONTROL Uploaded]**: Um lote é criado pela primeira vez no Adobe Experience Platform e os dados são assimilados ao lote. O campo ID do lote mostra a ID do lote para o lote no Adobe Experience Platform. O Adobe Experience Platform também executa uma validação de postagem no lote. O lote é marcado como carregado pela primeira vez até que o Adobe Experience Platform conclua a etapa de validação da publicação. Uma tarefa continua pesquisando o status do lote no Adobe Experience Platform após o upload. Um lote pode ir na validação de publicação em estado de falha ou de sucesso na Adobe Experience Platform.
* **[!UICONTROL Success]**: Depois que um lote é carregado no Adobe Experience Platform, o status do trabalho (validação da postagem na plataforma) é verificado após um intervalo configurado. Um status &quot;Êxito&quot; identificou uma assimilação bem-sucedida de dados na Adobe Experience Platform.
