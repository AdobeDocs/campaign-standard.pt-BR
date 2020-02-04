---
title: Lista de funções
description: Descubra a lista de funções que podem ser atribuídas aos usuários.
page-status-flag: never-activated
uuid: 128aaf9b-9b7d-49f3-9e1f-72e79a29baa0
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: users-and-security
discoiquuid: ceaa3c94-9e1a-4271-b443-b00b4068929f
context-tags: role,overview;role,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e31e8c63fa94d190211c7a51e7f1091657c9f479

---


# Lista de funções{#list-of-roles}

Por padrão, o Adobe Campaign oferece um conjunto de funções que permite definir autorizações unitárias atribuídas a usuários e grupos de usuários. Combinadas com unidades organizacionais, as funções fornecem aos usuários uma exibição filtrada da interface e definem seu acesso aos diferentes recursos. Para obter mais informações, consulte a tabela [](/help/administration/using/assets/acs_rights.pdf)Funções e permissões.

![](assets/user_management_3.png)

As funções podem ser gerenciadas no **[!UICONTROL Administration > Users & Security > Roles]**menu.

Os direitos padrão são:

* **[!UICONTROL Administration]**: Direito administrativo genérico.
* **[!UICONTROL Datamodel]**: Direito de executar publicações e criar recursos personalizados.
* **[!UICONTROL Export]**: Direito de exportar dados.
* **[!UICONTROL Generic import]**: Direito de executar uma importação genérica nos dados. Para que isso funcione, é necessário vincular a**[!UICONTROL Generic import]** função à **[!UICONTROL Workflow]**.
* **[!UICONTROL Prepare deliveries]**: Direito de criar, modificar, preparar e excluir entregas. Os usuários com essa função podem preparar a entrega, mas não enviá-la.
* **[!UICONTROL Start deliveries]**: Direito de criar, modificar, preparar, enviar e excluir entregas.
* **[!UICONTROL Workflow]**: Direito de criar, modificar, iniciar e excluir fluxos de trabalho. Os usuários com essa função não podem enviar uma entrega mesmo em um fluxo de trabalho.

>[!IMPORTANT]
>
>As funções **[!UICONTROL Deliverability]**,**[!UICONTROL Command execution]**, **[!UICONTROL Export]**e**[!UICONTROL File access]** **[!UICONTROL Message Center push]**são apenas para uso interno dos administradores da Adobe. Eles não devem ser concedidos a um usuário.

**Tópicos relacionados:**

* [Sobre o gerenciamento de acesso](../../administration/using/about-access-management.md)
* [Gerenciamento de grupos e usuários](../../administration/using/managing-groups-and-users.md)

