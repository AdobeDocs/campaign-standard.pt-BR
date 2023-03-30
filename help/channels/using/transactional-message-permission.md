---
title: Permissão de mensagens transacionais
description: Saiba mais sobre permissões vinculadas a eventos transacionais.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
hide: true
hidefromtoc: true
feature: Transactional Messaging
role: User
level: Intermediate
source-git-commit: d7e0912dd7d19a1f5dd2172235f28a40e130cac1
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 0%

---

# Permissão de mensagens transacionais {#transactional-message-permission}

Atualmente, no Adobe Campaign Standard, os usuários sem o grupo de segurança Administrador não podem acessar, criar ou publicar eventos, causando problemas para os usuários corporativos que precisam configurar e publicar eventos, mas não têm direitos de Administrador.

Implementamos as seguintes melhorias no controle de acesso de mensagens transacionais:

* Um novo **[!UICONTROL Role]**, chamada **Usuário do MC**, foi adicionado para permitir que usuários não administradores gerenciem eventos transacionais. O **Usuário do MC** concede a esses usuários a capacidade de acessar, criar, publicar e cancelar a publicação de eventos e mensagens transacionais.

* Os deliveries secundários agora são definidos como **[!UICONTROL Organizational unit]** do grupo de segurança ao qual o usuário que está criando o modelo de mensagem pertence, em vez de ser restrito ao **[!UICONTROL Organizational unit]** do **Agente do Centro de Mensagens (mcExec)** grupo de segurança.

* O padrão **Execução do Centro de Mensagens (mcExec)** a campanha, que reúne as mensagens transacionais e deliveries filho, agora está definida para a unidade organizacional **Todos** permitindo que todos os usuários visualizem relatórios de entregas secundárias.

Para atribuir a variável **Usuário do MC** função:

1. Crie um novo **[!UICONTROL Security group]** ou atualizar um existente. [Saiba mais](../../administration/using/managing-groups-and-users.md).

1. Clique em **[!UICONTROL Create element]** para atribuir funções ao seu grupo de segurança.

   ![](assets/event_access_1.png)

1. Selecione o usuário MC **[!UICONTROL Role]** e clique em **[!UICONTROL Confirm]**.

   >[!IMPORTANT]
   >
   > Continue com cautela ao atribuir a função Usuário do MC aos operadores, pois isso lhes concede a capacidade de cancelar a publicação de eventos.

   ![](assets/event_access_2.png)

1. Depois de configurado, clique em **[!UICONTROL Save]**.

Usuários vinculados a este **[!UICONTROL Security group]** Agora o pode acessar, criar e publicar eventos e mensagens transacionais.

A tabela abaixo descreve o impacto desse recurso no controle de acesso:

| Objetos | Antes desta alteração | Após esta alteração |
|:-: | :--: | :-:|
| Campanha de Execução do Centro de Mensagens (mcExec) | **Execução do Centro de Mensagens (mcExec)** a campanha é definida como a unidade organizacional da **Agente do Centro de Mensagens (mcExec)** grupo de segurança. | **Execução do Centro de Mensagens (mcExec)** campanha é definida como Unidade organizacional **Todos** para permitir que todos os deliveries secundários sejam associados a esta campanha.</br> Todos os usuários poderão visualizar relatórios dos deliveries secundários, mas terão somente acesso de leitura ao conteúdo do delivery. |
| Deliveries Secundários | Os deliveries secundários são definidos como **Unidade organizacional** do **Agente do Centro de Mensagens (mcExec)** grupo de segurança. | Os deliveries secundários serão definidos como **Unidade organizacional** do grupo de segurança ao qual o usuário que está criando o template de mensagem pertence. |
| Modelo de mensagem | Os Modelos de mensagem são definidos como **Unidade organizacional** do **Agente do Centro de Mensagens (mcExec)** grupo de segurança. | Os Modelos de mensagem serão definidos como **Unidade organizacional** do grupo de segurança ao qual o usuário que está criando o template de mensagem pertence. |
| Eventos transacionais | Somente usuários na **Administrador** grupo de segurança pode criar e publicar eventos. | O **Usuário do MC** permite que os usuários criem e publiquem eventos. |
| Modelos de Mensagens Transacionais | Os templates de Mensagens transacionais são definidos como a unidade organizacional **Todos**. | O Modelo de Mensagem de Transação será definido como **Unidade organizacional** do grupo de segurança ao qual o usuário que está criando o template de mensagem pertence. |