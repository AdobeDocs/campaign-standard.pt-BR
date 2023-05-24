---
title: Pontos de acesso
description: Saiba mais sobre os endpoints das APIs.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 9f6d3da6-374d-47f5-bc8f-b31b19cbb5ca
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 10%

---

# Pontos de acesso {#endpoints}

Os endpoints disponíveis para a API REST do Adobe Campaign:

* **/profileAndServices**: interaja com os campos prontos para uso. Os campos estendidos não podem ser acessados com este endpoint.
* **/profileAndServicesExt**: interage com campos personalizados adicionados durante a extensão de recurso personalizado Perfil ou Serviços. Para obter mais informações sobre recursos personalizados, consulte [nesta seção](../../api/using/custom-resources.md).
* **/&lt;transactionalapi>**: interagir com a API de mensagens transacionais (o nome do endpoint da API de mensagens transacionais depende da configuração da instância). Para obter mais informações, consulte [esta seção](../../api/using/managing-transactional-messages.md).
* **/workflow/execution**: interagir com workflows. Para obter mais informações, consulte [esta seção](../../api/using/controlling-a-workflow.md).
* **/privacy/privacyTool**: interaja com a API de privacidade para permitir o processo automático de solicitações de privacidade. Para obter mais informações, consulte [esta seção](../../api/using/creating-a-privacy-request.md).
* **/history**: recupere o histórico de marketing dos perfis. Para obter mais informações sobre perfis de clientes integrados no Campaign, consulte o [Documentação da campanha](https://helpx.adobe.com/campaign/standard/audiences/using/integrated-customer-profile.html).

Por padrão, os principais recursos disponíveis para o **profileAndServices** e **profileAndServicesExt** As APIs são:

* **/profile**: interaja com perfis do banco de dados do Campaign. Para adicionar perfis a um serviço, use o **/service** terminal. Para obter mais informações sobre perfis no Campaign, consulte [Documentação da campanha](https://helpx.adobe.com/campaign/standard/audiences/using/about-profiles.html).
* **/service**: gerencie serviços de assinatura. Para obter mais informações sobre os serviços no Campaign, consulte a [Documentação da campanha](https://helpx.adobe.com/campaign/standard/audiences/using/creating-a-service.html).

>[!NOTE]
>
>Todos os outros recursos que foram estendidos ou criados estão disponíveis por meio do **ProfileAndServicesExt** Somente API. Eles devem estar vinculados à variável **Perfil** para ser acessível.
