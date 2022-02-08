---
title: Unidades organizacionais
description: Defina os níveis de acesso dos usuários usando unidades organizacionais
audience: administration
feature: Access Management
role: Admin
level: Experienced
exl-id: fbab695a-2672-4183-8c3b-78af7aefd5b1
source-git-commit: bfba6b156d020e8d2656239e713d2d24625bda54
workflow-type: tm+mt
source-wordcount: '840'
ht-degree: 5%

---

# Unidades organizacionais{#organizational-units}

## Sobre unidades {#about-units}

Cada objeto e usuário da plataforma é vinculado a uma unidade organizacional. Essa unidade permite que uma estrutura hierárquica seja definida para fornecer aos usuários uma visualização filtrada. A unidade de um usuário define seu nível de acesso para diferentes objetos da plataforma.

>[!IMPORTANT]
>
>Se um usuário não estiver vinculado a nenhuma unidade, ele não poderá se conectar ao Adobe Campaign. Se você quiser restringir o acesso de um usuário ou grupo de usuários específico, não vincule-o à variável **[!UICONTROL All]** unidade. Recomendamos adicionar a opção **Acessar campos de gerenciamento de autorização** antes de importar perfis. Para obter mais informações, consulte esta [seção](../../administration/using/organizational-units.md#partitioning-profiles).
>
>Por padrão, a unidade organizacional **[!UICONTROL All (all)]** está atribuída ao grupo de segurança **[!UICONTROL Administrators]**. Ela é somente leitura e não pode ser modificada.

Um usuário tem acesso somente leitura a todos os objetos nas unidades pai. Esse usuário tem acesso de leitura e gravação a todos os objetos de sua unidade e unidades secundárias. Um usuário não tem acesso a objetos em ramificações paralelas.

Por padrão, somente a variável **[!UICONTROL All]** estão disponíveis.

Quando o usuário recebe uma unidade organizacional, essa unidade sempre será aplicada aos objetos criados pelo usuário.

![](assets/user_management_2.png)

>[!NOTE]
>
>Quando um usuário está em vários grupos vinculados a unidades diferentes, certas regras são aplicadas. Para obter mais informações, consulte [Gerenciamento de grupos e usuários](../../administration/using/managing-groups-and-users.md) seção.

## Criação e gerenciamento de unidades {#creating-and-managing-units}

As unidades organizacionais permitem filtrar a instância, dependendo da organização à qual os usuários estão vinculados. Essa unidade pode representar uma região, país ou até mesmo uma marca em sua instância.

Aqui, criamos previamente grupos de segurança com diferentes funções para dois usuários: um usuário recebe os grupos de segurança Administradores e Geometrixx, o outro usuário pertence aos grupos de segurança Usuário padrão e Geometrixx Clothes Consulte [Criação de um grupo de segurança e atribuição de usuários](../../administration/using/managing-groups-and-users.md#creating-a-security-group-and-assigning-users) para o exemplo completo.

Agora precisamos criar as unidades organizacionais para os grupos de segurança Geometrixx Clothes e Geometrixx:

1. No menu avançado da campanha do Adobe, selecione **[!UICONTROL Administration]** > **[!UICONTROL Users & security]** > **[!UICONTROL Organizational units]**.
1. Clique em **[!UICONTROL Create]** para começar a configurar sua unidade organizacional.

   ![](assets/manage_units_1.png)

1. Alterar o padrão **[!UICONTROL Label]** e **[!UICONTROL ID]** para o Geometrixx.
1. Em seguida, vincule essa unidade a uma unidade pai. Aqui, escolhemos **[!UICONTROL All]**.

   ![](assets/manage_units_2.png)

1. Finalmente, clique em **[!UICONTROL Create]** para começar a atribuir sua nova unidade organizacional ao grupo de segurança.
1. Siga o mesmo procedimento para a unidade Geometrixx Clothes, exceto que a unidade pai deve ser a unidade criada anteriormente, Geometrixx.

   ![](assets/manage_units_3.png)

Para ver o impacto da atribuição de unidades diferentes a grupos de segurança diferentes, o usuário atribuído aos grupos Administrador e Geometrixx criará dois modelos de email para ver o que o outro usuário atribuído ao Usuário padrão e à Geometrixx Clothes pode ou não acessar.

1. No menu avançado, selecione **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery Templates]**.
1. Duplique um template existente e personalize-o conforme necessário. Para obter mais informações, consulte a seção [Sobre templates](../../start/using/marketing-activity-templates.md)
1. Quando o modelo for criado, selecione o **[!UICONTROL Edit properties]** ícone para atribuir unidades ao modelo.

   ![](assets/manage_units_6.png)

1. No **[!UICONTROL Access authorization]** selecione a unidade organizacional no menu suspenso.

   Aqui vamos criar um modelo com o Geometrixx de unidade organizacional criado anteriormente.

   ![](assets/manage_units_5.png)

1. Siga os mesmos procedimentos para criar o segundo template atribuído à unidade organizacional Geometrixx Clothes criada anteriormente.

Usuários atribuídos ao **Usuário padrão** e **Geometrixx Clothes** os grupos poderão ver ambos os modelos. Devido à estrutura hierárquica das unidades organizacionais, elas terão acesso de leitura e gravação ao template vinculado à unidade Geometrixx Clothes e somente acesso de leitura ao template vinculado à unidade Geometrixx.

![](assets/manage_units_7.png)

Como a unidade Geometrixx Clothes é uma unidade filho do Geometrixx, a seguinte mensagem é exibida quando os usuários tentam modificar o template do Geometrixx:

![](assets/manage_units_8.png)

As unidades organizacionais podem restringir o acesso a diferentes recursos, como perfis. Por exemplo, se nossos usuários do Geometrixx Clothes acessarem o **[!UICONTROL Profiles]** , eles poderão acessar e modificar totalmente os perfis com a unidade organizacional Geometrixx Clothes .

Embora os perfis com a unidade organizacional do Geometrixx sejam somente leitura, o seguinte erro aparecerá se os usuários tentarem modificar um perfil: **[!UICONTROL You do not have the rights needed to modify the 'profile' resource of ID]**.

![](assets/manage_units_10.png)

## Particionamento de perfis {#partitioning-profiles}

>[!IMPORTANT]
>
>Recomendamos adicionar essa opção antes de importar qualquer perfil, pois os perfis sem unidades organizacionais não podem ser acessados pelos usuários.
>
>Se você já tiver importado o banco de dados do cliente, será necessária uma atualização para definir os valores da unidade organizacional nos perfis já importados.

Se sua organização precisar isolar os perfis contatados por cada uma de suas diferentes marcas, você poderá particionar seus perfis por suas unidades organizacionais.

Por padrão, os campos da unidade organizacional não estão disponíveis nos perfis e precisam ser adicionados.

1. No menu avançado, selecione pelo logotipo do Adobe Campaign **Administração > Desenvolvimento > Recursos personalizados**.
1. Selecionar **Perfil** ou criar um novo recurso personalizado para estender os perfis. Para obter mais informações sobre como estender os perfis, consulte esta seção [página](../../developing/using/extending-the-profile-resource-with-a-new-field.md#step-1--extend-the-profile-resource).
1. Verifique a **Adicionar campos de gerenciamento de autorização de acesso** para adicionar as unidades organizacionais no **Perfil** extensão.

   ![](assets/user_management_9.png)

1. Clique em **[!UICONTROL Save]**.
1. Atualize a estrutura publicando novamente os recursos personalizados. Para obter mais informações sobre o processo de publicação, consulte [Atualização da estrutura](../../developing/using/updating-the-database-structure.md) seção.

O campo da unidade organizacional é adicionado aos perfis na **[!UICONTROL Access authorization]** seção.

![](assets/user_management_10.png)

**Tópicos relacionados**:

* [Sobre unidades](../../administration/using/organizational-units.md#about-units)
* [Sobre gerenciamento de acesso](../../administration/using/about-access-management.md)
