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
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
    internal-label: APIs
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 10%
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
