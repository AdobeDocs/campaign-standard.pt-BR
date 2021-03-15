---
solution: Campaign Standard
product: campaign
title: Testar os acionadores
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
feature: Triggers
role: Arquiteto de dados
level: Intermediário
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 2%

---


# Testar os acionadores{#testing-your-triggers}

As seguintes dicas de solução de problemas ajudarão você a resolver os problemas mais comuns que poderá encontrar ao usar Triggers com o Adobe Campaign:

**A funcionalidade está ativada?**

Para verificar se a integração Triggers - Campaign está ativada, clique no logotipo do Adobe Campaign, no canto superior esquerdo, em seguida, selecione **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]**. Você deve ver o item **[!UICONTROL Experience Cloud Triggers]**.

Se vir, vá para a próxima etapa.

Caso contrário, entre em contato com o executivo da sua conta Adobe ou com o parceiro de serviços profissionais. Consulte [Ativando a funcionalidade](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality).

**Tente criar um acionador**

Siga as etapas descritas em [Criação de um acionador mapeado no Campaign](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) para criar um acionador.

Se o acionador for criado, vá para a próxima etapa. Caso contrário, significa que a conexão do ponto final do acionador falhou. Verifique se os Acionadores foram provisionados no Experience Cloud (Serviços de ativação). Caso contrário, entre em contato com o executivo da sua conta Adobe ou com o parceiro de serviços profissionais. As seguintes informações são obrigatórias:

* Nome da empresa do Marketing Cloud
* IMS Organization ID
* Empresa de logon do Analytics (pode ser igual ao Nome da empresa do Marketing Cloud)

**Tente publicar o acionador**

Siga as etapas descritas em [Criação de um acionador mapeado no Campaign](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) para publicar o acionador.

Se a publicação tiver êxito, vá para a próxima etapa. Caso contrário, entre em contato com o Adobe para reiniciar sua instância e tente novamente.

**Gerar o acionador a partir do site**

Siga as etapas descritas em [Editing the transactional message template](../../integrating/using/using-triggers-in-campaign.md#editing-the-transactional-message-template) para editar e publicar o template transacional. Em seguida, teste a geração do acionador a partir do site.

Se o acionador for recebido pelo Analytics, vá para a próxima etapa. Caso contrário, verifique os seguintes itens:

* O Acionador está ativado para o Analytics
* O site usado pela MCID e pelo Analytics está habilitado no DTM
* O conjunto de relatórios correto do Analytics é usado ao criar acionadores

**O acionador é recebido pelo Campaign?**

Caso contrário, verifique se o acionador foi recebido do pipeline.

Caso contrário, entre em contato com o Adobe para verificar a configuração dos pontos finais do pipeline.

Em caso afirmativo, siga estas diretrizes:

* Verifique o tipo de ID de reconciliação na fonte de dados do Campaign.
* A fonte de dados CustomerId é criada por meio dos atributos do cliente.
* Verifique a ID da fonte de dados.
* Peça ao Adobe para reiniciar a instância do Campaign após a configuração da fonte de dados.
* Verifique os problemas de análise do acionador no relatório do acionador.

**O acionador está com status pendente?**

Caso contrário, vá para a próxima etapa. Em caso afirmativo, siga estas diretrizes:

* Verifique se o template transacional está publicado.
* Verifique se o perfil não está em lista de bloqueios.
* Verifique a aplicação das regras de tipologia.
* Verifique os logs da mensagem transacional.

**A mensagem é válida?**

Se a mensagem não for válida, verifique os seguintes itens:

* Para acionar campos de personalização de enriquecimento marcados como inválidos, valide o modelo transacional das coleções eventCusResource associadas.
* Validar o formato da mensagem

