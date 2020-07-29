---
title: Gerenciamento de grupos e usuários
description: Saiba como criar grupos de segurança e gerenciar usuários.
page-status-flag: never-activated
uuid: b3a3a2e3-9d69-4231-b724-8f37419f7a61
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: users-and-security
discoiquuid: 12f896ab-ee79-4d96-976d-cf34643491b4
context-tags: user,overview;user,main;security,overview;security,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 09a6e062be32b78fda6b0eb83a6d11ac249b3168
workflow-type: tm+mt
source-wordcount: '926'
ht-degree: 1%

---


# Gerenciamento de grupos e usuários{#managing-groups-and-users}

## Sobre grupos de segurança {#about-security-groups}

Os grupos de segurança são conjuntos de usuários que compartilham as mesmas funções e direitos em sua organização.

Os usuários devem estar sempre vinculados a um grupo de segurança. Isso permitirá que você atribua funções específicas e unidades organizacionais.

Para obter mais informações sobre funções, as tabelas na página a seguir apresentam as diferentes operações disponíveis de acordo com as funções de um usuário: [Autorizações](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf)de Adobe Campaign Standard.

Os grupos de segurança padrão são:

* **[!UICONTROL Administrators]**
* **[!UICONTROL Delivery supervisors]**
* **[!UICONTROL Message Center agents]**
* **[!UICONTROL Standard Users]**
* **[!UICONTROL Workflow supervisors]**

Se um usuário não estiver vinculado a nenhum grupo de segurança, ele não poderá acessar o Adobe Campaign.

Para restringir o acesso de um usuário, não o adicione ao grupo de usuários do Campaign Standard, pois ele está vinculado à unidade **[!UICONTROL All]** organizacional.

>[!NOTE]
>
>Por padrão, a unidade organizacional é atribuída ao grupo de **[!UICONTROL All (all)]** **[!UICONTROL Administrators]** segurança. É somente leitura e não pode ser modificada.

## Criação de um grupo de segurança e atribuição de usuários {#creating-a-security-group-and-assigning-users}

>[!IMPORTANT]
>
>Observe que no Admin Console, os grupos de segurança são chamados de perfis.

