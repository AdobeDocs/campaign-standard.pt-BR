---
solution: Campaign Standard
product: campaign
title: Gerenciamento de grupos e usuários
description: Saiba como criar grupos de segurança e gerenciar usuários.
audience: administration
content-type: reference
topic-tags: users-and-security
context-tags: user,overview;user,main;security,overview;security,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '926'
ht-degree: 97%

---


# Gerenciamento de grupos e usuários{#managing-groups-and-users}

## Sobre grupos de segurança {#about-security-groups}

Os grupos de segurança são conjuntos de usuários que compartilham as mesmas funções e direitos na organização.

Os usuários devem estar sempre vinculados a um grupo de segurança. Assim, você poderá atribuir funções específicas e unidades organizacionais a eles.

Para saber mais sobre funções, as tabelas na página a seguir apresentam as diferentes operações disponíveis de acordo com as funções de um usuário: autorizações do [Adobe Campaign Standard](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf).

Os grupos de segurança padrão são:

* **[!UICONTROL Administrators]**
* **[!UICONTROL Delivery supervisors]**
* **[!UICONTROL Message Center agents]**
* **[!UICONTROL Standard Users]**
* **[!UICONTROL Workflow supervisors]**

Se um usuário não estiver vinculado a nenhum grupo de segurança, ele não poderá acessar o Adobe Campaign.

Para restringir o acesso de um usuário, não o adicione ao grupo de usuários do Campaign Standard, pois ele está vinculado à unidade organizacional **[!UICONTROL All]**.

>[!NOTE]
>
>Por padrão, a unidade organizacional **[!UICONTROL All (all)]** está atribuída ao grupo de segurança **[!UICONTROL Administrators]**. Ela é somente leitura e não pode ser modificada.

## Criação de um grupo de segurança e atribuição de usuários {#creating-a-security-group-and-assigning-users}

>[!IMPORTANT]
>
>Observe que, no Admin Console, os grupos de segurança são chamados de perfis.

