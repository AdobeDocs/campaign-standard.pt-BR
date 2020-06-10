---
title: Renderização de email
description: Descubra o recurso de renderização de email.
page-status-flag: never-activated
uuid: c423e237-ad39-4797-ac3a-4320894a8f99
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
discoiquuid: 2b5b13c8-2e51-4985-a161-c1d7f0fc32b4
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b43e6be265ff2d8ce357ef44672a755028e2e5af
workflow-type: tm+mt
source-wordcount: '435'
ht-degree: 15%

---


# Renderização de email{#email-rendering}

Before hitting the **[!UICONTROL Send]** button, make sure that your message will be displayed in an optimal way on a variety of web clients, web mails and devices.

Para permitir isso, o Adobe Campaign captura a renderização e a disponibiliza em um relatório dedicado. Isso permite que você pré-visualização a mensagem enviada nos diferentes contextos nos quais ela pode ser recebida.

The mobile, messaging and webmail clients available for **Email rendering** in Adobe Campaign are listed on the Litmus [website](https://litmus.com/email-testing) (click **View all email clients**).

## Verificando o relatório de renderização de email {#checking-the-email-rendering-report}

Após criar seu delivery de email e definir seu conteúdo, assim como a população alvo, siga as etapas abaixo.

1. Clique em **Audiência** para acessar a **[!UICONTROL Test profiles]** guia.

   ![](assets/email_rendering_05.png)

1. Use o editor de query para definir os perfis de teste que deseja usar, incluindo os perfis de teste que são para uso de renderização **por** email. Consulte [Sobre perfis](../../audiences/using/managing-test-profiles.md)de teste.

   ![](assets/email_rendering_06.png)

1. Verifique e confirme o query e salve as alterações.
1. Clique no **[!UICONTROL Test]** botão na barra de ações.

   ![](assets/email_rendering_07.png)

1. Selecione a **[!UICONTROL Email rendering]** opção e clique em **[!UICONTROL OK]**.

   ![](assets/email_rendering_08.png)

   >[!NOTE]
   >
   >A **[!UICONTROL Proof + Email rendering]** opção permite enviar uma prova e usar o recurso de renderização de email simultaneamente. Você pode ter sua mensagem aprovada pelos recipient de prova e, ao mesmo tempo, pode testar a forma como ela será recebida, dependendo das caixas de entrada direcionadas. Nesse caso, também é necessário selecionar perfis de teste de Prova. Consulte [Sobre perfis](../../audiences/using/managing-test-profiles.md)de teste.

   O delivery de teste é enviado.

1. As miniaturas de renderização estão disponíveis alguns minutos após o envio das mensagens. Para acessá-los, selecione **[!UICONTROL Proofs]** na lista suspensa **[!UICONTROL Summary]** .

   ![](assets/email_rendering_03.png)

1. Na **[!UICONTROL Proofs]** lista, clique no **[!UICONTROL Access email rendering]** ícone.

   ![](assets/email_rendering_04.png)

O relatório de renderização de email dedicado é exibido. Consulte Descrição [do relatório de renderização por](#email-rendering-report-description)email.

**Tópicos relacionados**:

* [Criação de um de email](../../channels/using/creating-an-email.md)
* [Envio de provas](../../sending/using/sending-proofs.md)
* [editor de Query](../../automating/using/editing-queries.md#about-query-editor)

## Descrição do relatório de renderização de email {#email-rendering-report-description}

Este relatório apresenta as renderizações por email à medida que elas são exibidas ao recipient. As renderizações por email podem ser diferentes com base em como o recipient abre o delivery de email: em um navegador, em um dispositivo móvel ou por meio de um aplicativo de email.

>[!NOTE]
>
>O número de renderizações disponíveis está listado em seu contrato de licença. Cada delivery com renderização **** por email ativada diminui as renderizações disponíveis (conhecidas como tokens) em uma.

O resumo do relatório apresenta o número de mensagens recebidas, indesejadas (spam), não recebidas ou recebidas pendentes.

![](assets/inbox_rendering_report.png)

O relatório divide-se em três partes: **[!UICONTROL Mobile]**, **[!UICONTROL Messaging clients]** e **[!UICONTROL Webmails]**. Role para baixo no relatório para exibir todas as renderizações agrupadas nessas três categorias.

![](assets/inbox_rendering_report_3.png)

Para obter os detalhes de cada relatório, clique no cartão correspondente. A renderização é exibida para o método de recebimento selecionado.

![](assets/inbox_rendering_report_2.png)

A **[!UICONTROL Technical data]** guia permite obter mais informações, como as datas de recebimento e captura, e os cabeçalhos completos de emails.
