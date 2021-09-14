---
title: Lista de funções
description: Descubra a lista de funções que você pode atribuir aos seus usuários.
audience: administration
content-type: reference
topic-tags: users-and-security
context-tags: role,overview;role,main
feature: Access Management
role: Admin
level: Experienced
exl-id: 00714c80-bdaf-4241-bf2f-51498ca1dbef
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 85%

---

# Lista de funções{#list-of-roles}

Por padrão, o Adobe Campaign oferece um conjunto de funções que permite definir autorizações unitárias atribuídas a usuários e grupos de usuários.

Combinadas com as unidades organizacionais, as funções exibem uma visualização filtrada da interface e definem o acesso dos usuários aos diferentes recursos.

Funções podem ser gerenciadas no menu **[!UICONTROL Administration > Users & Security > Roles]**.

Os direitos padrão são:

* **[!UICONTROL Administration]**: Direito de administração genérico.

   >[!NOTE]
   >
   >Se precisar trabalhar com Experience Cloud Triggers, será necessário o **[!UICONTROL Administration]** direito para acessar o menu Experience Cloud Triggers. Para obter mais informações sobre Experience Cloud Triggers, consulte esta [página](../../integrating/using/about-adobe-experience-cloud-triggers.md).

* **[!UICONTROL Datamodel]**: Direito de executar publicações e criar recursos personalizados.
* **[!UICONTROL Generic import]**: Direito de executar uma importação genérica nos dados. Para que isso funcione, é necessário vincular a função **[!UICONTROL Generic import]** à função **[!UICONTROL Workflow]**.
* **[!UICONTROL Prepare deliveries]**: Direito de criar, modificar, preparar e excluir deliveries. Os usuários com essa função podem preparar o delivery, mas não podem enviá-lo.
* **[!UICONTROL Start deliveries]**: Direito de criar, modificar, preparar, enviar e excluir o delivery.
* **[!UICONTROL Workflow]**: Direito de gerenciar a execução de workflows (início, parada, pausa etc.). Os usuários com essa função não podem enviar um delivery mesmo em um workflow.

Para obter mais informações, consulte a tabela [Funções e permissões](/help/administration/using/assets/acs_rights.pdf), que detalha as funções disponíveis na interface, dependendo das autorizações selecionadas.

[![imagem](assets/user_management_3.png)](https://experienceleague.adobe.com/docs/campaign-standard/assets/acs_rights.pdf?lang=en)

**Tópicos relacionados:**

* [Sobre gerenciamento de acesso](../../administration/using/about-access-management.md)
* [Gerenciamento de grupos e usuários](../../administration/using/managing-groups-and-users.md)