Você poderá criar grupos de segurança se os grupos predefinidos não forem suficientes para gerenciar seus usuários. Eles poderão ser gerenciados pelos administradores que têm acesso aos menus de administração do Adobe Campaign e ao Admin Console. Para saber mais sobre o Admin Console, consulte esta [documentação](https://helpx.adobe.com/br/enterprise/managing/user-guide.html).

Aqui, precisamos primeiro atribuir os dois grupos predefinidos Usuário padrão e Administrador aos nossos usuários. Esses grupos de segurança restringirão algumas funcionalidades do Adobe Campaign: o Usuário padrão tem acesso básico ao Adobe Campaign, enquanto o Administrador pode acessar os menus de administração, por exemplo.

Observe que qualquer alteração nos grupos de segurança no Admin Console será sincronizada assim que os usuários fizerem logon no Adobe Campaign.

Em seguida, criaremos um conjunto de grupos de segurança Geometrixx e Geometrixx Clothes que restringirão alguns acessos, dependendo das unidades organizacionais do nosso Usuário padrão e Administrador.

![](assets/ootb_security_group_1.png)

Primeiro, é necessário atribuir um dos grupos de segurança predefinidos aos usuários:

1. No Admin Console, selecione sua instância e, em seguida, a guia **Users**.

   ![](assets/manage_security_group_2.png)

1. Clique no botão **[!UICONTROL Add user]** e insira o endereço de email do usuário.
1. Na guia **[!UICONTROL Assign Products]**, selecione a instância e, em seguida, o grupo de segurança predefinido **[!UICONTROL Administrators]** na lista suspensa. Isso permitirá que o usuário tenha acesso aos menus de administração e crie os próximos grupos de segurança.

   ![](assets/ootb_security_group_2.png)

1. Clique em **[!UICONTROL Save]** e siga os mesmos procedimentos para atribuir o grupo de segurança predefinido **[!UICONTROL Standard Users]** ao novo usuário.

   ![](assets/ootb_security_group_3.png)

Assim que os dois usuários estiverem conectados aos grupos de segurança predefinidos **[!UICONTROL Administrators]** e **[!UICONTROL Standard users]** que atribuirão funções aos nossos usuários, o usuário Administrador poderá criar os dois grupos de segurança **Geometrixx** e **Geometrixx Clothes** que atribuirão unidades organizacionais aos usuários, além dos grupos de segurança predefinidos.

1. No Admin Console, selecione a instância e, em seguida, a guia **Products**.
1. Clique no botão **Novo perfil** para criar o grupo de segurança **Geometrixx**.

   ![](assets/create_security_1.png)

1. Digite o **[!UICONTROL Profile name]** seguindo esta sintaxe exata: **[!UICONTROL Campaign Standard- instance name - ID of the security group]** e clique em **[!UICONTROL Done]**.

   A ID escolhida será usada ao criar o grupo de segurança no Adobe Campaign.

   >[!NOTE]
   >
   >Se a sintaxe acima aparentemente não estiver funcionando com uma instância mais antiga, ela precisará ser substituída por **[!UICONTROL Campaign - instance name - ID of the security group]**.

   ![](assets/manage_security_group_1.png)

1. Em seguida, siga os mesmos procedimentos para criar o grupo de segurança **Geometrixx Clothes**.
1. Atribua o grupo de segurança ao usuário selecionando a guia **[!UICONTROL Users]**.

   ![](assets/manage_security_group_2.png)

1. Clique no usuário criado anteriormente e no ícone ![](assets/managing_security_group_10.png)na categoria **[!UICONTROL Products]**.

   Selecione **[!UICONTROL Edit products assigned directly]** para começar a atribuir o novo grupo de segurança ao usuário.

   ![](assets/manage_security_group_8.png)

1. Na guia **[!UICONTROL Assign Products]**, selecione a instância e, na lista suspensa, escolha os grupos de segurança criados anteriormente pelo Geometrixx para atribuí-la ao usuário Administrador.

   Clique em **[!UICONTROL Save]**.

   ![](assets/manage_security_group_3.png)

   Se um usuário estiver em vários grupos:

   * As funções dos diferentes grupos são acumuladas. Aqui, os usuários estão em dois grupos diferentes: um que atuará em funções, e o outro, em unidades.
   * A unidade mais alta na hierarquia será usada (veja o exemplo na seção [Unidades organizacionais](../../administration/using/organizational-units.md)).
   * O usuário não poderá mais se conectar se as unidades tiverem o mesmo nível equivalente e estiverem em ramificações paralelas na hierarquia.

1. Siga os mesmos procedimentos para atribuir o grupo de segurança Geometrixx Clothes ao Usuário padrão.

   ![](assets/manage_security_group_9.png)

Os grupos de segurança recém-criados agora estão criados no Admin Console. Para que eles sejam completamente sincronizados, você também precisa criá-los no Adobe Campaign.

O usuário Administrador precisa criar o conjunto de grupos de segurança que são usados para atribuir as unidades organizacionais Geometrixx e Geometrixx Clothes. Para saber como criar unidades organizacionais, consulte [Criação e gerenciamento de unidades](../../administration/using/organizational-units.md#creating-and-managing-units).

1. Clique no logotipo do **[!UICONTROL Adobe Campaign]**, no canto superior esquerdo e selecione **[!UICONTROL Administration > Users & Security > Security groups]**.
1. Crie o novo grupo de segurança e especifique o **[!UICONTROL Label]** e a **[!UICONTROL ID]**.

   A ID precisa ser a mesma escolhida no Admin Console.

1. No campo **[!UICONTROL User access]**, atribua a unidade organizacional. Aqui, a unidade organizacional **[!UICONTROL All]** é atribuída ao grupo de segurança Geometrixx.

   >[!NOTE]
   >
   >Se estiver atribuindo um grupo de segurança pronto para uso aos usuários, será necessário redefinir a unidade organizacional.

   ![](assets/manage_security_group_6.png)

1. Você também pode atribuir funções ao seu grupo de segurança. No nosso caso, essa etapa não é necessária, pois os grupos de segurança predefinidos **[!UICONTROL Administrators]** e **[!UICONTROL Standard users]** são usados para atribuir funções.
1. Siga os mesmos procedimentos para criar a última segurança Geometrixx Clothes e atribuir a unidade organizacional Geometrixx Clothes.

   ![](assets/manage_security_group_7.png)

Seus usuários agora estão atribuídos a um grupo de segurança e podem se conectar ao Adobe Campaign.

>[!IMPORTANT]
>
>Se os usuários forem removidos de um grupo de segurança no Admin Console, eles continuarão fazendo parte do grupo de segurança do Adobe Campaign e não poderão mais fazer logon no Adobe Campaign. Nesse caso, remova os endereços de email dos usuários no Admin Console para impedir que eles recebam informações confidenciais.

