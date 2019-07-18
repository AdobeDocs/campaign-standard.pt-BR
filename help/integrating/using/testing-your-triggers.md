---
title: Teste de acionadores
seo-title: Teste de acionadores
description: Teste de acionadores
seo-description: null
page-status-flag: nunca ativado
uuid: b 3 a 6667 d-e 843-4 ad 6-817 e-d 91542 b 5 f 2 e 2
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
discoiquuid: f 67 e 69 f 2-09 fb -4 f 33-b 2 c 3-c 67 a 060743 e 3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 698466596fdacd005dc4d72b8071208c8c39f77d

---


# Testing your triggers{#testing-your-triggers}

As seguintes dicas de solução de problemas ajudarão você a resolver os problemas mais comuns que podem ser encontrados ao usar Acionadores com o Adobe Campaign:

**A funcionalidade é ativada?**

To check if the Triggers - Campaign integration is activated, click the Adobe Campaign logo, in the top left corner, then select **[!UICONTROL Marketing plans]** &gt; **[!UICONTROL Transactional messages]**. You should see the **[!UICONTROL Experience Cloud Triggers]** item.

Se você o vir, passe para a próxima etapa.

Caso contrário, entre em contato com seu parceiro de serviços profissionais ou de serviços profissionais da Adobe. See [Activating the functionality](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality).

**Tente criar um acionador**

Follow the steps described in [Creating a mapped trigger in Campaign](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) to create a trigger.

Se o acionador for criado, prossiga para a próxima etapa. Caso contrário, a conexão de ponto final do acionador falhará. Verifique se Acionadores são provisionados na Experience Cloud (serviços de ativação). Caso contrário, entre em contato com seu parceiro de serviços profissionais ou de serviços profissionais da Adobe. As seguintes informações são necessárias:

* Nome da empresa da Marketing Cloud
* ID ORG IMS
* Empresa de logon do Analytics (pode ser o mesmo que o Nome da empresa da Marketing Cloud)

**Tente publicar o acionador**

Follow the steps described in [Creating a mapped trigger in Campaign](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) to publish the trigger.

Se a publicação tiver êxito, prossiga para a próxima etapa. Caso contrário, entre em contato com a Adobe para reiniciar sua instância e tentar novamente.

**Gerar o acionador do site**

Follow the steps described in [Editing the transactional message template](../../integrating/using/using-triggers-in-campaign.md#editing-the-transactional-message-template) to edit and publish the transactional template. Em seguida, teste a geração do acionador no site.

Se o acionador for recebido pelo Analytics, prossiga para a próxima etapa. Se não, verifique os seguintes itens:

* O acionador está ativado para o Analytics
* O site usado MCID e o Analytics estão ativados no DTM
* O conjunto de relatórios correto do Analytics é usado ao criar acionadores

**O acionador é recebido por Campanha?**

Caso contrário, verifique se o acionador é recebido do pipeline.

Caso contrário, entre em contato com a Adobe para verificar a configuração dos pontos finais do pipeline.

Se for, siga estas linhas de guia:

* Verifique o tipo de ID de reconciliação na fonte de dados da campanha.
* A Fonte de dados customerid é criada por meio dos Atributos do cliente.
* Verifique a ID da fonte de dados.
* Solicite que a Adobe reinicie a instância Campanha após a configuração da Fonte de dados.
* Verifique os problemas de análise de acionamento no relatório de disparo.

**O acionador é o status pendente?**

Caso contrário, prossiga para a próxima etapa. Se for, siga estas linhas de guia:

* Verifique se o modelo transacional foi publicado.
* Se o limite propensão estiver ativado para Campanha, verifique a pontuação de propensão do acionador do pipeline.
* Verifique se o perfil não está na lista negra.
* Verifique a aplicação das regras de tipologia.
* Verifique os logs da mensagem transacional.

**A mensagem é válida?**

Se a mensagem não for válida, verifique os seguintes itens:

* Para acionar os campos de personalização de enriquecimento marcados como inválidos, valide o modelo transacional das coleções eventcusresource associadas.
* Validar o formato da mensagem

