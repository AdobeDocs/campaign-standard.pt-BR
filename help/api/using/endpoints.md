---
title: Pontos de acesso
description: Saiba mais sobre os endpoints das APIs.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 9f6d3da6-374d-47f5-bc8f-b31b19cbb5ca
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 11%

---

# Pontos de acesso {#endpoints}

Os endpoints disponíveis para a API REST do Adobe Campaign:

* **/profileAndServices**: interage com campos prontos para uso. Os campos estendidos não podem ser acessados com este endpoint.
* **/profileAndServicesExt**: interage com campos personalizados adicionados durante a extensão de recurso personalizado Perfil ou Serviços. Para obter mais informações sobre recursos personalizados, consulte [esta seção](../../api/using/custom-resources.md).
* **/&lt;transactionalAPI>**: interagir com a API de mensagens transacionais (o nome do ponto de extremidade da API de mensagens transacionais depende da configuração da instância). Para obter mais informações, consulte [esta seção](../../api/using/managing-transactional-messages.md).
* **/workflow/execution**: interagir com fluxos de trabalho. Para obter mais informações, consulte [esta seção](../../api/using/controlling-a-workflow.md).
* **/privacy/privacyTool**: interaja com a API de privacidade para permitir o processo automático de solicitações de privacidade. Para obter mais informações, consulte [esta seção](../../api/using/creating-a-privacy-request.md).
* **/history**: recuperar o histórico de marketing dos perfis. Para obter mais informações sobre perfis de clientes integrados no Campaign, consulte a [documentação do Campaign](https://helpx.adobe.com/campaign/standard/audiences/using/integrated-customer-profile.html).

Por padrão, os principais recursos disponíveis para as APIs **profileAndServices** e **profileAndServicesExt** são:

* **/profile**: interagir com perfis do banco de dados do Campaign. Para adicionar perfis a um serviço, use o ponto de extremidade **/serviço**. Para obter mais informações sobre perfis no Campaign, consulte a [documentação do Campaign](https://helpx.adobe.com/campaign/standard/audiences/using/about-profiles.html).
* **/serviço**: gerenciar serviços de assinatura. Para obter mais informações sobre os serviços no Campaign, consulte a [documentação do Campaign](https://helpx.adobe.com/campaign/standard/audiences/using/creating-a-service.html).

>[!NOTE]
>
>Todos os outros recursos estendidos ou criados estão disponíveis somente por meio da API **ProfileAndServicesExt**. Eles devem estar vinculados ao recurso **Perfil** para serem acessíveis.
