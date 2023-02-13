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
ht-degree: 16%

---

# Exclusão de um recurso{#deleting-a-resource}

Para excluir um recurso, o recurso em questão deve ser um **[!UICONTROL Draft]**. O recurso está em **[!UICONTROL Draft]** status se:

* Acabou de ser criada e ainda não foi publicada.
* Se já tiver sido publicado, o recurso terá de ser reelaborado.

>[!IMPORTANT]
>
>A reformulação e exclusão de um recurso personalizado são operações confidenciais que podem afetar outros recursos. Essas ações devem ser executadas somente por um usuário especialista.

Para redesenhar e excluir um recurso publicado:

1. Selecione o recurso que deseja redesenhar.
1. Clique no botão **[!UICONTROL Re-draft]** na barra de ações.

   ![](assets/schema_extension_uc26.png)

1. Clique em **[!UICONTROL Ok]**.

   >[!IMPORTANT]
   >
   >Esta ação é definitiva: a tabela ou colunas do banco de dados do recurso e seus dados serão excluídos permanentemente quando a modificação for publicada, o que pode resultar em links quebrados de outros recursos personalizados. Somente a definição de recurso permanecerá disponível.

   ![](assets/schema_extension_uc27.png)

   >[!NOTE]
   >
   >Se você reprojetar uma extensão do **Perfis (perfil)** , você também deve redesenhar qualquer **Perfil de ensaio (seedMember)** extensão que você pode ter definido. Para obter mais informações sobre como estender o recurso de perfil, consulte [esta seção](../../developing/using/extending-the-profile-resource-with-a-new-field.md).

1. Publique o recurso. Para obter etapas mais detalhadas, consulte [Publicação de um recurso personalizado](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).

   O recurso entra em **Rascunho** e seu status de ativação é **[!UICONTROL Inactive]**.

1. Em **[!UICONTROL List]** , marque o recurso a ser excluído e clique no botão ![](assets/delete_darkgrey-24px.png) **[!UICONTROL Delete element]** ícone .

   ![](assets/schema_extension_uc28.png)

Seu recurso é excluído do modelo de dados.

>[!NOTE]
>
>Se um campo de um recurso personalizado usado em um evento for modificado ou excluído, a publicação do evento correspondente será automaticamente cancelada. Consulte [Cancelamento de publicação de um evento transacional](../../channels/using/publishing-transactional-event.md#unpublishing-an-event).
