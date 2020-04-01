---
title: Criar perfis
description: Saiba como criar perfis e coletar dados em seus contatos, usando APIs, recursos de importação, aquisição on-line, atualizações automáticas ou manuais.
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
source-git-commit: a1bc9d23163d12517c4501a572fc92aac6aacbc6

---


# Criar perfis{#creating-profiles}

No Adobe Campaign, os perfis são usados por padrão para definir o público alvo principal das mensagens.

Para criar ou atualizar um perfil na Campanha, é possível:

* Importar uma lista de perfil de um arquivo, por meio de um [fluxo de trabalho](../../automating/using/importing-data.md#example--import-workflow-template)
* Coletar dados online, via [landing page](../../channels/using/getting-started-with-landing-pages.md)
* Criar massa por meio da API [REST](../../api/using/about-campaign-standard-apis.md)
* Sincronizar perfis do [Microsoft Dynamics](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md)
* Insira os dados usando as telas de interface gráfica, como explicado abaixo

Por exemplo, para criar um novo perfil diretamente na interface do usuário, siga as etapas abaixo:

1. No home page Adobe Campaign, clique na placa Perfis **do** cliente ou na guia **Perfis** para acessar a lista dos perfis.

   ![](assets/profile_creation_1.png)

1. Then click **[!UICONTROL Create]**.

   ![](assets/profile_creation.png)

1. Insira os dados do perfil.

   ![](assets/profile_creation1.png)

   * As informações de contato, como nome, sobrenome, gênero, data de nascimento, foto, idioma preferencial (para emails [](../../channels/using/creating-a-multilingual-email.md)multilíngues), ajudam a personalizar melhor os delivery.
   * O perfil **[!UICONTROL Time zone]** é usado para enviar delivery no fuso horário do perfil. Para obter mais informações, consulte esta [seção](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md).
   * A **[!UICONTROL Channels]** categoria, que contém o endereço de email, o número de telefone celular, as informações de não participação, informa sobre qual canal o perfil pode ser acessado.
   * A **[!UICONTROL No longer contact]** categoria é atualizada assim que o perfil cancela a inscrição em um canal.
   * A **[!UICONTROL Address]** categoria contém o endereço postal que precisa ser preenchido junto com a **[!UICONTROL Address specified]** opção de enviar o correio [](../../channels/using/about-direct-mail.md) direto para esse perfil. Se a **[!UICONTROL Address specified]** opção não estiver marcada, esse perfil será excluído de todos os delivery de mala direta.
   * A **[!UICONTROL Access authorization]** categoria indica as unidades organizacionais do perfil (para [gerenciar permissões](../../administration/using/about-access-management.md)). Consulte também [Particionamento de perfis](../../administration/using/organizational-units.md#partitioning-profiles).
   * A **[!UICONTROL Traceability]** categoria atualiza automaticamente as informações referentes ao usuário que criou ou modificou o perfil.

1. Clique em **[!UICONTROL Create]** para salvar o perfil.

O perfil agora será exibido na lista.

>[!NOTE]
>
>A criação de Perfil também é possível usando a API Adobe Campaign Standard. For more on this, refer to the [dedicated documentation](../../api/using/creating-profiles.md).

Os Perfis também podem ser particionados dependendo de suas unidades organizacionais. Para adicionar os campos organizacionais aos perfis, consulte a seção perfis [de](../../administration/using/organizational-units.md#partitioning-profiles) particionamento.

>[!NOTE]
>
>O campo de idioma preferencial é usado para selecionar o idioma ao enviar mensagens multilíngues. Para obter mais informações sobre as mensagens multilíngues, [consulte esta página](../../channels/using/creating-a-multilingual-email.md).

**Tópicos relacionados:**

* [Sobre o guia passo a passo do landing page](../../channels/using/getting-started-with-landing-pages.md)
* [Vídeo Importando perfis](https://video.tv.adobe.com/v/24993?captions=por_br)
