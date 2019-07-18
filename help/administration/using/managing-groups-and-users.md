---
title: Gerenciamento de grupos e usuários
seo-title: Gerenciamento de grupos e usuários
description: Gerenciamento de grupos e usuários
seo-description: Saiba como criar grupos de segurança e gerenciar usuários.
page-status-flag: nunca ativado
uuid: b 3 a 3 a 2 e 3-9 d 69-4231-b 724-8 f 37419 f 7 a 61
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: usuários e segurança
discoiquuid: 12 f 896 ab-ee 79-4 d 96-976 d-cf 34643491 b 4
context-tags: usuário, visão geral; user, main; segurança, visão geral; segurança, principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a12df43de55dedf388a397fbf4670d99e3ea7f3d

---


# Managing groups and users{#managing-groups-and-users}

## About security groups {#about-security-groups}

Grupos de segurança são conjuntos de usuários que compartilham as mesmas funções e direitos em sua organização.

Os usuários devem estar sempre vinculados a um grupo de segurança. Isso permitirá a atribuição de funções e unidades organizacionais específicas.

For more information on roles, the tables in the following page present the different operations available according to a user's role(s): [Adobe Campaign Standard authorizations](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf).

Os grupos de segurança padrão são:

* **[!UICONTROL Administrators]**
* **[!UICONTROL Delivery supervisors]**
* **[!UICONTROL Message Center agents]**
* **[!UICONTROL Standard Users]**
* **[!UICONTROL Workflow supervisors]**

Se um usuário não estiver vinculado a nenhum grupo de segurança, ele não poderá acessar o Adobe Campaign.

To restrict a user's access, do not add the user to the Campaign Standard users group as this is linked to **[!UICONTROL All]** organizational unit.

## Creating a security group and assigning users {#creating-a-security-group-and-assigning-users}

>[!CAUTION]
>
>Observe que no Admin Console, os grupos de segurança são referenciados como perfis.

