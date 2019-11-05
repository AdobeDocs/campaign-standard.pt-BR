---
title: Excluir um recurso
description: 'Saiba como excluir um recurso '
page-status-flag: nunca ativado
uuid: 5de27589-6fa5-412c-8e5a-a4976de05715
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: desenvolvimento
content-type: referência
topic-tags: adição ou extensão de um recurso
discoiquuid: 0130733d-4e3f-40cd-b959-56381f2c8f44
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Excluir um recurso{#deleting-a-resource}

Para excluir um recurso, o recurso em questão deve ser um **[!UICONTROL Draft]**. O recurso está em **[!UICONTROL Draft]** status se:

* Acabou de ser criada e ainda não foi publicada.
* Se já foi publicado, o recurso tem de ser reformulado.

>[!CAUTION]
>
>A reformulação e exclusão de um recurso personalizado são operações confidenciais que podem afetar outros recursos. Essas ações devem ser executadas somente por um usuário especialista.

Para redesenhar e excluir um recurso publicado:

1. Selecione o recurso que deseja redesenhar.
1. Clique no **[!UICONTROL Re-draft]** botão na barra de ações.

   ![](assets/schema_extension_uc26.png)

1. Click **[!UICONTROL Ok]**.

   >[!CAUTION]
   >
   >Esta ação é definitiva: a tabela ou colunas do banco de dados do recurso e seus dados serão permanentemente excluídos quando a modificação for publicada, o que pode resultar em links quebrados de outros recursos personalizados. Somente a definição do recurso permanecerá disponível.

   ![](assets/schema_extension_uc27.png)

   >[!NOTE]
   >
   >Se você redesenhar uma extensão do recurso predefinido de **Perfis (perfil)** , também deverá redesenhar qualquer extensão de perfil **de teste (sementeMember)** que você tenha definido. Para obter mais informações sobre como estender o recurso de perfil, consulte [esta seção](../../developing/using/extending-the-profile-resource-with-a-new-field.md).

1. Publique o recurso. Para obter etapas mais detalhadas, consulte [Publicação de um recurso](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource)personalizado.

   O recurso então entra no modo **Rascunho** e seu status de ativação é **[!UICONTROL Inactive]**.

1. No **[!UICONTROL List]** modo, marque o recurso a ser excluído e clique no ![](assets/delete_darkgrey-24px.png) ícone **[!UICONTROL Delete element]** .

   ![](assets/schema_extension_uc28.png)

Seu recurso é excluído do modelo de dados.

>[!NOTE]
>
>Se um campo de um recurso personalizado usado em um evento for modificado ou excluído, o evento correspondente será automaticamente despublicado. See [Configuring transactional messaging](../../administration/using/configuring-transactional-messaging.md).

