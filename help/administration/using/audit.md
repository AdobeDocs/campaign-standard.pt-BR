---
title: Trilha de auditoria
description: Monitorar ações e eventos com a Trilha de auditoria do Campaign
audience: administration
feature: Access Management
role: Admin
level: Experienced
exl-id: bda6f8d5-3bcf-498c-a7c4-d3c2c79b9510
source-git-commit: 64da7ac09e1b0fbf13ba1e563b6dc7be995b1640
workflow-type: tm+mt
source-wordcount: '495'
ht-degree: 3%

---

# Trilha de auditoria {#audit}

O **[!UICONTROL Audit trail]** fornece acesso ao histórico completo de alterações feitas na instância.

O **[!UICONTROL Audit trail]** captura, em tempo real, uma lista abrangente de ações e eventos que ocorrem na sua instância do Adobe Campaign Standard. Ele inclui uma forma de autoatendimento para acessar um histórico de dados que ajudam a responder perguntas como: o que aconteceu com seus fluxos de trabalho, recursos e opções personalizados, quem os atualizou pela última vez ou o que seus usuários fizeram na instância.

![](assets/audit-trail.png)

**[!UICONTROL Audit trail]** consiste em três componentes:

* **Trilha de auditoria de recursos personalizados**: verifique a atividade e a última modificação feita nos recursos personalizados.

  Para obter mais informações sobre **[!UICONTROL Custom resources]**, consulte esta [página](../../developing/using/key-steps-to-add-a-resource.md).

* **Trilha de auditoria do fluxo de trabalho**: verifique a atividade e a última modificação feita nos fluxos de trabalho, além do estado dos fluxos de trabalho, como:

   * Criado
   * Modificado
   * Excluído
   * Início do fluxo de trabalho
   * Fluxo de trabalho Pausar
   * Interrupção do fluxo de trabalho
   * Reinicialização do fluxo de trabalho
   * Limpeza do fluxo de trabalho
   * Simular Fluxo de Trabalho
   * Ativação do fluxo de trabalho
   * Interrupção Imediata do Fluxo de Trabalho
   * Reinicialização do fluxo de trabalho com o mesmo usuário
   * comando Workflow Restart Unknown

  Para obter mais informações sobre **[!UICONTROL Workflows]**, consulte esta [página](../../automating/using/get-started-workflows.md).

* **Trilha de auditoria de opção**: verifique a atividade e a última modificação feita nas opções.

  Para obter mais informações sobre **[!UICONTROL Options]**, consulte esta [página](../../administration/using/about-campaign-standard-settings.md).

Observe que, por padrão, o período de retenção é de 30 dias.

## Acessando a Trilha de auditoria {#audit-access}

Para acessar a Trilha de auditoria da instância:

1. No Adobe Campaign Standard, no menu avançado, selecione **[!UICONTROL Administration]** > **[!UICONTROL Audit trail]**.

   ![](assets/audit-trail.png)

1. A janela **[!UICONTROL Audit trail]** é aberta com a lista de suas entidades. O Adobe Campaign Standard auditará a criação, edição e exclusão de ações para fluxos de trabalho, opções e recursos personalizados.

   No menu **[!UICONTROL Search]**, você pode filtrar sua entidade em:

   * **[!UICONTROL Start date]**
   * **[!UICONTROL End date]**
   * **[!UICONTROL Type]**: Tipo de entidade entre Tudo, Fluxo de Trabalho, Recurso Personalizado e Opção.
   * **[!UICONTROL Entity name]**: ID do fluxo de trabalho, opção ou recurso personalizado

   ![](assets/audit-trail_2.png)

1. Selecione uma das entidades para saber mais sobre as últimas modificações.

1. A janela Audit entity fornece informações mais detalhadas sobre a entidade escolhida, como:

   * **[!UICONTROL Entity]**: ID do fluxo de trabalho, opção ou recurso personalizado.
   * **[!UICONTROL Action]**: Última ação executada nesta entidade.
   * **[!UICONTROL Changed by]**: Nome de usuário da última pessoa que modificou esta entidade pela última vez.
   * **[!UICONTROL Changed date]**: Data da última ação executada nesta entidade.
   * **[!UICONTROL Content]**: Bloco de código que fornece mais informações sobre o que foi alterado exatamente em sua entidade.

   Neste exemplo, podemos ver que o workflow WKF110 foi iniciado em 26 de agosto pelo administrador de negócios dessa instância.

   ![](assets/audit-trail_3.png)

## Ativar/desativar trilha de auditoria {#enable-disable-audit}

>[!NOTE]
>
> Somente administradores funcionais podem ativar ou desativar a Trilha de auditoria. Para obter mais informações, consulte esta [página](../../administration/using/users-management.md#functional-administrators).

A trilha de auditoria pode ser facilmente ativada ou desativada para uma atividade específica.

Para fazer isso:

1. No Adobe Campaign Standard, no menu avançado, selecione **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**.

   ![](assets/audit-trail_4.png)

1. Selecione uma das seguintes opções dependendo da entidade que deseja desativar:

   * **[!UICONTROL XtkAudit_Workflows]** opção para gerenciar a Trilha de auditoria para Fluxos de trabalho.
   * **[!UICONTROL XtkAudit_Option]** opção para gerenciar a Trilha de auditoria para Opções.
   * Opção **[!UICONTROL XtkAudit_CusResource]** para gerenciar a Trilha de auditoria para recursos personalizados.
   * **[!UICONTROL XtkAudit_Enable_All]** opção para gerenciar a Trilha de auditoria para cada entidade.

     >[!NOTE]
     >
     >Se a opção **[!UICONTROL XtkAudit_Enable_All]** estiver definida como 0, o recurso **[!UICONTROL Audit trail]** será completamente desabilitado, independentemente de outros valores de opção individuais.

   ![](assets/audit-trail_5.png)

1. Na página **[!UICONTROL Options]**, defina o **[!UICONTROL Value (integer)]** como 0 se desejar desabilitar o **[!UICONTROL Audit trail]** ou como 1 para habilitá-lo.

   ![](assets/audit-trail_6.png)

1. Clique em **[!UICONTROL Save]**.
