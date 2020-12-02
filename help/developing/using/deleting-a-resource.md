---
solution: Campaign Standard
product: campaign
title: Excluir um recurso
description: 'Saiba como excluir um recurso '
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
translation-type: tm+mt
source-git-commit: fc755f3176622e1faf08ccfa4236e016110f9a68
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 14%

---


# Excluir um recurso{#deleting-a-resource}

Para excluir um recurso, o recurso em questão deve ser **[!UICONTROL Draft]**. O recurso está no status **[!UICONTROL Draft]** se:

* Acabou de ser criada e ainda não foi publicada.
* Se já foi publicado, o recurso tem de ser reformulado.

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
   >Esta ação é definitiva: a tabela ou colunas do banco de dados do recurso e seus dados serão permanentemente excluídos quando a modificação for publicada, o que pode resultar em links quebrados de outros recursos personalizados. Somente a definição do recurso permanecerá disponível.

   ![](assets/schema_extension_uc27.png)

   >[!NOTE]
   >
   >Se você redesenhar uma extensão dos recursos predefinidos **Perfis (perfil)**, também deverá redesenhar qualquer extensão **Test perfil (sementeMember)** que tenha definido. Para obter mais informações sobre a extensão do recurso de perfil, consulte [esta seção](../../developing/using/extending-the-profile-resource-with-a-new-field.md).

1. Publique o recurso. Para obter etapas mais detalhadas, consulte [Publicar um recurso personalizado](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).

   O recurso então entra no modo **Rascunho** e seu status de ativação é **[!UICONTROL Inactive]**.

1. No modo **[!UICONTROL List]**, verifique o recurso a ser excluído e clique no ícone ![](assets/delete_darkgrey-24px.png) **[!UICONTROL Delete element]**.

   ![](assets/schema_extension_uc28.png)

Seu recurso é excluído do modelo de dados.

>[!NOTE]
>
>Se um campo de um recurso personalizado usado em um evento for modificado ou excluído, a publicação do evento correspondente será automaticamente cancelada. Consulte [Cancelar publicação de um evento transacional](../../channels/using/publishing-transactional-event.md#unpublishing-an-event).
