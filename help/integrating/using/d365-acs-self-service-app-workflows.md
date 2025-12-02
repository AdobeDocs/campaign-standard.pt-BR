---
title: Workflows do aplicativo de integração
description: Workflows de integração do Campaign e do Dynamics
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 51f07f08-5d57-4c4c-aff2-d03e5956ec6f
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 1%

---

# Workflows de integração do Campaign - Microsoft Dynamics 365

A página **[!UICONTROL Workflows]** lista os fluxos de trabalho técnicos e seus status.

O aplicativo de integração vem com três workflows:

![](assets/do-not-localize/d365-to-acs-ui-page-workflows.png)

**Microsoft Dynamics 365 para o Campaign**
* Enviar *contatos* do Microsoft Dynamics 365 para o Adobe Campaign
* *Entidades personalizadas*: traga tabelas personalizadas do Microsoft Dynamics 365 para o Adobe Campaign. [Saiba mais](../../integrating/using/d365-acs-using-the-integration.md#data-flows)
* Isso também é conhecido como **Ingresso** (referente à entrada de dados do Microsoft Dynamics 365 no Adobe Campaign)

**Campanha para o Microsoft Dynamics 365**
* Os eventos de marketing por email do Adobe Campaign Standard são enviados para o Dynamics 365 (envio de email, abertura, clique, rejeição). [Saiba mais](../../integrating/using/d365-acs-using-the-integration.md#email-marketing-event-flow)
* Isso também é conhecido como **Saída** (referente à saída de dados do Adobe Campaign para o Microsoft Dynamics 365)

**Aceitar/Recusar**

Os status de recusa (por exemplo, incluir na lista de bloqueios) podem ser sincronizados do Microsoft Dynamics 365 para o Adobe Campaign ou do Adobe Campaign para o Microsoft Dynamics 365. Os dados também podem ser sincronizados bidirecionalmente (ou seja, fluxos de dados em ambas as direções). [Saiba mais](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf).

>[!IMPORTANT]
>
>É altamente recomendável interromper o fluxo de trabalho do **Microsoft Dynamics 365 para o Campaign** antes de publicar alterações no Adobe Campaign Standard ou no Microsoft Dynamics 365. Essas alterações incluem atualizações de recursos/entidades (e seus campos associados), links, colunas de identificador etc. que estão sendo usados atualmente pela integração. Se isso não for feito, poderá ocorrer perda de dados e/ou interrupção inesperada do fluxo de trabalho.

## Backlog do fluxo de trabalho

Esse aplicativo de integração lê primeiro os dados e depois os grava no destino. A coluna **[!UICONTROL Backlog]** indica o número de registros enfileirados e que estão aguardando gravação. Espera-se que esse valor aumente quando houver uma grande quantidade de dados para processar (por exemplo, você está executando a integração pela primeira vez, está reproduzindo os dados etc.).

>[!NOTE]
>Se os registros do Microsoft Dynamics 365 e/ou Campaign não estiverem sendo atualizados, verifique primeiro se há um grande número de registros aguardando para serem gravados no destino.
>

## Status do fluxo de trabalho {#workflow-status}

A coluna **[!UICONTROL Status]** indica o estado dos processos de segundo plano associados ao fluxo de trabalho. Os valores possíveis são:

* **EM EXECUÇÃO**: o processo está em execução no momento e seus dados devem ser sincronizados.
* **PARADO**: o processo não está em execução no momento, portanto, você não deve esperar que seus dados sejam sincronizados.
* **INÍCIO**: você solicitou que os processos de fluxo de trabalho sejam iniciados. O aplicativo ainda não começou a sincronizar os dados associados a este fluxo de trabalho, mas você pode esperar que isso ocorra após alguns minutos (quando isso mostrar o status de **EM EXECUÇÃO**)
* **FALHA**: os processos de fluxo de trabalho estavam em execução, mas encontraram erro(s) e não puderam se recuperar.

## Ações disponíveis

As possíveis ações estão listadas abaixo.

* **Editar**: ao clicar no ícone de lápis, você será enviado para outra página que permitirá fazer atualizações no fluxo de trabalho. Lembre-se de que as alterações feitas NÃO entrarão em vigor até que você interrompa o fluxo de trabalho e, em seguida, reinicie-o.

* **Início**: um botão Iniciar solicita que um fluxo de trabalho interrompido seja iniciado. Esse botão só aparecerá quando os processos associados ao workflow estiverem interrompidos no momento. Os processos serão alterados primeiro para &quot;INICIANDO&quot; e depois para &quot;EM EXECUÇÃO&quot;. Os dados associados ao workflow não iniciarão a sincronização até que o workflow esteja em um estado &quot;EM EXECUÇÃO&quot;.

  O botão Iniciar é um botão de alternância. Se os processos de fluxo de trabalho já tiverem sido iniciados, o botão será alterado para um botão **Parar**.

* **Parar**: um botão **Parar** solicita que um fluxo de trabalho em execução seja interrompido. Esse botão só aparecerá quando os processos associados ao workflow estiverem em execução no momento.

Ao editar um fluxo de trabalho, suas atualizações NÃO são incorporadas imediatamente às regras dos processos em execução, até que você pare o fluxo de trabalho e clique no botão **Iniciar**. Em seguida, suas atualizações são incorporadas aos processos em execução (uma vez que o processo retorne a um estado **EM EXECUÇÃO**).

Uma indicação de aviso é adicionada ao botão **Parar** para informar quando você (a) atualizou o fluxo de trabalho, mas (b) não fez uma Parada/Início deste fluxo de trabalho.

![](assets/do-not-localize/d365-to-acs-icon-stop-with-changes.png)
