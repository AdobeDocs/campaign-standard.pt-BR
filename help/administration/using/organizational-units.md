---
title: Unidades organizacionais
seo-title: Unidades organizacionais
description: Unidades organizacionais
seo-description: Defina os níveis de acesso de seus usuários usando unidades organizacionais.
page-status-flag: nunca ativado
uuid: 8 c 82 ffea-cef 4-4 a 89-b 823-d 8 b 7 bae 1 db 4 f
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: usuários e segurança
discoiquuid: 6 f 60 c 653-1 d 12-4 d 27-9 bc 8-ce 8 c 19 bca 466
context-tags: Orgunit, overview; Orgunit, main; Geounit, overview; Geounit, main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a12df43de55dedf388a397fbf4670d99e3ea7f3d

---


# Organizational units{#organizational-units}

## About units {#about-units}

Cada objeto e usuário da plataforma está vinculado a uma unidade organizacional. Essa unidade permite que uma estrutura hierárquica seja definida para fornecer aos usuários uma visualização filtrada. A unidade de um usuário define seu nível de acesso para diferentes objetos de plataforma.

>[!CAUTION]
>
>Se um usuário não estiver vinculado a nenhuma unidade, ele não poderá se conectar ao Adobe Campaign. If you would like to restrict access for a particular user or group of users, do not link it to the **[!UICONTROL All]** unit.

Um usuário tem acesso somente leitura a todos os objetos nas unidades pai. Ele tem acesso de leitura e gravação a todos os objetos de unidades de unidade e filho. Um usuário não tem acesso a objetos em ramificações paralelas.

By default, only the **[!UICONTROL All]** units are available.

Quando o usuário recebe uma unidade organizacional, essa unidade sempre será aplicada aos objetos criados pelo usuário.

![](assets/user_management_2.png)

>[!NOTE]
>
>Quando um usuário está em vários grupos vinculados a unidades diferentes, algumas regras são aplicadas. For more information, refer to the [Managing groups and users](../../administration/using/managing-groups-and-users.md) section.

## Creating and managing units {#creating-and-managing-units}

As unidades organizacionais permitem filtrar sua instância dependendo da organização à qual os usuários estão vinculados. Essa unidade pode representar uma região, país ou até mesmo uma marca na sua instância.

Here, we previously created security groups with different roles to two users: one user is assigned the security groups Administrators and Geometrixx, the other user belongs to the security groups Standard user and Geometrixx Clothes See [Creating a security group and assigning users](../../administration/using/managing-groups-and-users.md#creating-a-security-group-and-assigning-users) for the full example.

Agora precisamos criar as unidades organizacionais para os grupos de segurança do Geometrixx Roupas e do Geometrixx:

1. From Adobe campaign advanced menu, select **[!UICONTROL Administration]** &gt; **[!UICONTROL Users & security]** &gt; **[!UICONTROL Organizational units]**.
1. Click **[!UICONTROL Create]** to start configuring your organizational unit.

   ![](assets/manage_units_1.png)

1. Change the default **[!UICONTROL Label]** and **[!UICONTROL ID]** to Geometrixx.
1. Em seguida, vincule essa unidade a uma unidade pai. Here, we chose **[!UICONTROL All]**.

   ![](assets/manage_units_2.png)

1. Finally, click **[!UICONTROL Create]** to start assigning your new organizational unit to security group.
1. Siga o mesmo procedimento para a unidade de Roupas do Geometrixx, exceto que sua unidade pai deve ser a unidade criada anteriormente, Geometrixx.

   ![](assets/manage_units_3.png)

Para visualizar o impacto da atribuição de unidades diferentes para grupos de segurança diferentes, o usuário atribuído aos grupos Administradores e Geometrixx criará dois modelos de e-mail para ver o que o outro usuário atribuído a Roupas padrão do usuário e o Geometrixx Roupas pode ou não ser acessado.

1. From the advanced menu, select **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Delivery Templates]**.
1. Duplique um modelo existente e personalize-o conforme necessário. For more on this, refer to the [About templates](../../start/using/about-templates.md) section.
1. When the template is created, select the **[!UICONTROL Edit properties]** icon to assign units to your template.

   ![](assets/manage_units_6.png)

1. In the **[!UICONTROL Access authorization]** drop down menu, select the organizational unit.

   Aqui, nós criamos um modelo com a unidade organizacional criada anteriormente Geometrixx.

   ![](assets/manage_units_5.png)

1. Siga os mesmos procedimentos para criar o segundo modelo atribuído à unidade organizacional de Roupas criada anteriormente do Geometrixx.

O usuário atribuído aos grupos de Roupas do usuário padrão e Geometrixx poderá ver ambos os modelos. Devido à estrutura hierárquica das unidades organizacionais, ele terá acesso de leitura e gravação ao modelo vinculado à unidade de Roupas do Geometrixx e somente leitura ao modelo vinculado à unidade do Geometrixx.

![](assets/manage_units_7.png)

Como a unidade de Roupas do Geometrixx é uma unidade secundária do Geometrixx, a seguinte mensagem é exibida quando o usuário tenta modificar o modelo Geometrixx:

![](assets/manage_units_8.png)

As unidades organizacionais podem restringir o acesso a diferentes recursos, como perfis. For example, if our Geometrixx Clothes user access the **[!UICONTROL Profiles]** tab, he will be able to fully access and modify the profiles with the Geometrixx Clothes organizational unit.

Whereas the profiles with the Geometrixx organizational unit will be read only, the following error will appear if our user tries to modify one profile: **[!UICONTROL You do not have the rights needed to modify the 'profile' resource of ID]**.

![](assets/manage_units_10.png)

## Partitioning profiles {#partitioning-profiles}

Se a sua empresa precisa isolar os perfis contados por cada uma das marcas diferentes, você pode dividir seus perfis por unidades organizacionais.

Por padrão, os campos de unidade organizacional não estão disponíveis em seus perfis e precisam ser adicionados.

Os perfis sem unidades organizacionais não podem ser acessados por usuários.

>[!CAUTION]
>
>Recomendamos adicionar essa opção antes de importar quaisquer perfis. Se você já tiver importado o banco de dados do cliente, uma atualização será necessária para definir os valores de unidade organizacional nos perfis já importados.

1. From the advanced menu, via the Adobe Campaign logo, select **Administration &gt; Development &gt; Custom resources**.
1. Select **Profile** or create a new custom resource to extend the profiles.
1. Check the **Add access authorization management fields** box to add the organizational units in the **Profile** extension.

   ![](assets/user_management_9.png)

1. Click **[!UICONTROL Save]**.
1. Atualize a estrutura republicar os recursos personalizados. For more information about the publication process, refer to [Updating the structure](../../developing/using/data-model-concepts.md) section.

The organizational unit field is added to your profiles in the **[!UICONTROL Access authorization]** section.

![](assets/user_management_10.png)

**Tópicos relacionados**:

* [Sobre unidades](../../administration/using/organizational-units.md#about-units)
* [Sobre o gerenciamento de acesso](../../administration/using/about-access-management.md)

