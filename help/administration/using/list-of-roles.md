---
title: Lista de funções
description: Descubra a lista de funções que você pode atribuir aos seus usuários
audience: administration
feature: Access Management
role: Admin
level: Experienced
exl-id: 00714c80-bdaf-4241-bf2f-51498ca1dbef
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 77%

---

# Lista de funções{#list-of-roles}

Por padrão, o Adobe Campaign oferece um conjunto de funções que permite definir autorizações unitárias atribuídas a usuários e grupos de usuários.

Combinadas com as unidades organizacionais, as funções exibem uma visualização filtrada da interface e definem o acesso dos usuários aos diferentes recursos.

Funções podem ser gerenciadas no menu **[!UICONTROL Administration > Users & Security > Roles]**.

Os direitos padrão são:

* **[!UICONTROL Administration]**: Direito de administração genérico.

   >[!NOTE]
   >
   >Se você trabalhar com Acionadores do Experience Cloud, precisará da variável **[!UICONTROL Administration]** direito de acessar o menu Acionadores do Experience Cloud. Para obter mais informações sobre Experience Cloud Triggers, consulte esta página [página](../../integrating/using/about-adobe-experience-cloud-triggers.md).

* **[!UICONTROL Datamodel]**: Direito de executar publicações e criar recursos personalizados.
* **[!UICONTROL Generic import]**: Direito de executar uma importação genérica nos dados. Para que isso funcione, é necessário vincular o **[!UICONTROL Generic import]** para a **[!UICONTROL Workflow]** função.
* **[!UICONTROL Prepare deliveries]**: Direito de criar, modificar, preparar e excluir deliveries. Os usuários com essa função podem preparar o delivery, mas não podem enviá-lo.
* **[!UICONTROL Start deliveries]**: Direito de criar, modificar, preparar, enviar e excluir o delivery.
* **[!UICONTROL Workflow]**: Direito de gerenciar a execução de workflows (início, parada, pausa etc.). Os usuários com essa função não podem enviar um delivery mesmo em um workflow.

Para obter mais informações, consulte a tabela [Funções e permissões](/help/administration/using/assets/acs_rights.pdf), que detalha as funções disponíveis na interface, dependendo das autorizações selecionadas.

[![imagem](assets/user_management_3.png)](https://experienceleague.adobe.com/docs/campaign-standard/assets/acs_rights.pdf)

**Tópicos relacionados:**

* [Sobre gerenciamento de acesso](../../administration/using/about-access-management.md)
* [Gerenciamento de grupos e usuários](../../administration/using/managing-groups-and-users.md)
