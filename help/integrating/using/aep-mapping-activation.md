---
solution: Campaign Standard
product: campaign
title: Ativação de mapeamento
description: Saiba como ativar o mapeamento de dados
audience: administration
content-type: reference
topic-tags: configuring-channels
translation-type: tm+mt
source-git-commit: 35d61efce8d752ea30b7eaad55e6c23d4debd853
workflow-type: tm+mt
source-wordcount: '476'
ht-degree: 0%

---


# Ativação de mapeamento {#mapping-activation}

>[!IMPORTANT]
>
>O Conector de dados da Adobe Experience Platform está atualmente em beta, que pode estar sujeito a atualizações frequentes sem aviso prévio. Os clientes precisam ser hospedados no Azure (atualmente em beta somente para a América do Norte) para acessar esses recursos. Entre em contato com o Atendimento ao cliente da Adobe se desejar acesso.

Quando a definição de mapeamento for concluída, você poderá publicar o mapeamento. Após a etapa de implantação, a replicação de dados entre o Campaign Standard e a Adobe Experience Platform é iniciada automaticamente. A qualquer momento, você pode interromper a replicação clicando no botão **[!UICONTROL Stop]** .

Dependendo das modificações de mapeamento, você pode optar por reenviar todos os registros para a Adobe Experience Platform.

![](assets/aep_publishmapping.png)

No bloco de implantação , é possível acessar o log de publicação e os logs de exportação.

![](assets/aep_publog.png)

Na guia **[!UICONTROL Export jobs]**, é possível monitorar o trabalho de exportação para o mapeamento publicado.

![](assets/aep_jobstatus.png)

Para monitorar todos os trabalhos de exportação de dados, vá para o menu **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Platform]** > **[!UICONTROL Status of data export to platform]** .

![](assets/aep_statusmapping.png)

Os status do trabalho de assimilação de dados são:

* **[!UICONTROL Created]**: Um trabalho de assimilação de dados é criado e a assimilação de dados está em andamento.
* **[!UICONTROL Failed]**: Falha no trabalho de assimilação de dados. O campo reason descreve o motivo da falha. A falha pode ser transitória ou permanente. No caso de falhas transitórias, um novo trabalho de assimilação é criado após um intervalo configurado. Como primeiro passo para a solução de problemas, o usuário pode verificar o campo do motivo da falha. Se o motivo redirecionar um usuário para a interface do usuário da Adobe Experience Platform, o usuário poderá fazer logon na Adobe Experience Platform e verificar o status do lote no conjunto de dados para determinar o motivo exato da falha.
* **[!UICONTROL Uploaded]**: Um lote é criado primeiro na Adobe Experience Platform e os dados são assimilados no lote. O campo ID do lote mostra a ID do lote para o lote na Adobe Experience Platform. A Adobe Experience Platform também executa uma validação de postagem no lote. O lote é marcado pela primeira vez como carregado até que a Adobe Experience Platform conclua a etapa de validação da publicação. Um trabalho continua pesquisando o status do lote na Adobe Experience Platform após o upload. Um lote pode ser acessado em Falha ou no estado de sucesso após a validação na Adobe Experience Platform.
* **[!UICONTROL Success]**: Depois que um lote é carregado na Adobe Experience Platform, o status da tarefa (pós-validação na plataforma) é verificado após um intervalo configurado. Um status &quot;Sucesso&quot; identificou uma assimilação bem-sucedida de dados na Adobe Experience Platform.

Em alguns casos, você pode receber o erro de validação abaixo ao publicar o mapeamento.

![](assets/aep_datamapping_ccpa.png)

Isso ocorre quando o esquema XDM que você está usando não foi atualizado com o campo XDM mais recente relacionado ao gerenciamento de privacidade e ainda contém o campo XDM &quot;cpa&quot; obsoleto.

Para atualizar o esquema XDM, siga estas etapas:

1. Vá para o conjunto de dados na Adobe Experience Platform usando o link presente na página de mapeamento XDM.

1. Navegue até o esquema XDM.

1. Adicione o mixin **[!UICONTROL Profile Privacy]** ao schema.

   ![](assets/aep_datamapping_privacyfield.png)

1. Salve o esquema e tente publicar novamente o mapeamento. A publicação agora deve ser bem-sucedida.

   ![](assets/aep_save_mapping.png)
