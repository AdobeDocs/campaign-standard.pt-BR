---
title: Ativação de mapeamento
description: Saiba como ativar o mapeamento de dados
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Microsoft CRM Integration
old-role: Data Architect
role: Developer
level: Experienced
exl-id: d7ca0de6-7f7b-4e31-877c-909d962c5f53
hide: true
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: d5ef99fa-df0c-4153-bf94-105ad0724167
    internal-label: Integrations
subfeature_v2:
  - id: dd99420f-367d-4a14-bbc4-5140615992c2
    internal-label: Microsoft CRM integration
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '476'
ht-degree: 0%
---
# Ativação de mapeamento {#mapping-activation}

>[!IMPORTANT]
>
>O Conector de dados do Adobe Experience Platform está atualmente na versão beta, que pode estar sujeita a atualizações frequentes sem aviso prévio. Os clientes precisam ser hospedados na Azure (atualmente na versão beta somente para a América do Norte) para acessar esses recursos. Entre em contato com o Atendimento ao cliente da Adobe se desejar obter acesso.

Quando a definição de mapeamento for concluída, você poderá publicar o mapeamento. Após a etapa de implantação, a replicação de dados entre o Campaign Standard e o Adobe Experience Platform é iniciada automaticamente. A qualquer momento, você pode interromper a replicação clicando no botão **[!UICONTROL Stop]**.

Dependendo das modificações de mapeamento, você pode optar por reenviar todos os registros para o Adobe Experience Platform.

![](assets/aep_publishmapping.png)

No bloco de implantação, você pode acessar o log de publicação e os logs de exportação.

![](assets/aep_publog.png)

Na guia **[!UICONTROL Export jobs]**, é possível monitorar o trabalho de exportação para o mapeamento publicado.

![](assets/aep_jobstatus.png)

Se quiser monitorar todos os trabalhos de exportação de dados, vá para o menu **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Platform]** > **[!UICONTROL Status of data export to platform]**.

![](assets/aep_statusmapping.png)

Os status do trabalho de assimilação de dados são:

* **[!UICONTROL Created]**: um trabalho de assimilação de dados foi criado e a assimilação de dados está em andamento.
* **[!UICONTROL Failed]**: falha em um trabalho de assimilação de dados. O campo reason descreve o motivo da falha. A falha pode ser transitória ou permanente. Em caso de falhas transitórias, um novo trabalho de assimilação é criado após um intervalo configurado. Como primeira etapa na solução de problemas, o usuário pode verificar o campo de motivo da falha. Se o motivo redirecionar um usuário para a interface do usuário do Adobe Experience Platform, o usuário poderá fazer logon no Adobe Experience Platform e verificar o status do lote no conjunto de dados para determinar o motivo exato da falha.
* **[!UICONTROL Uploaded]**: um lote é criado primeiro no Adobe Experience Platform e os dados são assimilados no lote. O campo ID do lote mostra a ID do lote no Adobe Experience Platform. O Adobe Experience Platform também executa uma pós-validação no lote. O lote é marcado primeiro como carregado até que o Adobe Experience Platform conclua a etapa de pós-validação. Uma tarefa continua pesquisando no Adobe Experience Platform o status do lote após o upload. Um lote pode entrar no estado Falha ou Sucesso após a validação no Adobe Experience Platform.
* **[!UICONTROL Success]**: depois que um lote é carregado para o Adobe Experience Platform, o status do trabalho (pós-validação na plataforma) é verificado após um intervalo configurado. O status &quot;Sucesso&quot; identificou uma assimilação de dados bem-sucedida no Adobe Experience Platform.

Em alguns casos, você pode receber o erro de validação abaixo ao publicar seu mapeamento.

![](assets/aep_datamapping_ccpa.png)

Isso ocorre quando o esquema XDM que você está usando não foi atualizado com o campo XDM mais recente relacionado ao gerenciamento de privacidade e ainda contém o campo XDM &quot;ccpa&quot; obsoleto.

Para atualizar o esquema XDM, siga estas etapas:

1. Vá para o conjunto de dados no Adobe Experience Platform usando o link presente na página de mapeamento XDM.

1. Navegue até o esquema XDM.

1. Adicione o mixin **[!UICONTROL Profile Privacy]** ao esquema.

   ![](assets/aep_datamapping_privacyfield.png)

1. Salve o esquema e tente publicar o mapeamento novamente. A publicação agora deve passar.

   ![](assets/aep_save_mapping.png)
