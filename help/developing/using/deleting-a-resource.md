---
title: Exclusão de um recurso
description: Saiba como excluir um recurso
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
feature: Data Model
role: Developer
level: Experienced
exl-id: 4ddfdbcc-a154-4c10-a97e-73ad888d1f1f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 14%

---

# Exclusão de um recurso{#deleting-a-resource}

Para excluir um recurso, o recurso em questão deve ser um **[!UICONTROL Draft]**. O recurso está no status **[!UICONTROL Draft]** se:

* Ele acabou de ser criado e ainda não foi publicado.
* Se já tiver sido publicado, o recurso deverá ser reformulado.

>[!IMPORTANT]
>
>Recriar e excluir um recurso personalizado são operações confidenciais que podem afetar outros recursos. Essas ações devem ser executadas somente por um usuário especialista.

Para recriar e excluir um recurso publicado:

1. Selecione o recurso que deseja recriar.
1. Clique no botão **[!UICONTROL Re-draft]** na barra de ações.

   ![](assets/schema_extension_uc26.png)

1. Clique em **[!UICONTROL Ok]**.

   >[!IMPORTANT]
   >
   >Esta ação é definitiva: a(s) tabela(s) de banco de dados do recurso e suas colunas e seus dados serão excluídos permanentemente quando a modificação for publicada, o que pode resultar em links quebrados de outros recursos personalizados. Somente a definição de recurso permanecerá disponível.

   ![](assets/schema_extension_uc27.png)

   >[!NOTE]
   >
   >Se você recriar uma extensão do recurso **Perfis (perfil)** predefinido, também deverá recriar qualquer extensão de **Perfil de teste (seedMember)** que tenha definido. Para obter mais informações sobre a extensão do recurso de perfil, consulte [esta seção](../../developing/using/extending-the-profile-resource-with-a-new-field.md).

1. Publish do recurso. Para obter etapas mais detalhadas, consulte [Publicação de um recurso personalizado](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).

   O recurso entra no modo **Rascunho** e seu status de ativação é **[!UICONTROL Inactive]**.

1. No modo **[!UICONTROL List]**, marque o recurso a ser excluído e clique no ícone ![](assets/delete_darkgrey-24px.png) **[!UICONTROL Delete element]**.

   ![](assets/schema_extension_uc28.png)

Seu recurso foi excluído do modelo de dados.

>[!NOTE]
>
>Se um campo de um recurso personalizado usado em um evento for modificado ou excluído, a publicação do evento correspondente será automaticamente cancelada. Consulte [Desfazer a publicação de um evento transacional](../../channels/using/publishing-transactional-event.md#unpublishing-an-event).
