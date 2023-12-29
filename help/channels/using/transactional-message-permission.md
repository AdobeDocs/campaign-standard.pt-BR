---
title: Permissão de mensagens transacionais
description: Saiba mais sobre permissões vinculadas a eventos transacionais.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: User
level: Intermediate
exl-id: 995da330-6c86-444b-86b2-61d887f37db4
source-git-commit: 7247fe596494690ac0676196fbb72c6139aeb0c7
workflow-type: tm+mt
source-wordcount: '797'
ht-degree: 1%

---

# Melhorias no evento transacional {#transactional-event-improvements}

>[!AVAILABILITY]
>
>No momento, esses recursos estão disponíveis apenas para algumas organizações (disponibilidade limitada). Para mais informações, entre em contato com o seu representante da Adobe.

Atualmente, no Adobe Campaign Standard, os usuários sem o grupo de segurança Administrador não podem acessar, criar ou publicar eventos transacionais, causando problemas para usuários empresariais que precisam configurar e publicar eventos, mas não têm direitos de Administrador. Além disso, não é possível duplicar eventos transacionais.

Implementamos as seguintes melhorias no controle de acesso de mensagens transacionais:

* Um novo **[!UICONTROL Role]**, chamado **Usuário MC**, foi adicionado para permitir que usuários não administradores gerenciem a configuração de eventos transacionais. A variável **Usuário MC** A função concede a esses usuários a capacidade de acessar, criar, publicar e cancelar a publicação de eventos transacionais e mensagens.

* Os deliveries de execução (ou seja, mensagens técnicas que são criadas sempre que uma mensagem transacional é editada e publicada novamente, ou uma vez por mês por padrão) agora são definidos como **[!UICONTROL Organizational unit]** do grupo de segurança ao qual o usuário que está criando o evento pertence, em vez de ficar restrito ao **[!UICONTROL Organizational unit]** do **Agente do Centro de mensagens (mcExec)** grupo de segurança.

* **Administradores** agora podem duplicar eventos transacionais publicados, bem como usuários com a **Usuário MC** desde que estejam na mesma **Unidade organizacional** hierarquia como o usuário que criou o evento.

## Atribuir a função de usuário MC {#assign-role}

Para atribuir a variável **Usuário MC** para o seu grupo de segurança:

1. Criar um novo **[!UICONTROL Security group]** ou atualizar um existente. [Saiba mais](../../administration/using/managing-groups-and-users.md).

1. Clique em **[!UICONTROL Create element]** para atribuir funções ao seu grupo de segurança.

   ![](assets/event_access_1.png)

1. Selecione o usuário MC **[!UICONTROL Role]** e clique em **[!UICONTROL Confirm]**.

   >[!IMPORTANT]
   >
   > Continue com cuidado ao atribuir a função Usuário da MC aos operadores, pois isso lhes concede a capacidade de cancelar a publicação de eventos.

   ![](assets/event_access_2.png)

1. Após a configuração, clique em **[!UICONTROL Save]**.

Usuários vinculados a este **[!UICONTROL Security group]** O agora pode acessar, criar e publicar eventos transacionais e mensagens.

## Atribuir o grupo de segurança de usuário MC {#assign-group}

1. No Admin Console, selecione a variável **Produtos** guia.

1. Selecionar **Adobe Campaign Standard** em seguida, escolha a instância.

1. No **Perfis de produto** , selecione a **Usuário MC** grupo.

1. Clique em **Adicionar usuário** e digite o nome, grupo de usuários ou endereço de email do perfil que deseja adicionar a esse perfil de produto.

1. Depois de adicionado, clique em **Salvar**.

Usuários adicionados a este **[!UICONTROL Security group]** O agora pode acessar, criar e publicar eventos transacionais e mensagens.

## Eventos transacionais duplicados {#duplicate-transactional-events}

