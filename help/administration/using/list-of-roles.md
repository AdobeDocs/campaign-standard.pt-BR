---
title: Lista de funções
description: Descubra a lista de funções que você pode atribuir aos usuários.
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
source-git-commit: c65cce2168219b3cd8cbd6704bdd0b6f3f55e3e6
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 7%

---


# Lista de funções{#list-of-roles}

Por padrão, o Adobe Campaign oferta um conjunto de funções que permite definir autorizações unitárias atribuídas a usuários e grupos de usuários.

Combinadas com unidades organizacionais, as funções fornecem aos usuários uma visualização filtrada da interface e definem seu acesso aos diferentes recursos.

Para obter mais informações, consulte a tabela [](/help/administration/using/assets/acs_rights.pdf)Funções e permissões, que detalha as funções disponíveis na interface, dependendo das autorizações selecionadas.

[![imagem](assets/user_management_3.png)](https://docs.adobe.com/content/help/en/campaign-standard/using/administrating/users-and-security/assets/acs_rights.pdf)

As funções podem ser gerenciadas a partir do **[!UICONTROL Administration > Users & Security > Roles]** menu.

Os direitos padrão são:

* **[!UICONTROL Administration]**: Direito administrativo genérico.
* **[!UICONTROL Datamodel]**: Direito de executar publicações e criar recursos personalizados.
* **[!UICONTROL Generic import]**: Direito de executar uma importação genérica nos dados. Para que isso funcione, é necessário vincular a **[!UICONTROL Generic import]** função à **[!UICONTROL Workflow]** .
* **[!UICONTROL Prepare deliveries]**: Direito de criar, modificar, preparar e excluir delivery. Os usuários com essa função podem preparar o delivery, mas não enviá-lo.
* **[!UICONTROL Start deliveries]**: Direito de criar, modificar, preparar, enviar e excluir delivery.
* **[!UICONTROL Workflow]**: Direito de gerenciar a execução de workflows (start, parada, pausa etc.). Os usuários com essa função não podem enviar um delivery mesmo em um fluxo de trabalho.

**Tópicos relacionados:**

* [Sobre o gerenciamento de acesso](../../administration/using/about-access-management.md)
* [Gerenciamento de grupos e usuários](../../administration/using/managing-groups-and-users.md)