Você pode criar seus próprios grupos de segurança se os grupos predefinidos não forem suficientes para gerenciar seus usuários. Eles podem ser gerenciados por administradores que têm acesso aos menus de administração do Adobe Campaign e ao Admin Console. Para obter mais informações sobre o Admin Console, consulte esta [documentação](https://helpx.adobe.com/br/enterprise/managing/user-guide.html).

Aqui, primeiro precisamos atribuir os dois grupos predefinidos Usuário padrão e Administrador aos nossos usuários. Estes grupos de segurança irão restringir algumas funcionalidades do Adobe Campaign: o usuário padrão tem acesso básico ao Adobe Campaign, enquanto o administrador pode acessar os menus de administração, por exemplo.

Observe que quaisquer alterações feitas em grupos de segurança no Admin Console serão sincronizadas assim que os usuários fizerem logon no Adobe Campaign.

Em seguida, queremos criar um conjunto de grupos de segurança, Geometrixx e roupas de Geometrixx, que restringirão algum acesso, dependendo das unidades organizacionais do usuário e do administrador do Standard.

![](assets/ootb_security_group_1.png)

Primeiro, é necessário atribuir um dos grupos de segurança prontos para uso aos usuários:

1. No Admin Console, selecione sua instância e, em seguida, a guia **Usuários** .

   ![](assets/manage_security_group_2.png)

1. Clique no **[!UICONTROL Add user]** botão e insira o endereço de email do usuário.
1. Na **[!UICONTROL Assign Products]** guia, selecione a instância e, em seguida, o grupo de segurança **[!UICONTROL Administrators]** pronto para uso na lista suspensa. Isso permitirá que o usuário tenha acesso aos menus de administração e crie os próximos grupos de segurança.

   ![](assets/ootb_security_group_2.png)

1. Clique **[!UICONTROL Save]** e siga os mesmos procedimentos para atribuir o grupo de segurança **[!UICONTROL Standard Users]** pronto para usar ao seu novo usuário.

   ![](assets/ootb_security_group_3.png)

Assim que os dois usuários estiverem conectados aos grupos de segurança **[!UICONTROL Administrators]** e prontos para uso **[!UICONTROL Standard users]** que atribuírem funções aos nossos usuários, o usuário Administrador poderá criar os dois grupos de segurança **Geometrixx** e **Roupas** de Geometrixx que atribuirão unidades organizacionais aos nossos usuários, além dos grupos de segurança predefinidos.

1. No Admin Console, selecione a instância e, em seguida, a guia **Produtos** .
1. Clique no botão **Novo Perfil** para criar o grupo de segurança do **Geometrixx** .

   ![](assets/create_security_1.png)

1. Digite a sintaxe **[!UICONTROL Profile name]** a seguir: **[!UICONTROL Campaign Standard- instance name - ID of the security group]** e clique em **[!UICONTROL Done]**.

   A ID escolhida será usada ao criar o grupo de segurança no Adobe Campaign.

   >[!NOTE]
   >
   >Se a sintaxe acima não parecer funcionar com uma instância mais antiga, ela precisa ser substituída por **[!UICONTROL Campaign - instance name - ID of the security group]**.

   ![](assets/manage_security_group_1.png)

1. Em seguida, siga os mesmos procedimentos para criar o grupo de segurança **Roupas** de Geometrixx.
1. Atribua seu grupo de segurança ao usuário selecionando a **[!UICONTROL Users]** guia.

   ![](assets/manage_security_group_2.png)

1. Clique no usuário criado anteriormente e no ![](assets/managing_security_group_10.png) ícone na **[!UICONTROL Products]** categoria.

   Selecione **[!UICONTROL Edit products assigned directly]** a opção start atribuindo novo grupo de segurança ao usuário.

   ![](assets/manage_security_group_8.png)

1. Na **[!UICONTROL Assign Products]** guia, selecione a instância e, em seguida, a Geometrixx de grupos de segurança criados anteriormente na lista suspensa para atribuí-la ao usuário Administrador.

   Clique em **[!UICONTROL Save]**.

   ![](assets/manage_security_group_3.png)

   Se um usuário estiver em vários grupos:

   * As funções dos diferentes grupos são acumuladas. Aqui, os usuários estão em dois grupos diferentes: uma que atuará em função da outra em unidades.
   * É a unidade mais alta da hierarquia que será usada (consulte o exemplo na seção Unidades [](../../administration/using/organizational-units.md) organizacionais).
   * O usuário não poderá mais se conectar se as unidades tiverem o mesmo nível equivalente e estiverem em ramificações paralelas na hierarquia.

1. Siga os mesmos procedimentos para atribuir o grupo de segurança Roupas de Geometrixx ao usuário do Standard.

   ![](assets/manage_security_group_9.png)

Os grupos de segurança criados recentemente são criados no Admin Console. Para que eles sejam completamente sincronizados, você também precisa criá-los no Adobe Campaign.

O usuário Administrador precisa criar o conjunto de grupos de segurança que são usados para atribuir unidades organizacionais: Geometrixx e roupa de Geometrixx. Para saber como criar unidades organizacionais, consulte [Criação e gerenciamento de unidades](../../administration/using/organizational-units.md#creating-and-managing-units) .

1. Clique no **[!UICONTROL Adobe Campaign]** logotipo, no canto superior esquerdo e selecione **[!UICONTROL Administration > Users & Security > Security groups]**.
1. Crie seu novo grupo de segurança e especifique seu **[!UICONTROL Label]** e **[!UICONTROL ID]**.

   A ID precisa ser a mesma escolhida no Admin Console.

1. No **[!UICONTROL User access]** campo, atribua a unidade organizacional. Aqui, o grupo de segurança do Geometrixx recebe a unidade organizacional. **[!UICONTROL All]**

   >[!NOTE]
   >
   >Se estiver atribuindo um grupo de segurança pronto para uso aos usuários, será necessário redefinir a unidade organizacional.

   ![](assets/manage_security_group_6.png)

1. Você também pode atribuir funções ao seu grupo de segurança. Em nosso caso, essa etapa não é necessária, pois os grupos de segurança predefinidos **[!UICONTROL Administrators]** e **[!UICONTROL Standard users]** são usados para atribuir funções.
1. Siga os mesmos procedimentos para criar as últimas Roupas de segurança e atribuir a unidade organizacional Roupas de Geometrixx.

   ![](assets/manage_security_group_7.png)

Seus usuários agora estão atribuídos a um grupo de segurança e podem se conectar ao Adobe Campaign.

>[!IMPORTANT]
>
>Se os usuários forem removidos de um grupo de segurança no Admin Console, eles continuarão fazendo parte do grupo de segurança do Adobe Campaign e não poderão mais fazer logon no Adobe Campaign. Nesse caso, remova os endereços de email dos usuários no Admin Console para impedir que eles recebam informações confidenciais.

