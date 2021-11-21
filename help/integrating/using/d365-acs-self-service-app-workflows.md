---
title: Workflows do aplicativo de integração
description: Workflows de integração do Campaign e do Dynamics
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
exl-id: 51f07f08-5d57-4c4c-aff2-d03e5956ec6f
source-git-commit: e7fdaa4b1d77afdae8004a88bbe41bbbe75a3f3c
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 1%

---

# Campaign - Fluxos de trabalho de integração do Microsoft Dynamics 365

O **[!UICONTROL Workflows]** lista os workflows técnicos e seu status.

O aplicativo de integração vem com três workflows:

![](assets/do-not-localize/d365-to-acs-ui-page-workflows.png)

**Microsoft Dynamics 365 para Campaign**
* Enviar *contatos* do Microsoft Dynamics 365 no Adobe Campaign
* *Entidades personalizadas*: Traga tabelas personalizadas do Microsoft Dynamics 365 para o Adobe Campaign. [Saiba mais](../../integrating/using/d365-acs-using-the-integration.md#data-flows)
* Isso também é conhecido como **Incursão** (referência à entrada de dados do Microsoft Dynamics 365 para Adobe Campaign)

**Campanha para Microsoft Dynamics 365**
* Os eventos de marketing por email do Adobe Campaign Standard são enviados para o Dynamics 365 (envio de email, abrir, clicar, rejeição). [Saiba mais](../../integrating/using/d365-acs-using-the-integration.md#email-marketing-event-flow)
* Isso também é conhecido como **Egresso** (referindo-se à saída de dados do Adobe Campaign para o Microsoft Dynamics 365)

**Aceitar/Rejeitar**

Os status de rejeição (por exemplo, lista de bloqueios) podem ser sincronizados do Microsoft Dynamics 365 para o Adobe Campaign ou do Adobe Campaign para o Microsoft Dynamics 365. Os dados também podem ser sincronizados bidirecionalmente (ou seja, fluxos de dados em ambas as direções). [Saiba mais](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf).

>[!IMPORTANT]
>
>É altamente recomendável interromper a **Microsoft Dynamics 365 para Campaign** fluxo de trabalho antes de publicar as alterações no Adobe Campaign Standard ou no Microsoft Dynamics 365. Essas alterações incluem atualizações nos recursos/entidades (e seus campos associados), links, colunas de identificador etc.. que estão em uso na integração. Se isso não for feito, os dados serão perdidos e/ou o workflow será interrompido inesperadamente.

## Backlog do workflow

Esse aplicativo de integração primeiro lê os dados e, em seguida, grava os dados no destino. O **[!UICONTROL Backlog]** indica o número de registros que foram enfileirados e estão aguardando gravação. Espera-se que esse valor cresça quando você tem uma grande quantidade de dados para processar (por exemplo, você está executando a integração pela primeira vez, está reproduzindo os dados etc.).

>[!NOTE]
>Se os registros do Microsoft Dynamics 365 e/ou Campaign não estiverem sendo atualizados, verifique primeiro se há um grande número de registros aguardando para serem gravados no destino.

## Status do workflow {#workflow-status}

O **[!UICONTROL Status]** indica o estado dos processos em segundo plano associados ao fluxo de trabalho. Os valores possíveis são:

* **EM EXECUÇÃO**: O processo está em execução no momento e seus dados devem ser sincronizados.
* **PARADO**: O processo não está em execução no momento, portanto, você não deve esperar que seus dados sejam sincronizados.
* **INÍCIO**: Você solicitou que o workflow iniciasse. O aplicativo ainda não começou a sincronizar os dados associados a esse fluxo de trabalho, mas você pode esperar que isso aconteça após alguns minutos (quando ele mostrará o status de **EM EXECUÇÃO**)
* **FALHA**: Os processos de workflow estavam em execução, mas encontraram erros e não puderam se recuperar deles.

## Ações disponíveis

As ações possíveis estão listadas abaixo.

* **Editar**: Clicar no ícone de lápis o enviará para outra página que permitirá fazer atualizações no fluxo de trabalho. Lembre-se de que as alterações feitas NÃO entrarão em vigor até que você pare o fluxo de trabalho e reinicie-o.

* **Iniciar**: Um botão Start solicita que um workflow interrompido seja iniciado. Esse botão só aparecerá quando os processos associados ao workflow forem interrompidos no momento. Os processos primeiro serão alterados para &quot;INICIANDO&quot; e depois para &quot;EXECUTANDO&quot;. Os dados associados ao workflow não iniciarão a sincronização até que o workflow esteja em um estado &quot;EM EXECUÇÃO&quot;.

   O botão Iniciar é um botão de alternância. Se os processos de workflow já tiverem sido iniciados, o botão será alterado para um **Stop** botão.

* **Stop**: A **Stop** solicita que um fluxo de trabalho em execução seja interrompido. Esse botão só aparecerá quando os processos associados ao workflow estiverem em execução no momento.

Ao editar um fluxo de trabalho, suas atualizações NÃO são incorporadas imediatamente às regras dos processos em execução, até que você pare o fluxo de trabalho e clique no botão **Iniciar** botão. Em seguida, suas atualizações são incorporadas aos processos em execução (uma vez que o processo retorne a um **EM EXECUÇÃO** estado).

É aditada uma indicação de aviso ao **Stop** botão para informá-lo quando você (a) fez atualizações no fluxo de trabalho, mas (b) não fez um Stop/Start desse fluxo de trabalho.

![](assets/do-not-localize/d365-to-acs-icon-stop-with-changes.png)
