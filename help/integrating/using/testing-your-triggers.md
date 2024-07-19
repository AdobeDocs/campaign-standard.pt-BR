---
title: Testar acionadores
description: Obtenha dicas de solução de problemas para ajudar a resolver os problemas mais comuns que você pode encontrar ao usar Triggers com o Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 66628f2a-6ed3-4b12-b2ed-9b9eec440dc3
source-git-commit: 602878233e919d01f3972167cb6d3a1acc4cfc02
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 1%

---

# Testar acionadores{#testing-your-triggers}

As seguintes dicas de solução de problemas ajudam a resolver os problemas mais comuns que você pode encontrar ao usar Acionadores com o Adobe Campaign:

**A funcionalidade está ativada?**

Para verificar se a integração Triggers - Campaign está ativada, clique no logotipo do Adobe Campaign, no canto superior esquerdo, em seguida, selecione **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]**. Você deve ver o item **[!UICONTROL Experience Cloud Triggers]**.

Se você o vir, siga para a próxima etapa.

Caso contrário, entre em contato com seu executivo de conta da Adobe ou com um parceiro de serviços profissionais. Consulte [Ativando a funcionalidade](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality).

**Tente criar um gatilho**

Siga as etapas descritas em [Criação de um acionador mapeado no Campaign](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) para criar um acionador.

Se o acionador for criado, avance para a próxima etapa. Caso contrário, significa que a conexão do ponto final do acionador falhou. Verifique se Triggers está provisionado em Experience Cloud (Serviços de ativação). Se não estiver, entre em contato com seu executivo de conta da Adobe ou com um parceiro de serviços profissionais. As seguintes informações são obrigatórias:

* Nome da empresa do Marketing Cloud
* ID da organização
* Empresa de logon do Analytics (pode ser o mesmo que o Nome da empresa do Marketing Cloud)

**Tente publicar o acionador**

Siga as etapas descritas em [Criar um acionador mapeado no Campaign](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) para publicar o acionador.

Se a publicação for bem-sucedida, avance para a próxima etapa. Caso contrário, entre em contato com o Adobe para reiniciar sua instância e tente novamente.

**Gerar o acionador a partir do site**

Siga as etapas descritas em [Editar o modelo de mensagem transacional](../../integrating/using/using-triggers-in-campaign.md#editing-the-transactional-message-template) para editar e publicar o modelo transacional. Em seguida, teste a geração do acionador no site.

Se o acionador for recebido pelo Analytics, siga para a próxima etapa. Caso contrário, verifique os seguintes itens:

* O acionador está ativado para o Analytics
* O site usado pela MCID e pelo Analytics está habilitado no DTM
* O conjunto de relatórios correto do Analytics é usado ao criar acionadores

**O acionador foi recebido pelo Campaign?**

Caso contrário, verifique se o acionador foi recebido do pipeline.

Caso contrário, entre em contato com o Adobe para verificar a configuração dos pontos de extremidade do pipeline.

Se estiver, siga estas diretrizes:

* Verifique o tipo de ID de reconciliação na fonte de dados do Campaign.
* A fonte de dados da ID do cliente é criada por meio dos atributos do cliente.
* Verifique a ID da fonte de dados.
* Peça ao Adobe para reiniciar a instância do Campaign após a configuração da fonte de dados.
* Verifique os problemas de análise do acionador no relatório de acionador.

**O gatilho está com status pendente?**

Caso contrário, siga para a próxima etapa. Se estiver, siga estas diretrizes:

* Verifique se o template transacional foi publicado.
* Verifique se o perfil não está no incluo na lista de bloqueios.
* Verifique a aplicação das regras de tipologia.
* Verifique os logs da mensagem transacional.

**A mensagem é válida?**

Se a mensagem não for válida, verifique os seguintes itens:

* Para campos de personalização de enriquecimento do acionador marcados como inválidos, valide o modelo transacional das coleções eventCusResource associadas.
* Validar o formato da mensagem
