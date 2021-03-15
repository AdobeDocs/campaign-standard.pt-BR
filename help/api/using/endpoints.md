---
solution: Campaign Standard
product: campaign
title: Desfechos
description: Saiba mais sobre os endpoints de APIs.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Engenheiro de dados
level: Experienciado
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '247'
ht-degree: 10%

---


# Desfechos {#endpoints}

Os endpoints disponíveis para a API REST do Adobe Campaign:

* **/profileAndServices**: interaja com os campos prontos para uso. Os campos estendidos não podem ser acessados com este ponto de extremidade.
* **/profileAndServicesExt**: interaja com campos personalizados adicionados durante a extensão de recurso personalizado Perfil ou Serviços . Para obter mais informações sobre recursos personalizados, consulte [esta seção](../../api/using/custom-resources.md).
* **/&lt;transactionalapi>**: interaja com a API de mensagens transacionais (o nome do endpoint da API de mensagens transacionais depende da configuração da instância). Para obter mais informações, consulte [esta seção](../../api/using/managing-transactional-messages.md).
* **/workflow/execution**: interagir com fluxos de trabalho. Para obter mais informações, consulte [esta seção](../../api/using/controlling-a-workflow.md).
* **/privacy/privacyTool**: interaja com a API de privacidade para permitir o processo automático de solicitações de privacidade. Para obter mais informações, consulte [esta seção](../../api/using/creating-a-privacy-request.md).
* **/histórico**: recupere o histórico de marketing dos perfis. Para obter mais informações sobre perfis de clientes integrados no Campaign, consulte a [documentação do Campaign](https://helpx.adobe.com/campaign/standard/audiences/using/integrated-customer-profile.html).

Por padrão, os principais recursos disponíveis para as APIs **profileAndServices** e **profileAndServicesExt** são:

* **/perfil**: interaja com perfis do banco de dados do Campaign. Para adicionar perfis a um serviço, use o terminal **/service**. Para obter mais informações sobre perfis no Campaign, consulte a [documentação do Campaign](https://helpx.adobe.com/campaign/standard/audiences/using/about-profiles.html).
* **/serviço**: gerenciar serviços de assinatura. Para obter mais informações sobre serviços no Campaign, consulte a [documentação do Campaign](https://helpx.adobe.com/campaign/standard/audiences/using/creating-a-service.html).

>[!NOTE]
>
>Todos os outros recursos que foram estendidos ou criados estão disponíveis somente por meio da API **ProfileAndServicesExt** . Eles devem estar vinculados ao recurso **Profile** para serem acessíveis.
