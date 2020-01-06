---
title: Unidades organizacionais
description: Defina os níveis de acesso dos usuários usando unidades organizacionais.
page-status-flag: never-activated
uuid: 8c82ffea-cef4-4a89-b823-d8b7bae1db4f
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: users-and-security
discoiquuid: 6f60c653-1d12-4d27-9bc8-ce8c19bca466
context-tags: orgUnit,overview;orgUnit,main;geoUnit,overview;geoUnit,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c26f98c8edd832beeedfedafb8ad27730cc30d25

---


# Unidades organizacionais{#organizational-units}

## Sobre unidades {#about-units}

Cada objeto e usuário da plataforma está vinculado a uma unidade organizacional. Essa unidade permite que uma estrutura hierárquica seja definida para dar aos usuários uma exibição filtrada. Uma unidade do usuário define seu nível de acesso para diferentes objetos da plataforma.

>[!CAUTION]
>
>Se um usuário não estiver vinculado a nenhuma unidade, ele não poderá se conectar ao Adobe Campaign. Se você deseja restringir o acesso de um usuário ou grupo de usuários específico, não vincule-o à **[!UICONTROL All]**unidade.

Um usuário tem acesso somente leitura a todos os objetos nas unidades pai. Ele tem acesso de leitura e gravação a todos os objetos de sua unidade e unidades filhas. Um usuário não tem acesso a objetos em ramificações paralelas.

Por padrão, somente as **[!UICONTROL All]**unidades estão disponíveis.

Quando o usuário recebe uma unidade organizacional, essa unidade sempre será aplicada aos objetos criados pelo usuário.

![](assets/user_management_2.png)

>[!NOTE]
>
>Quando um usuário está em vários grupos vinculados a unidades diferentes, determinadas regras são aplicadas. Para obter mais informações, consulte a seção [Gerenciar grupos e usuários](../../administration/using/managing-groups-and-users.md) .

## Criação e gerenciamento de unidades {#creating-and-managing-units}

As unidades organizacionais permitem que você filtre sua instância dependendo da organização à qual seus usuários estão vinculados. Essa unidade pode representar uma região, país ou até mesmo uma marca em seu caso.

Aqui, criamos anteriormente grupos de segurança com funções diferentes para dois usuários: um usuário recebe os grupos de segurança Administradores e Geometrixx, o outro usuário pertence aos grupos de segurança Usuário padrão e Roupas Geometrixx Consulte [Criar um grupo de segurança e atribuir usuários](../../administration/using/managing-groups-and-users.md#creating-a-security-group-and-assigning-users) ao exemplo completo.

Agora precisamos criar as unidades organizacionais para os grupos de segurança Geometrixx Clothes e Geometrixx:

1. No menu avançado da campanha Adobe, selecione **[!UICONTROL Administration]**>**[!UICONTROL Users & security]** > **[!UICONTROL Organizational units]**.
1. Clique **[!UICONTROL Create]**para iniciar a configuração da unidade organizacional.

   ![](assets/manage_units_1.png)

1. Altere o padrão **[!UICONTROL Label]**e**[!UICONTROL ID]** para Geometrixx.
1. Em seguida, vincule essa unidade a uma unidade pai. Aqui, escolhemos **[!UICONTROL All]**.

   ![](assets/manage_units_2.png)

1. Por fim, clique em **[!UICONTROL Create]**para começar a atribuir sua nova unidade organizacional ao grupo de segurança.
1. Siga o mesmo procedimento para a unidade de roupas Geometrixx, exceto que a unidade pai deve ser a unidade criada anteriormente, Geometrixx.

   ![](assets/manage_units_3.png)

Para ver o impacto da atribuição de unidades diferentes a grupos de segurança diferentes, o usuário atribuído aos grupos Administrador e Geometrixx criará dois modelos de email para ver o que o outro usuário atribuído às Roupas Padrão do Usuário e Geometrixx pode ou não acessar.

1. No menu avançado, selecione **[!UICONTROL Resources]**>**[!UICONTROL Templates]** > **[!UICONTROL Delivery Templates]**.
1. Duplique um modelo existente e personalize-o conforme necessário. For more on this, refer to the [About templates](../../start/using/marketing-activity-templates.md) section.
1. Quando o modelo for criado, selecione o **[!UICONTROL Edit properties]**ícone para atribuir unidades ao modelo.

   ![](assets/manage_units_6.png)

1. No menu **[!UICONTROL Access authorization]**suspenso, selecione a unidade organizacional.

   Aqui vamos criar um modelo com a unidade organizacional previamente criada Geometrixx.

   ![](assets/manage_units_5.png)

1. Siga os mesmos procedimentos para criar o segundo modelo atribuído à unidade organizacional de Roupas Geometrixx criada anteriormente.

O usuário atribuído aos grupos Usuário padrão e Roupas Geometrixx poderá ver ambos os modelos. Devido à estrutura hierárquica das unidades organizacionais, terá acesso de leitura e gravação ao modelo ligado à unidade de Roupas Geometrixx e apenas acesso só de leitura ao modelo ligado à unidade Geometrixx.

![](assets/manage_units_7.png)

Como a unidade de roupas Geometrixx é uma unidade secundária do Geometrixx, a seguinte mensagem é exibida quando o usuário tenta modificar o modelo do Geometrixx:

![](assets/manage_units_8.png)

As unidades organizacionais podem restringir o acesso a diferentes recursos, como perfis. Por exemplo, se nosso usuário do Geometrixx Clothes acessar a guia, ele poderá acessar e modificar completamente os perfis com a unidade organizacional do Geometrixx Clothes **[!UICONTROL Profiles]**.

Enquanto os perfis com a unidade organizacional Geometrixx serão somente leitura, o seguinte erro aparecerá se o usuário tentar modificar um perfil: **[!UICONTROL You do not have the rights needed to modify the 'profile' resource of ID]**.

![](assets/manage_units_10.png)

## Perfis de particionamento {#partitioning-profiles}

Se sua organização precisar isolar os perfis contatados por cada uma de suas marcas diferentes, você poderá particionar seus perfis pelas unidades organizacionais.

Por padrão, os campos da unidade organizacional não estão disponíveis em seus perfis e precisam ser adicionados.

Os perfis sem unidades organizacionais não podem ser acessados pelos usuários.

>[!CAUTION]
>
>Recomendamos adicionar essa opção antes de importar qualquer perfil. Se você já tiver importado o banco de dados do cliente, será necessária uma atualização para definir os valores da unidade organizacional nos Perfis já importados.

1. No menu avançado, pelo logotipo do Adobe Campaign, selecione **Administração > Desenvolvimento > Recursos** personalizados.
1. Selecione **Perfil** ou crie um novo recurso personalizado para estender os perfis.
1. Marque a caixa **Adicionar campos** de gerenciamento de autorização de acesso para adicionar as unidades organizacionais na extensão **Perfil** .

   ![](assets/user_management_9.png)

1. Clique em **[!UICONTROL Save]**.
1. Atualize a estrutura republicando os recursos personalizados. Para obter mais informações sobre o processo de publicação, consulte a seção [Atualização da estrutura](../../developing/using/data-model-concepts.md) .

O campo da unidade organizacional é adicionado aos seus perfis na **[!UICONTROL Access authorization]**seção.

![](assets/user_management_10.png)

**Tópicos relacionados**:

* [Sobre unidades](../../administration/using/organizational-units.md#about-units)
* [Sobre o gerenciamento de acesso](../../administration/using/about-access-management.md)

