---
title: Lista de funções
description: Descubra a lista de funções que podem ser atribuídas aos usuários.
page-status-flag: nunca ativado
uuid: 128aaf9b-9b7d-49f3-9e1f-72e79a29baa0
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: administração
content-type: referência
topic-tags: usuários e segurança
discoiquuid: ceaa3c94-9e1a-4271-b443-b00b4068929f
context-tags: função,visão geral;função,principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Lista de funções{#list-of-roles}

Por padrão, o Adobe Campaign oferece um conjunto de funções que permite definir autorizações unitárias atribuídas a usuários e grupos de usuários. Combinadas com unidades organizacionais, as funções fornecem aos usuários uma exibição filtrada da interface e definem seu acesso aos diferentes recursos. Para obter mais informações, consulte a tabela [](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf)Funções e permissões.

[![imagem](/help/administration/using/assets/user_management_3.png)](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf)

As funções podem ser gerenciadas no **[!UICONTROL Administration > Users & Security > Roles]** menu.

Os direitos padrão são:

* **[!UICONTROL Administration]**: Direito administrativo genérico.
* **[!UICONTROL Datamodel]**: Direito de executar publicações e criar recursos personalizados.
* **[!UICONTROL Export]**: Direito de exportar dados.
* **[!UICONTROL Generic import]**: Direito de executar uma importação genérica nos dados. Para que isso funcione, é necessário vincular a **[!UICONTROL Generic import]** função à **[!UICONTROL Workflow]** .
* **[!UICONTROL Prepare deliveries]**: Direito de criar, modificar, preparar e excluir entregas. Os usuários com essa função podem preparar a entrega, mas não enviá-la.
* **[!UICONTROL Start deliveries]**: Direito de criar, modificar, preparar, enviar e excluir entregas.
* **[!UICONTROL Workflow]**: Direito de criar, modificar, iniciar e excluir fluxos de trabalho. Os usuários com essa função não podem enviar uma entrega mesmo em um fluxo de trabalho.

>[!CAUTION]
>
>As funções **[!UICONTROL Deliverability]**, **[!UICONTROL Command execution]**, **[!UICONTROL Export]** e **[!UICONTROL File access]** **[!UICONTROL Message Center push]** são apenas para uso interno dos administradores da Adobe. Eles não devem ser concedidos a um usuário.

**Tópicos relacionados:**

* [Sobre o gerenciamento de acesso](../../administration/using/about-access-management.md)
* [Gerenciamento de grupos e usuários](../../administration/using/managing-groups-and-users.md)

