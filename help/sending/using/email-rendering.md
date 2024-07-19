---
title: Renderização de email
description: Conheça o recurso de renderização de email.
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
feature: Send Time Optimization
role: User
level: Intermediate
exl-id: 31f4e557-55b3-4bf5-8d5d-9d412b7670a6
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '512'
ht-degree: 79%

---

# Renderização de email{#email-rendering}

Antes de clicar no botão **[!UICONTROL Send]**, verifique se a sua mensagem será exibida com eficiência em uma variedade de clientes Web, Webmails e dispositivos.

Para permitir isso, o Adobe Campaign captura a renderização e a disponibiliza em um relatório dedicado. Assim, você pré-visualiza a mensagem enviada nos diferentes contextos nos quais ela pode ser recebida.

Os clientes de dispositivos móveis, mensagens e webmail disponíveis para a **Renderização de email** no Adobe Campaign estão listados no [site](https://litmus.com/email-testing) do Litmus (clique em **Exibir todos os clientes de email**).

## Geração de renderização de email {#checking-the-email-rendering-report}

Após criar a entrega de email e definir seu conteúdo, assim como o público-alvo, siga as etapas abaixo.

1. Clique em **Audience** para acessar a guia **[!UICONTROL Test profiles]**.

   ![](assets/email_rendering_05.png)

1. Use o editor de consultas para definir os perfis de teste que deseja usar, incluindo os perfis de teste que são para uso de **Renderização de email**. Consulte [Sobre perfis de teste](../../audiences/using/managing-test-profiles.md).

   ![](assets/email_rendering_06.png)

1. Verifique e confirme a consulta e salve as alterações.
1. Clique no botão **[!UICONTROL Test]** na barra de ações.

   ![](assets/email_rendering_07.png)

1. Selecione a opção **[!UICONTROL Email rendering]** e clique em **[!UICONTROL OK]**.

   ![](assets/email_rendering_08.png)

   >[!NOTE]
   >
   >A opção **[!UICONTROL Proof + Email rendering]** permite enviar uma prova e usar o recurso de renderização de email simultaneamente. Você pode ter sua mensagem aprovada pelos destinatários de prova e, ao mesmo tempo, pode testar a forma como ela será recebida, dependendo das caixas de entrada direcionadas. Nesse caso, também é necessário selecionar Perfis de teste de prova. Consulte [Sobre perfis de teste](../../audiences/using/managing-test-profiles.md).

   A entrega de teste é enviada.

1. As miniaturas de renderização estão disponíveis alguns minutos após o envio das mensagens. Para acessá-las, selecione **[!UICONTROL Proofs]** na lista suspensa **[!UICONTROL Summary]**.

   ![](assets/email_rendering_03.png)

1. Na lista **[!UICONTROL Proofs]**, clique no ícone **[!UICONTROL Access email rendering]**.

   ![](assets/email_rendering_04.png)

O relatório de renderização de email dedicado é exibido. Consulte [Descrição do relatório de renderização de email](#email-rendering-report-description).

**Tópicos relacionados**:

* [Criação de um email](../../channels/using/creating-an-email.md)
* [Envio de provas](../../sending/using/sending-proofs.md)
* [Editor de consultas](../../automating/using/editing-queries.md#about-query-editor)

## Relatório de renderização de email {#email-rendering-report-description}

Este relatório apresenta as renderizações de email conforme elas são exibidas para o destinatário. As renderizações de email podem ser diferentes com base em como o destinatário abre a entrega de email: em um navegador, em um dispositivo móvel ou por um aplicativo de email.

### Tokens de renderização de email

O número de renderizações disponíveis está listado em seu contrato de licença. Cada entrega com a opção **Renderização de email** habilitada diminui uma renderização das renderizações disponíveis (conhecidas como tokens).

Os tokens são contabilizados para cada renderização individual e não para o relatório de renderização de email inteiro, o que significa que:

* **Cada vez** que o relatório de renderização de email é gerado, é deduzido um token por cliente da mensagem: um token para a renderização do Outlook 2000, um para a renderização do Outlook, um para a renderização do Apple Mail e assim por diante.

* **Para a mesma entrega**, se você gerar a renderização de email novamente, o número de tokens disponíveis será reduzido novamente pelo número de renderizações geradas.

### Resumo do relatório

O resumo do relatório apresenta o número de mensagens recebidas, indesejadas (spam), não recebidas ou recebimentos pendentes.

![](assets/inbox_rendering_report.png)

O relatório divide-se em três partes: **[!UICONTROL Mobile]**, **[!UICONTROL Messaging clients]** e **[!UICONTROL Webmails]**. Role para baixo no relatório para exibir todas as renderizações agrupadas nessas três categorias.

![](assets/inbox_rendering_report_3.png)

Para obter os detalhes de cada relatório, clique no cartão correspondente. A renderização é exibida para o método de recebimento selecionado.

![](assets/inbox_rendering_report_2.png)

A guia **[!UICONTROL Technical data]** permite obter mais informações, como as datas de recebimento e captura e os cabeçalhos completos de emails.
