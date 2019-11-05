---
title: Testar os acionadores
description: null
page-status-flag: nunca ativado
uuid: b3a6667d-e843-4ad6-817e-d91542b5f2e2
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: integrando
content-type: referência
topic-tags: trabalhar com campanha e acionadores
discoiquuid: f67e69f2-09fb-4f33-b2c3-c67a060743e3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Testar os acionadores{#testing-your-triggers}

As seguintes dicas de solução de problemas ajudarão a resolver os problemas mais comuns que você pode encontrar ao usar Acionadores com o Adobe Campaign:

**A funcionalidade está ativada?**

Para verificar se a integração Acionadores - Campanha está ativada, clique no logotipo do Adobe Campaign, no canto superior esquerdo, em seguida selecione **[!UICONTROL Marketing plans]** &gt; **[!UICONTROL Transactional messages]**. Você deveria ver o **[!UICONTROL Experience Cloud Triggers]** item.

Se você vir, vá para a próxima etapa.

Caso contrário, entre em contato com o executivo de sua conta da Adobe ou com o parceiro de serviços profissionais. Consulte [Ativando a funcionalidade](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality).

**Tente criar um acionador**

Siga as etapas descritas em [Criar um acionador mapeado no Campaign](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) para criar um acionador.

Se o acionador for criado, vá para a próxima etapa. Caso contrário, isso significa que a conexão do ponto final do acionador falhou. Verifique se os Acionadores foram provisionados na Experience Cloud (Serviços de ativação). Caso contrário, entre em contato com seu parceiro de serviços profissional ou executivo de conta da Adobe. As seguintes informações são obrigatórias:

* Nome da empresa da Marketing Cloud
* ID ORG IMS
* Empresa de logon do Analytics (pode ser igual ao nome da empresa da Marketing Cloud)

**Tente publicar o acionador**

Siga as etapas descritas em [Criar um acionador mapeado no Campaign](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) para publicar o acionador.

Se a publicação tiver êxito, siga para a próxima etapa. Caso contrário, entre em contato com a Adobe para reiniciar sua instância e tente novamente.

**Gerar o acionador do site**

Siga as etapas descritas em [Edição do modelo](../../integrating/using/using-triggers-in-campaign.md#editing-the-transactional-message-template) de mensagem transacional para editar e publicar o modelo transacional. Em seguida, teste a geração do acionador a partir do site.

Se o acionador for recebido pelo Analytics, vá para a próxima etapa. Caso contrário, verifique os seguintes itens:

* O acionador está habilitado para o Analytics
* O site usado pelo MCID e Analytics está habilitado no DTM
* O conjunto de relatórios correto do Analytics é usado ao criar acionadores

**O acionador é recebido pelo Campaign?**

Caso contrário, verifique se o acionador foi recebido do pipeline.

Caso contrário, entre em contato com a Adobe para verificar a configuração dos pontos finais do pipeline.

Se estiver, siga estas linhas de guia:

* Verifique o tipo de ID de reconciliação na fonte de dados Campaign.
* A Fonte de Dados CustomerId é criada por meio dos Atributos do cliente.
* Verifique a ID da fonte de dados.
* Solicite à Adobe que reinicie a instância Campaign após a configuração da Fonte de dados.
* Verifique os problemas de análise do acionador no relatório do acionador.

**O acionador está no status pendente?**

Caso contrário, vá para a próxima etapa. Se estiver, siga estas linhas de guia:

* Verifique se o modelo transacional foi publicado.
* Se o limite de propensãoScore estiver ativado para Campaign, verifique a pontuação de propensão do acionador a partir do pipeline.
* Verifique se o perfil não está na lista negra.
* Verifique a aplicação das regras de tipologia.
* Verifique os registros da mensagem transacional.

**A mensagem é válida?**

Se a mensagem não for válida, verifique os seguintes itens:

* Para acionar campos de personalização de enriquecimento marcados como inválidos, valide o modelo transacional das coleções eventCusResource associadas.
* Validar o formato de mensagem

