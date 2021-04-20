---
title: Obter acesso ao aplicativo de autoatendimento Adobe Campaign Standard Integration with Dynamics 365
description: Integração do Adobe Campaign Standard com o aplicativo de autoatendimento do Dynamics 365
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '417'
ht-degree: 1%

---


# Acesse a integração do Adobe Campaign Standard com o aplicativo de autoatendimento do Microsoft Dynamics 365

Essa configuração exigirá que você trabalhe com um Administrador do Experience Cloud (EC) para sua organização. Essas são as etapas iniciais necessárias para fornecer acesso à interface do aplicativo de integração de autoatendimento. Após ter acesso à ferramenta, você definirá as conexões com seus dados e configurará o fluxo de dados entre o Adobe Campaign e o Microsoft Dynamics 365.

>[!NOTE]
>
>É necessário entrar em contato com o representante do Adobe e fornecer os nomes de instância e organização da Adobe Campaign Standard. Um tíquete será registrado para solicitar que o aplicativo de integração seja ativado para sua organização.

## Adicionar um perfil de produto

Nesta seção, você aprenderá a conceder acesso à integração do Adobe Campaign Standard com o aplicativo de autoatendimento do Microsoft Dynamics 365. Os usuários que têm acesso à sua organização no Adobe Experience Cloud não terão acesso ao aplicativo de autoatendimento de integração, a menos que você siga as etapas abaixo para conceder acesso a eles.

>[!IMPORTANT]
>
> Essas etapas exigem a função **Administrador** no Experience Cloud para sua organização.


1. Navegue até https://experience.adobe.com/ e faça logon na Adobe Experience Cloud.
1. Acesse o **Admin Console**.

   ![](assets/do-not-localize/d365-to-acs-access-3.png)

1. Clique em **[!UICONTROL Products]** para acessar as soluções do Experience Cloud.

   ![](assets/do-not-localize/d365-to-acs-access-6.png)


   >[!IMPORTANT]
   >
   >As etapas restantes nesta seção serão executadas para cada uma das instâncias do Campaign (desenvolvimento, texto, produção).

1. Clique na primeira instância para configurar.

   ![](assets/do-not-localize/d365-to-acs-access-6.png)

   A página de instância deve ser semelhante a:

   ![](assets/do-not-localize/d365-to-acs-access-8.png)

1. Clique no botão **[!UICONTROL New Profile]** e adicione uma nova entrada chamada: **Campaign Standard - your-prod-instance-name - D365/ACS Integration**

   * Se você vir essa entrada na lista, não é necessário continuar. Clique em **Adobe Campaign Standard** no menu esquerdo e verifique as outras instâncias do Campaign.

   * Substitua &quot;your-prod-instance-name&quot; pelo nome real da sua instância.

1. Você pode deixar a lista suspensa **[!UICONTROL Permission Group]** com o valor padrão.

1. Se as entradas forem semelhantes ao seguinte, clique no botão **[!UICONTROL Done]**.

   ![](assets/do-not-localize/d365-to-acs-access-14.png)

   O novo perfil de produto foi adicionado.

   ![](assets/do-not-localize/d365-to-acs-access-15.png)

## Conceder acesso aos usuários {#add-users-to-profile}

Na página **[!UICONTROL Products]** , selecione a instância do Campaign e siga as etapas abaixo:

1. Clique no novo perfil que você criou anteriormente:  **Campaign Standard - your-prod-instance-name - D365/ACS Integration**

   ![](assets/do-not-localize/d365-to-acs-access-15.png)

1. Clique na guia **[!UICONTROL Developers]**. 

   ![](assets/do-not-localize/d365-to-acs-access-18.png)

1. Clique no botão **[!UICONTROL Add Developer]**

1. Insira o nome ou o endereço de email do usuário que deseja adicionar.  Selecione o resultado que corresponde ao usuário.

   Se esta for a primeira vez que o usuário é adicionado à Organização, insira os detalhes.

1. Clique em **[!UICONTROL Save]** para confirmar.
