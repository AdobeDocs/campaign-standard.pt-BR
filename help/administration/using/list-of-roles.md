---
solution: Campaign Standard
product: campaign
title: Lista de funções
description: Descubra a lista de funções que você pode atribuir aos seus usuários.
audience: administration
content-type: reference
topic-tags: users-and-security
context-tags: role,overview;role,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '203'
ht-degree: 94%

---


# Lista de funções{#list-of-roles}

Por padrão, o Adobe Campaign oferece um conjunto de funções que permite definir autorizações unitárias atribuídas a usuários e grupos de usuários.

Combinadas com as unidades organizacionais, as funções exibem uma visualização filtrada da interface e definem o acesso dos usuários aos diferentes recursos.

Para obter mais informações, consulte a tabela [Funções e permissões](/help/administration/using/assets/acs_rights.pdf), que detalha as funções disponíveis na interface, dependendo das autorizações selecionadas.

[![imagem](assets/user_management_3.png)](https://docs.adobe.com/content/help/en/campaign-standard/using/administrating/users-and-security/assets/acs_rights.pdf)

Funções podem ser gerenciadas no menu **[!UICONTROL Administration > Users & Security > Roles]**.

Os direitos padrão são:

* **[!UICONTROL Administration]**: Direito de administração genérico.
* **[!UICONTROL Datamodel]**: Direito de executar publicações e criar recursos personalizados.
* **[!UICONTROL Generic import]**: Direito de executar uma importação genérica nos dados. Para que isso funcione, é necessário vincular a função **[!UICONTROL Generic import]** à função **[!UICONTROL Workflow]**.
* **[!UICONTROL Prepare deliveries]**: Direito de criar, modificar, preparar e excluir deliveries. Os usuários com essa função podem preparar o delivery, mas não podem enviá-lo.
* **[!UICONTROL Start deliveries]**: Direito de criar, modificar, preparar, enviar e excluir o delivery.
* **[!UICONTROL Workflow]**: Direito de gerenciar a execução de workflows (início, parada, pausa etc.). Os usuários com essa função não podem enviar um delivery mesmo em um workflow.

**Tópicos relacionados:**

* [Sobre o gerenciamento de acesso](../../administration/using/about-access-management.md)
* [Gerenciamento de grupos e usuários](../../administration/using/managing-groups-and-users.md)