Você pode criar seus próprios grupos de segurança se os grupos prontos para uso não forem suficientes para gerenciar os usuários. Eles podem ser gerenciados por administradores que têm acesso aos menus de administração do Adobe Campaign e ao Admin Console. For more information on the Admin console, refer to this [documentation](https://helpx.adobe.com/enterprise/managing/user-guide.html).

Aqui, primeiro, atribua os dois grupos do Standard e Administrador padrão aos nossos usuários. Esses grupos de segurança restringirão algumas funcionalidades do Adobe Campaign: o Usuário padrão tem acesso básico ao Adobe Campaign, enquanto o administrador pode acessar os menus de administração por exemplo.

Observe que quaisquer alterações feitas nos grupos de segurança no Admin Console serão sincronizadas assim que os usuários fizerem logon no Adobe Campaign.

Em seguida, queremos criar um conjunto de grupos de segurança Geometrixx e Roupas Geometrixx que restringirão algum acesso, dependendo das unidades organizacionais de nosso Usuário e Administrador padrão.

![](assets/ootb_security_group_1.png)

Primeiro, você deve atribuir um dos grupos de segurança prontos para os usuários:

1. In the Admin console, select your instance then the **Users** tab.

   ![](assets/manage_security_group_2.png)

1. Click the **[!UICONTROL Add user]** button and enter your user's email address.
1. In the **[!UICONTROL Assign Products]** tab, select your instance then the **[!UICONTROL Administrators]** out-of-the-box security group from the drop-down list. Isso permitirá que o usuário tenha acesso aos menus de administração e crie os próximos grupos de segurança.

   ![](assets/ootb_security_group_2.png)

1. Click **[!UICONTROL Save]** and follow the same procedures to assign the **[!UICONTROL Standard Users]** out-of-the-box security group to your new user.

   ![](assets/ootb_security_group_3.png)

Once your two users are attached to the **[!UICONTROL Administrators]** and **[!UICONTROL Standard users]** out-of-the-box security groups which assign roles to our users, the Administrator user can now create the two security groups **Geometrixx** and **Geometrixx Clothes** that will assign organizational units to our users in addition to the out-of-the-box security groups.

1. In the Admin console, select your instance then the **Products** tab.
1. Click the **New Profile** button to create the **Geometrixx** security group.

   ![](assets/create_security_1.png)

1. Type the **[!UICONTROL Profile name]** by following this exact syntax: **[!UICONTROL Campaign Standard- instance name - ID of the security group]** and click **[!UICONTROL Done]**.

   A ID escolhida será usada ao criar o grupo de segurança no Adobe Campaign.

   >[!NOTE]
   >
   >If the above syntax doesn't seem to work with an older instance, it needs to be replaced by **[!UICONTROL Campaign - instance name - ID of the security group]**.

   ![](assets/manage_security_group_1.png)

1. Then, follow the same procedures to create the **Geometrixx Clothes** security group.
1. Assign your security group to your user by selecting the **[!UICONTROL Users]** tab.

   ![](assets/manage_security_group_2.png)

1. Click your previously created user then the ![](assets/managing_security_group_10.png) icon in the **[!UICONTROL Products]** category.

   Select **[!UICONTROL Edit products assigned directly]** to start assigning new security group to your user.

   ![](assets/manage_security_group_8.png)

1. In the **[!UICONTROL Assign Products]** tab, select your instance then your previously created security groups Geometrixx from the drop-down list to assign it to your Administrator user.

   Click **[!UICONTROL Save]**.

   ![](assets/manage_security_group_3.png)

   Se um usuário estiver em vários grupos:

   * As funções dos diferentes grupos são acumuladas. Aqui, os usuários estão em dois grupos diferentes: uma que atuará sobre funções a outra em unidades.
   * It is the unit that is the highest in the hierarchy that will be used (see example in the [Organizational units](../../administration/using/organizational-units.md) section).
   * O usuário não poderá mais se conectar se as unidades tiverem o mesmo nível equivalente e estiverem em ramificações paralelas na hierarquia.

1. Siga os mesmos procedimentos para atribuir o grupo de segurança de Roupas do Geometrixx ao seu usuário padrão.

   ![](assets/manage_security_group_9.png)

Os grupos de segurança recém criados agora são criados no Admin Console. Para que sejam completamente sincronizados, você também precisa criá-los no Adobe Campaign.

O usuário do administrador deve criar o conjunto de grupos de segurança usados para atribuir unidades organizacionais: Geometrixx e Geometrixx Roupas. To learn how to create organizational units, see [Creating and managing units](../../administration/using/organizational-units.md#creating-and-managing-units) .

1. Click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner, then select **[!UICONTROL Administration > Users & Security > Security groups]**.
1. Create your new security group and specify its **[!UICONTROL Label]** and **[!UICONTROL ID]**.

   A ID precisa ser a mesma escolhida no Admin Console.

1. In the **[!UICONTROL User access]** field, assign organizational unit. Here, the Geometrixx security group is assigned the **[!UICONTROL All]** organizational unit.

   ![](assets/manage_security_group_6.png)

1. Você também pode atribuir funções ao seu grupo de segurança. In our case, this step is not needed since the out-of-the-box security groups **[!UICONTROL Administrators]** and **[!UICONTROL Standard users]** are used to assign roles.
1. Siga os mesmos procedimentos para criar a última segurança de Roupas Geometrixx e atribuir a unidade organizacional de Roupas do Geometrixx.

   ![](assets/manage_security_group_7.png)

Os usuários agora são atribuídos a um grupo de segurança e podem se conectar ao Adobe Campaign.

>[!CAUTION]
>
>Se os usuários forem removidos de um grupo de segurança no console de administração, eles permanecerão parte do grupo de segurança do Adobe Campaign e não poderão mais fazer logon no Adobe Campaign. Nesse caso, remova os endereços de email dos usuários no console de administração para impedir que eles recebam informações sigilosas.