Um usuário com a variável **Administrador** grupo de segurança<!--([Functional administrators](../../administration/using/users-management.md#functional-administrators)?)--> agora pode duplicar uma configuração de evento se o evento tiver sido **publicado**.

Além disso, os usuários não administradores com o **Usuário MC** agora a função pode acessar configurações de evento, mas a permissão para duplicar é determinada pelo **Unidade organizacional** eles pertencem a. Se o usuário atual e o usuário que criou o evento pertencerem à mesma hierarquia de unidade organizacional, a duplicação será permitida.

Por exemplo, se um usuário pertencente à unidade organizacional &quot;France Sales&quot; criar uma configuração de evento:

* Um outro usuário cuja unidade organizacional é &#39;Paris Sales&#39; poderá duplicar esse evento, pois &#39;Paris Sales&#39; faz parte da unidade organizacional &#39;France Sales&#39;.

* No entanto, um usuário cuja unidade organizacional é &quot;San Francisco Sales&quot; não poderá fazê-lo, porque &quot;San Francisco Sales&quot; está sob a unidade organizacional &quot;US Sales&quot;, que é separada da unidade organizacional &quot;France Sales&quot;.

Para duplicar uma configuração de evento, siga as etapas abaixo.

1. Clique em **Adobe** no canto superior esquerdo e selecione **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]**.

1. Passe o mouse sobre a configuração de evento publicada de sua escolha e selecione o **[!UICONTROL Duplicate element]** botão.

   ![](assets/message-center_duplicate-button.png)

   >[!CAUTION]
   >
   >Não é possível duplicar uma configuração de evento que não está publicada. [Saiba mais](publishing-transactional-event.md)

1. O evento duplicado é exibido automaticamente. Ele contém a mesma configuração que você definiu para o evento original, mas tem a variável **[!UICONTROL Draft]** status.

   ![](assets/message-center_duplicated-draft-event.png)

1. A mensagem transacional correspondente é criada automaticamente. Para acessá-lo, acesse **[!UICONTROL Transactional messages]** > **[!UICONTROL Transactional messages]**.

   ![](assets/message-center_duplicated-message.png)

1. Abra a mensagem recém-duplicada. Ela contém o mesmo design que você definiu para a mensagem original, mas tem o **[!UICONTROL Draft]** mesmo se a mensagem transacional original tiver sido publicada.

   ![](assets/message-center_duplicated-draft-message.png)

1. Agora você pode editar e personalizar esta mensagem. Consulte [Edição de mensagens transacionais](../../channels/using/editing-transactional-message.md).

## Impactos {#impacts}

A tabela abaixo descreve o impacto dessas melhorias:

| Objetos | Antes desta alteração | Após essa alteração |
|:-: | :--: | :-:|
| Eventos transacionais | Somente usuários dentro do **Administrador** grupo de segurança pode criar e publicar eventos. | A variável **Usuário MC** permite que os usuários criem e publiquem eventos. |
| Mensagens transacionais | As mensagens transacionais são definidas como **Unidade organizacional** do **Agente do Centro de mensagens (mcExec)** grupo de segurança. | As mensagens transacionais são definidas como **Unidade organizacional** do grupo de segurança ao qual pertence o usuário que cria o evento/mensagem transacional. |
| Entregas de execução | Os deliveries de execução são definidos como **Unidade organizacional** do **Agente do Centro de mensagens (mcExec)** grupo de segurança. | Os deliveries de execução são definidos como **Unidade organizacional** do grupo de segurança ao qual pertence o usuário que cria o evento/mensagem transacional. |
| Eventos transacionais publicados | A duplicação não é possível para nenhum usuário. | <ul><li>Usuários com o **Administrador** o grupo de segurança pode duplicar eventos publicados.</li> <li>Usuários com o **Usuário MC** pode duplicar eventos publicados desde que estejam na mesma **Unidade organizacional** hierarquia como o usuário que criou o evento.</li></ul> |


<!--Transactional Message Templates| Transactional Message templates are set to the Organizational unit **All**. | Transaction Message Template will be set to the **Organizational unit** of the security group to which the user creating the message template belongs.-->