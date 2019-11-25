---
title: Criar perfis
description: Saiba como criar perfis e coletar dados em seus contatos, usando APIs, recursos de importação, aquisição online, atualizações automáticas ou manuais.
page-status-flag: never-activated
uuid: a5f5a58a-e798-400f-8648-05dc843d5557
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-profiles
discoiquuid: 4ab8a984-f898-4fff-ad8c-ed8f95362f96
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b06edadfa963881403328c4ab37d25d701bc8237

---


# Criar perfis{#creating-profiles}

No Adobe Campaign, os perfis são usados por padrão para definir o destino principal das mensagens.

Para criar ou atualizar um perfil no Campaign, você pode:

* Importar uma lista de perfis de um arquivo, por meio de um [fluxo de trabalho](https://helpx.adobe.com/campaign/kt/acs/using/acs-importing-profiles-feature-video-using.html)
* Coletar dados online, por meio de páginas [iniciais](../../channels/using/about-landing-pages.md)
* Criar massa por meio da API [REST](../../api/using/about-campaign-standard-apis.md)
* Sincronizar perfis do [Microsoft Dynamics](https://helpx.adobe.com/campaign/kb/acs-ms-dynamics.html)
* Insira os dados usando as telas de interface gráfica, como explicado abaixo

Por exemplo, para criar um novo perfil diretamente na interface do usuário, siga as etapas abaixo:

1. Na página inicial do Adobe Campaign, clique no cartão Perfis **do** cliente ou na guia **Perfis** para acessar a lista de perfis.

   ![](assets/profile_creation_1.png)

1. Em seguida, clique em **[!UICONTROL Create]**.

   ![](assets/profile_creation.png)

1. Insira os dados do perfil.

   ![](assets/profile_creation1.png)

   * As informações de contato, como nome, sobrenome, sexo, data de nascimento, foto, idioma preferencial (para emails [](../../channels/using/creating-a-multilingual-email.md)multilíngues), ajudam a personalizar melhor as entregas.
   * A do perfil **[!UICONTROL Time zone]** é usada para enviar entregas no fuso horário do perfil. Para obter mais informações, consulte esta [seção](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md).
   * A **[!UICONTROL Channels]** categoria, que contém o endereço de email, o número do telefone celular, as informações de não participação, permite saber em qual canal o perfil está acessível.
   * A **[!UICONTROL No longer contact]** categoria é atualizada assim que o perfil cancela a assinatura de um canal.
   * A **[!UICONTROL Address]** categoria contém o endereço postal que precisa ser preenchido junto com a **[!UICONTROL Address specified]** opção para enviar mala [](../../channels/using/about-direct-mail.md) direta para esse perfil. Se a **[!UICONTROL Address specified]** opção não estiver marcada, esse perfil será excluído de todas as entregas de mala direta.
   * A **[!UICONTROL Access authorization]** categoria indica as unidades organizacionais do perfil (para [gerenciar permissões](../../administration/using/about-access-management.md)). Consulte também Perfis [de](../../administration/using/organizational-units.md#partitioning-profiles)particionamento.
   * A **[!UICONTROL Traceability]** categoria atualiza automaticamente as informações referentes ao usuário que criou ou modificou o perfil.

1. Clique em **[!UICONTROL Create]** para salvar o perfil.

O perfil agora aparecerá na lista.

>[!NOTE]
>
>A criação de perfis também é possível usando a API do Adobe Campaign Standard. For more on this, refer to the [dedicated documentation](../../api/using/managing-profiles.md).

Os perfis também podem ser particionados dependendo de suas unidades organizacionais. Para adicionar os campos organizacionais aos seus perfis, consulte a seção Perfis [de](../../administration/using/organizational-units.md#partitioning-profiles) particionamento.

>[!NOTE]
>
>O campo de idioma preferencial é usado para selecionar o idioma ao enviar mensagens multilíngues. Para obter mais informações sobre as mensagens multilíngues, [consulte esta página](../../channels/using/creating-a-multilingual-email.md).

**Tópicos relacionados:**

* [Sobre páginas](../../channels/using/about-landing-pages.md) iniciais, guia passo a passo
* [Importação de perfis](https://helpx.adobe.com/campaign/kt/acs/using/acs-importing-profiles-feature-video-using.html)

