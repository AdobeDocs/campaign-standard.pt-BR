---
title: Workflows do aplicativo de integração
description: Workflows de integração de campanha e dinâmica
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
translation-type: tm+mt
source-git-commit: efa30d7ed4a0caf929da6f485681078318849cda
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 1%

---


# Campanha - workflows de integração do Microsoft Dynamics 365

A página **[!UICONTROL Workflows]** lista os workflows técnicos e seu status.

O aplicativo de integração tem três workflows:

![](assets/do-not-localize/d365-to-acs-ui-page-workflows.png)

**Microsoft Dynamics 365 para Campanha**
* Envie *contatos* do Microsoft Dynamics 365 para o Adobe Campaign
* *Entidades* personalizadas: Inclua tabelas personalizadas do Microsoft Dynamics 365 no Adobe Campaign. [Saiba mais](../../integrating/using/d365-acs-using-the-integration.md#data-flows)
* Isso também é conhecido como **Ingress** (referindo-se à entrada de dados do Microsoft Dynamics 365 para Adobe Campaign)

**Campanha ao Microsoft Dynamics 365**
* Os eventos de marketing de email da Adobe Campaign Standard são enviados para o Dynamics 365 (envio de email, abrir, clicar, saltar). [Saiba mais](../../integrating/using/d365-acs-using-the-integration.md#email-marketing-event-flow)
* Isso também é conhecido como **Egress** (referindo-se à saída de dados da Adobe Campaign para o Microsoft Dynamics 365)

**Entrada/saída**

Os status de recusa (por exemplo, lista de bloqueios) podem ser sincronizados do Microsoft Dynamics 365 para o Adobe Campaign ou do Adobe Campaign para o Microsoft Dynamics 365. Os dados também podem ser sincronizados bidirecionalmente (ou seja, fluxos de dados em ambas as direções). [Saiba mais](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf).

>[!IMPORTANT]
>
>É altamente recomendável parar o fluxo de trabalho do **Microsoft Dynamics 365 para Campaign** antes de publicar as alterações no Adobe Campaign Standard ou no Microsoft Dynamics 365. Essas alterações incluem atualizações de recursos/entidades (e seus campos associados), links, colunas de identificador, etc... que estão sendo usadas atualmente pela integração. Se isso não for feito, os dados serão perdidos e/ou o fluxo de trabalho será interrompido inesperadamente.

## Backlog do fluxo de trabalho

Esse aplicativo de integração primeiro lê os dados e, em seguida, grava os dados no destino. A coluna **[!UICONTROL Backlog]** indica o número de registros que foram enfileirados e que estão aguardando para serem gravados. Espera-se que esse valor cresça quando você tem uma grande quantidade de dados para processar (por exemplo, você está executando a integração pela primeira vez, está reproduzindo os dados etc.).

>[!NOTE]
>Se seus registros do Microsoft Dynamics 365 e/ou Campanha não estiverem sendo atualizados, verifique se há um grande número de registros aguardando para serem gravados no destino.


## Status do fluxo de trabalho {#workflow-status}

A coluna **[!UICONTROL Status]** indica o estado dos processos em segundo plano associados ao fluxo de trabalho. Os valores possíveis são:

* **EM EXECUÇÃO**: O processo está em execução no momento e seus dados devem ser sincronizados.
* **PARADO**: O processo não está em execução no momento, portanto, você não deve esperar que seus dados sejam sincronizados.
* **COMEÇANDO**: Você solicitou que o fluxo de trabalho seja processado para start. O aplicativo ainda não começou a sincronizar os dados associados a esse fluxo de trabalho, mas você pode esperar que isso ocorra após alguns minutos (quando ele mostrará o status de **EXECUÇÃO**)
* **FALHA**: Os processos de fluxo de trabalho estavam em execução, mas encontraram erros e não puderam se recuperar deles.

## Ações disponíveis

As ações possíveis estão listadas abaixo.

* **Editar**: Clicar no ícone de lápis o enviará para outra página que permitirá fazer atualizações no fluxo de trabalho. Lembre-se de que as alterações feitas NÃO entrarão em vigor até que você pare o fluxo de trabalho e reinicie-o.

* **Start**: Um botão Start solicita que um fluxo de trabalho interrompido seja iniciado. Este botão só aparecerá quando os processos associados ao fluxo de trabalho forem interrompidos. Os processos primeiro mudarão para &quot;INICIANDO&quot; e depois para &quot;EXECUTANDO&quot;. Os dados associados ao fluxo de trabalho não serão sincronizados até que o fluxo de trabalho esteja em um estado &quot;EXECUTANDO&quot;.

   O botão start é uma alternância. Se os processos de fluxo de trabalho já tiverem sido iniciados, o botão será alterado para um botão **Parar**.

* **Parar**: Um  **** botão Parar solicita que um fluxo de trabalho em execução seja interrompido. Este botão só aparecerá quando os processos associados ao fluxo de trabalho estiverem em execução.

Quando você edita um fluxo de trabalho, suas atualizações NÃO são incorporadas imediatamente às regras dos processos em execução, até que você pare o fluxo de trabalho e clique no botão **Start**. Em seguida, suas atualizações são incorporadas aos processos em execução (uma vez que o processo retorna a um estado **RUNNING**).

Uma indicação de aviso é adicionada ao botão **Parar** para informá-lo quando você (a) fez atualizações no fluxo de trabalho, mas (b) não fez uma Parada/Start desse fluxo de trabalho.

![](assets/do-not-localize/d365-to-acs-icon-stop-with-changes.png)
