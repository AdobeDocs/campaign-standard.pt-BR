---
title: Lista de funções
seo-title: Lista de funções
description: Lista de funções
seo-description: Descubra a lista de funções que podem ser atribuídas aos usuários.
page-status-flag: nunca ativado
uuid: 128 aaf 9 b -9 b 7 d -49 f 3-9 e 1 f -72 e 79 a 29 baa 0
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: usuários e segurança
discoiquuid: ceaa 3 c 94-9 e 1 a -4271-b 443-b 00 b 4068929 f
context-tags: função, visão geral; role, main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6a877d878f01fa1e541dc20b8b0941602113d15b

---


# List of roles{#list-of-roles}

Por padrão, o Adobe Campaign oferece um conjunto de funções que permite definir autorizações unitárias atribuídas a usuários e grupos de usuários. Combinado com unidades organizacionais, as funções fornecem aos usuários uma visão filtrada da interface e definem o acesso aos diferentes recursos. For more on this, refer to the [Roles and permissions table](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf).

![](assets/user_management_3.png)

Roles can be managed from the **[!UICONTROL Administration > Users & Security > Roles]** menu.

Os direitos padrão são:

* **[!UICONTROL Administration]**: Administração genérica à direita.
* **[!UICONTROL Datamodel]**: Direito de executar publicações e criar recursos personalizados.
* **[!UICONTROL Export]**: Direito de exportar dados.
* **[!UICONTROL Generic import]**: Direita para executar uma importação genérica em dados. For this to work, you need to link the **[!UICONTROL Generic import]** role to the **[!UICONTROL Workflow]** role.
* **[!UICONTROL Prepare deliveries]**: O direito de criar, editar, iniciar a preparação de entrega e enviar provas.
* **[!UICONTROL Start deliveries]**: Direito de validar entregas previamente preparadas.
* **[!UICONTROL Workflow]**: Direito de usar fluxos de trabalho.

>[!CAUTION]
>
>A função DELIVERABILITY é usada somente para administradores da Adobe. Não deve ser concedida a um usuário.

**Tópicos relacionados:**

* [Sobre o gerenciamento de acesso](../../administration/using/about-access-management.md)
* [Gerenciamento de grupos e usuários](../../administration/using/managing-groups-and-users.md)

