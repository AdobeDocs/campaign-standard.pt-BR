---
title: Workflows do aplicativo de integração
description: Workflows de integração do Campaign e do Dynamics
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Integração do Microsoft CRM
role: Arquiteto de dados
level: Intermediário
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '651'
ht-degree: 1%

---


# Campaign - Fluxos de trabalho de integração do Microsoft Dynamics 365

A página **[!UICONTROL Workflows]** lista os workflows técnicos e seu status.

O aplicativo de integração vem com três workflows:

![](assets/do-not-localize/d365-to-acs-ui-page-workflows.png)

**Microsoft Dynamics 365 para Campaign**
* Enviar *contatos* do Microsoft Dynamics 365 para o Adobe Campaign
* *Entidades* personalizadas: Traga tabelas personalizadas do Microsoft Dynamics 365 para o Adobe Campaign. [Saiba mais](../../integrating/using/d365-acs-using-the-integration.md#data-flows)
* Isso também é conhecido como **Ingress** (referindo-se à entrada de dados do Microsoft Dynamics 365 para Adobe Campaign)

**Campanha para o Microsoft Dynamics 365**
* Os eventos de marketing por email do Adobe Campaign Standard são enviados para o Dynamics 365 (envio de email, abrir, clicar, rejeição). [Saiba mais](../../integrating/using/d365-acs-using-the-integration.md#email-marketing-event-flow)
* Isso também é conhecido como **Egress** (referindo-se à saída de dados do Adobe Campaign para o Microsoft Dynamics 365)

**Aceitar/Rejeitar**

Os status de rejeição (por exemplo, lista de bloqueios) podem ser sincronizados do Microsoft Dynamics 365 para Adobe Campaign ou do Adobe Campaign para o Microsoft Dynamics 365. Os dados também podem ser sincronizados bidirecionalmente (ou seja, fluxos de dados em ambas as direções). [Saiba mais](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf).

>[!IMPORTANT]
>
>É altamente recomendável interromper o fluxo de trabalho do **Microsoft Dynamics 365 para Campaign** antes de publicar as alterações no Adobe Campaign Standard ou no Microsoft Dynamics 365. Essas alterações incluem atualizações nos recursos/entidades (e seus campos associados), links, colunas de identificador etc.. que estão em uso na integração. Se isso não for feito, os dados serão perdidos e/ou o workflow será interrompido inesperadamente.

## Backlog do workflow

Esse aplicativo de integração primeiro lê os dados e, em seguida, grava os dados no destino. A coluna **[!UICONTROL Backlog]** indica o número de registros que foram enfileirados e que estão aguardando para serem gravados. Espera-se que esse valor cresça quando você tem uma grande quantidade de dados para processar (por exemplo, você está executando a integração pela primeira vez, está reproduzindo os dados etc.).

>[!NOTE]
>Se os registros do Microsoft Dynamics 365 e/ou Campaign não estiverem sendo atualizados, verifique primeiro se há um grande número de registros aguardando para serem gravados no destino.


## Status do workflow {#workflow-status}

A coluna **[!UICONTROL Status]** indica o estado dos processos em segundo plano associados ao fluxo de trabalho. Os valores possíveis são:

* **EM EXECUÇÃO**: O processo está em execução no momento e seus dados devem ser sincronizados.
* **INTERROMPIDO**: O processo não está em execução no momento, portanto, você não deve esperar que seus dados sejam sincronizados.
* **INICIANDO**: Você solicitou que o workflow iniciasse. O aplicativo ainda não começou a sincronizar os dados associados a esse workflow, mas você pode esperar que isso ocorra após alguns minutos (quando ele mostrará o status de **RUNNING**)
* **FALHA**: Os processos de workflow estavam em execução, mas encontraram erros e não puderam se recuperar deles.

## Ações disponíveis

As ações possíveis estão listadas abaixo.

* **Editar**: Clicar no ícone de lápis o enviará para outra página que permitirá fazer atualizações no fluxo de trabalho. Lembre-se de que as alterações feitas NÃO entrarão em vigor até que você pare o fluxo de trabalho e reinicie-o.

* **Início**: Um botão Start solicita que um workflow interrompido seja iniciado. Esse botão só aparecerá quando os processos associados ao workflow forem interrompidos no momento. Os processos primeiro serão alterados para &quot;INICIANDO&quot; e depois para &quot;EXECUTANDO&quot;. Os dados associados ao workflow não iniciarão a sincronização até que o workflow esteja em um estado &quot;EM EXECUÇÃO&quot;.

   O botão Iniciar é um botão de alternância. Se os processos de workflow já tiverem sido iniciados, o botão será alterado para um botão **Stop**.

* **Parar**: Um  **** botão Parar solicita que um fluxo de trabalho em execução seja interrompido. Esse botão só aparecerá quando os processos associados ao workflow estiverem em execução no momento.

Ao editar um workflow, suas atualizações NÃO são incorporadas imediatamente às regras dos processos em execução, até que você pare o workflow e clique no botão **Start**. Em seguida, suas atualizações são incorporadas nos processos em execução (uma vez que o processo retorna a um estado **RUNNING**).

Uma indicação de aviso é adicionada ao botão **Stop** para avisá-lo quando você (a) fez atualizações no workflow, mas (b) não fez um Stop/Start desse workflow.

![](assets/do-not-localize/d365-to-acs-icon-stop-with-changes.png)
