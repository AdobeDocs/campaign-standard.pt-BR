---
solution: Campaign Standard
product: campaign
title: Testar os acionadores
description: null
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '443'
ht-degree: 2%

---


# Testar os acionadores{#testing-your-triggers}

As seguintes dicas de solução de problemas ajudarão você a resolver os problemas mais comuns que você pode encontrar ao usar Acionadores com o Adobe Campaign:

**A funcionalidade está ativada?**

Para verificar se a integração Acionadores - Campanha está ativada, clique no logotipo Adobe Campaign, no canto superior esquerdo, em seguida selecione **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]**. Você deve ver o item **[!UICONTROL Experience Cloud Triggers]**.

Se você vir, vá para a próxima etapa.

Caso contrário, entre em contato com o executivo da conta do Adobe ou com o parceiro de serviços profissionais. Consulte [Ativando a funcionalidade](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality).

**Tente criar um acionador**

Siga as etapas descritas em [Criar um acionador mapeado na Campanha](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) para criar um acionador.

Se o acionador for criado, vá para a próxima etapa. Caso contrário, isso significa que a conexão do ponto final do acionador falhou. Verifique se os Acionadores foram provisionados no Experience Cloud (serviços de Ativação). Caso contrário, entre em contato com o executivo da sua conta Adobe ou com o parceiro de serviços profissionais. As seguintes informações são obrigatórias:

* Nome da Empresa do Marketing Cloud
* IMS Organization ID
* Empresa de logon do Analytics (pode ser igual ao Nome da Empresa do Marketing Cloud)

**Tente publicar o acionador**

Siga as etapas descritas em [Criar um acionador mapeado na Campanha](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) para publicar o acionador.

Se a publicação tiver êxito, siga para a próxima etapa. Caso contrário, entre em contato com a Adobe para reiniciar sua instância e tente novamente.

**Gerar o acionador do site**

Siga as etapas descritas em [Editar o template de mensagem transacional](../../integrating/using/using-triggers-in-campaign.md#editing-the-transactional-message-template) para editar e publicar o modelo transacional. Em seguida, teste a geração do acionador a partir do site.

Se o acionador for recebido pelo Analytics, vá para a próxima etapa. Caso contrário, verifique os seguintes itens:

* O acionador está habilitado para o Analytics
* O site usado pela MCID e pelo Analytics está habilitado no DTM
* O conjunto de relatórios correto do Analytics é usado ao criar acionadores

**O gatilho é recebido pela Campanha?**

Caso contrário, verifique se o acionador foi recebido do pipeline.

Caso contrário, entre em contato com a Adobe para verificar a configuração dos pontos finais do pipeline.

Em caso afirmativo, siga estas orientações:

* Verifique o tipo de ID de reconciliação na fonte de dados de Campanha.
* A Fonte de Dados CustomerId é criada por meio dos Atributos do cliente.
* Verifique a ID da fonte de dados.
* Peça à Adobe para reiniciar a instância da Campanha após a configuração da Fonte de Dados.
* Verifique os problemas de análise do acionador no relatório do acionador.

**O acionador está no status pendente?**

Caso contrário, vá para a próxima etapa. Em caso afirmativo, siga estas orientações:

* Verifique se o modelo transacional foi publicado.
* Verifique se o perfil não está em lista de bloqueios.
* Verifique a aplicação do regra de tipologia.
* Verifique os registros do mensagen transacional.

**A mensagem é válida?**

Se a mensagem não for válida, verifique os seguintes itens:

* Para campos de personalização de enriquecimento de disparo marcados como inválidos, valide o modelo transacional das coleções eventCusResource associadas.
* Validar o formato de mensagem

