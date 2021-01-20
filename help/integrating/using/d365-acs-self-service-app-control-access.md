---
title: Obtenha acesso à integração da Adobe Campaign Standard com o aplicativo de autoatendimento do Dynamics 365
description: Integração da Adobe Campaign Standard com o aplicativo de autoatendimento do Dynamics 365
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
translation-type: tm+mt
source-git-commit: cce30fd5cd3d5d63563d1dab3bb1e7554c26fb3e
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 1%

---


# Acesse a integração do Adobe Campaign Standard com o aplicativo de autoatendimento do Microsoft Dynamics 365

Essa configuração exigirá que você trabalhe com um Administrador de Experience Cloud (EC) para sua organização. Estas são as etapas iniciais necessárias para fornecer acesso à interface de aplicativo de integração de autoatendimento. Depois de ter acesso à ferramenta, você configurará as conexões com seus dados e configurará o fluxo de dados entre o Adobe Campaign e o Microsoft Dynamics 365.

>[!NOTE]
>
>É necessário entrar em contato com seu representante de Adobe e fornecer os nomes de organização e instância do Adobe Campaign Standard. Um ticket será registrado para solicitar que o aplicativo de integração seja ativado para sua organização.

## Adicionar um perfil de produto

Nesta seção, você aprenderá a conceder acesso à integração do Adobe Campaign Standard com o aplicativo de autoatendimento do Microsoft Dynamics 365. Os usuários que têm acesso à sua organização no Adobe Experience Cloud não terão acesso ao aplicativo de autoatendimento de integração, a menos que você siga as etapas abaixo para conceder acesso a eles.

>[!IMPORTANT]
>
> Essas etapas exigem a função **Administrador** no Experience Cloud para sua organização.


1. Navegue até https://experience.adobe.com/ e faça logon no Adobe Experience Cloud.
1. Acesse **Admin Console**.

   ![](assets/d365-to-acs-access-3.png)

1. Clique em **[!UICONTROL Products]** para acessar suas soluções Experience Cloud.

   ![](assets/d365-to-acs-access-6.png)


   >[!IMPORTANT]
   >
   >As etapas restantes nesta seção serão executadas para cada uma de suas instâncias de Campanha (dev, text, production).

1. Clique na primeira instância para configurar.

   ![](assets/d365-to-acs-access-6.png)

   A página de instância deve ser semelhante a:

   ![](assets/d365-to-acs-access-8.png)

1. Clique no botão **[!UICONTROL New Profile]** e adicione uma nova entrada chamada: **Campaign Standard - your-prod-instance-name - Integração entre D365/ACS**

   * Se vir essa entrada na lista, não é necessário continuar. Clique em **Adobe Campaign Standard** no menu esquerdo e verifique as outras instâncias de Campanha.

   * Certifique-se de substituir &quot;your-prod-instance-name&quot; pelo nome real da sua instância.

1. Você pode deixar a lista suspensa **[!UICONTROL Permission Group]** com o valor padrão.

1. Se as entradas forem semelhantes às seguintes, clique no botão **[!UICONTROL Done]**.

   ![](assets/d365-to-acs-access-14.png)

   O novo perfil de produto foi adicionado.

   ![](assets/d365-to-acs-access-15.png)

## Conceder acesso aos usuários {#add-users-to-profile}

Na página **[!UICONTROL Products]**, selecione a instância de Campanha e siga as etapas abaixo:

1. Clique no novo perfil criado anteriormente:  **Campaign Standard - your-prod-instance-name - Integração com D365/ACS**

   ![](assets/d365-to-acs-access-15.png)

1. Clique na guia **[!UICONTROL Developers]**. 

   ![](assets/d365-to-acs-access-18.png)

1. Clique no botão **[!UICONTROL Add Developer]**

1. Digite o nome ou endereço de email do usuário que deseja adicionar.  Selecione o resultado que corresponde ao usuário.

   Se esta for a primeira vez que o usuário for adicionado à Organização, insira os detalhes.

1. Clique em **[!UICONTROL Save]** para confirmar.
