---
title: Exclusão de um recurso
seo-title: Exclusão de um recurso
description: Exclusão de um recurso
seo-description: 'Saiba como excluir um recurso '
page-status-flag: nunca ativado
uuid: 5 de 27589-6 fa 5-412 c -8 e 5 a-a 4976 de 05715
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: adição ou extensão-a-resource
discoiquuid: 0130733 d -4 e 3 f -40 cd-b 959-56381 f 2 c 8 f 44
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a12df43de55dedf388a397fbf4670d99e3ea7f3d

---


# Deleting a resource{#deleting-a-resource}

To delete a resource, the resource in question must be a **[!UICONTROL Draft]**. The resource is in **[!UICONTROL Draft]** status if:

* Ela acabou de ser criada e ainda não foi publicada.
* Se já tiver sido publicado, o recurso precisará ser recompilado.

>[!CAUTION]
>
>A recompilação e a exclusão de um recurso personalizado são operações sigilosas que podem afetar outros recursos. Essas ações devem ser executadas somente por um usuário especialista.

Para rerascunhar e excluir um recurso publicado:

1. Selecione o recurso que deseja redesenhar.
1. Click the **[!UICONTROL Re-draft]** button in the action bar.

   ![](assets/schema_extension_uc26.png)

1. Click **[!UICONTROL Ok]**.

   >[!CAUTION]
   >
   >Esta ação é definitiva: a tabela ou os dados de banco de dados do recurso, bem como seus dados, serão excluídos permanentemente quando a modificação for publicada, o que pode resultar em links quebrados de outros recursos personalizados. Somente a definição do recurso continuará disponível.

   ![](assets/schema_extension_uc27.png)

   >[!NOTE]
   >
   >If you re-draft an extension of the out-of-the-box **Profiles (profile)** resource, you must also re-draft any **Test profile (seedMember)** extension you may have defined. For more on extending the profile resource, see [this section](../../developing/using/extending-the-profile-resource-with-a-new-field.md).

1. Publique o recurso. For more detailed steps, refer to [Publishing a custom resource](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).

   The resource then goes into **Draft** mode and its activation status is **[!UICONTROL Inactive]**.

1. In **[!UICONTROL List]** mode, check the resource to delete then click the ![](assets/delete_darkgrey-24px.png) **[!UICONTROL Delete element]** icon.

   ![](assets/schema_extension_uc28.png)

Seu recurso é excluído do modelo de dados.

>[!NOTE]
>
>Se um campo de um recurso personalizado usado em um evento for modificado ou excluído, o evento correspondente será despublicado automaticamente. See [Configuring transactional messaging](../../administration/using/configuring-transactional-messaging.md).

