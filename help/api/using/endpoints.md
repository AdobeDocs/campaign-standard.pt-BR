---
title: Pontos finais
description: Saiba mais sobre os pontos finais das APIs.
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f251e4b5187aa09f65a5d8d6215f208a09cd9159

---


# Pontos finais {#endpoints}

Os pontos de extremidade disponíveis para a API REST do Adobe Campaign:

* **/profileAndServices**: interagir com campos fora da caixa. Os campos estendidos não estão acessíveis com este endpoint.
* **/profileAndServicesExt**: interagir com campos personalizados adicionados durante a extensão de recurso personalizado Perfil ou Serviços. For more on custom resources, refer to [this section](../../api/using/custom-resources.md).
* **/&lt;transactionalAPI&gt;**: interaja com a API de mensagens transacionais (o nome do terminal da API de mensagens transacionais depende da configuração da instância). Para obter mais informações, consulte [esta seção](../../api/using/managing-transactional-messages.md).
* **/workflow/execução**: interagir com fluxos de trabalho. Para obter mais informações, consulte [esta seção](../../api/using/controlling-a-workflow.md).
* **/privacy/privacyFerramenta**: interaja com a API de privacidade para permitir o processo automático de solicitações de privacidade. Para obter mais informações, consulte [esta seção](../../api/using/creating-a-privacy-request.md).
* **/histórico**: recupere o histórico de marketing dos perfis. Para obter mais informações sobre perfis de clientes integrados no Campaign, consulte a documentação [da](https://helpx.adobe.com/campaign/standard/audiences/using/integrated-customer-profile.html)Campanha.

Por padrão, os principais recursos disponíveis para as APIs **profileAndServices** e **profileAndServicesExt** são:

* **/perfil**: interaja com perfis do banco de dados do Campaign. Para adicionar perfis a um serviço, use o terminal **/serviço** . Para obter mais informações sobre perfis no Campaign, consulte a documentação [da](https://helpx.adobe.com/campaign/standard/audiences/using/about-profiles.html)Campanha.
* **/serviço**: gerenciar serviços de assinatura. Para obter mais informações sobre serviços no Campaign, consulte a documentação [da](https://helpx.adobe.com/campaign/standard/audiences/using/creating-a-service.html)Campanha.

>[!NOTE]
>
>Todos os outros recursos que foram estendidos ou criados estão disponíveis somente por meio da API **ProfileAndServicesExt** . Eles devem estar vinculados ao recurso **Perfil** para serem acessíveis.
