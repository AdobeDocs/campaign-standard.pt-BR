---
title: Obter Acesso ao Aplicativo de Autoatendimento da Integração do Adobe Campaign Standard com o Dynamics 365
description: Integração do Adobe Campaign Standard com o aplicativo de autoatendimento do Dynamics 365
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
exl-id: 44b59f56-99be-41ae-af8d-76272bb94d18
source-git-commit: e7fdaa4b1d77afdae8004a88bbe41bbbe75a3f3c
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 1%

---

# Acessar a Integração do Adobe Campaign Standard com o Aplicativo de Autoatendimento do Microsoft Dynamics 365

Essa configuração exigirá que você trabalhe com um Administrador de Experience Cloud (EC) na sua organização. Essas são as etapas iniciais necessárias para fornecer acesso à interface do aplicativo de integração de autoatendimento. Depois de ter acesso à ferramenta, você definirá conexões com seus dados e configurará o fluxo de dados entre o Adobe Campaign e o Microsoft Dynamics 365.

>[!NOTE]
>
>Entre em contato com o representante de Adobe e forneça os nomes da organização e da instância da Adobe Campaign Standard. Um tíquete será registrado para solicitar que o aplicativo de integração seja habilitado para sua organização.

## Adicionar um perfil de produto

Nesta seção, você aprenderá a conceder acesso à integração do Adobe Campaign Standard com o aplicativo de autoatendimento do Microsoft Dynamics 365. Os usuários que têm acesso à sua organização no Adobe Experience Cloud não terão acesso ao aplicativo de autoatendimento de integração, a menos que você siga as etapas abaixo para conceder acesso a eles.

>[!IMPORTANT]
>
> Essas etapas exigem **Administrador** função no Experience Cloud da sua organização.
>

1. Navegue até https://experience.adobe.com/ e faça logon na Adobe Experience Cloud.
1. Acesse o **Admin Console**.

   ![](assets/do-not-localize/d365-to-acs-access-3.png)

1. Clique em **[!UICONTROL Products]** para acessar as soluções Experience Cloud.

   ![](assets/do-not-localize/d365-to-acs-access-6.png)


   >[!IMPORTANT]
   >
   >As etapas restantes nesta seção serão executadas para cada uma das instâncias do Campaign (desenvolvimento, texto, produção).
   >

1. Clique em na primeira instância a ser configurada.

   ![](assets/do-not-localize/d365-to-acs-access-6.png)

   A página da instância deve ser semelhante a:

   ![](assets/do-not-localize/d365-to-acs-access-8.png)

1. Clique em **[!UICONTROL New Profile]** e adicione uma nova entrada chamada: **Campaign Standard - your-prod-instance-name - Integração do D365/ACS**

   * Se você vir essa entrada na lista, não é necessário continuar. Clique em **Adobe Campaign Standard** no menu esquerdo e verifique as outras instâncias do Campaign.

   * Substitua &quot;your-prod-instance-name&quot; pelo nome real da sua instância.

1. Você pode deixar a variável **[!UICONTROL Permission Group]** com o valor padrão.

1. Se as entradas forem semelhantes às seguintes, clique no link **[!UICONTROL Done]** botão.

   ![](assets/do-not-localize/d365-to-acs-access-14.png)

   O novo perfil de produto foi adicionado.

   ![](assets/do-not-localize/d365-to-acs-access-15.png)

## Conceder acesso aos usuários {#add-users-to-profile}

No **[!UICONTROL Products]**  selecione a instância do Campaign e siga as etapas abaixo:

1. Clique no novo perfil criado anteriormente:  **Campaign Standard - your-prod-instance-name - Integração do D365/ACS**

   ![](assets/do-not-localize/d365-to-acs-access-15.png)

1. Clique na guia **[!UICONTROL Developers]**. 

   ![](assets/do-not-localize/d365-to-acs-access-18.png)

1. Clique no link **[!UICONTROL Add Developer]** botão

1. Insira o nome ou endereço de email do usuário que deseja adicionar.  Selecione o resultado que corresponde ao usuário.

   Se esta for a primeira vez que o usuário é adicionado à Organização, insira os detalhes.

1. Clique em **[!UICONTROL Save]** para confirmar.
