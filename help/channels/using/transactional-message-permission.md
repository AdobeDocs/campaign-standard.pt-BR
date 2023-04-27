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
exl-id: 995da330-6c86-444b-86b2-61d887f37db4
source-git-commit: 8e6465e8334ea621b353b0a908e231b9093c58ce
workflow-type: tm+mt
source-wordcount: '797'
ht-degree: 0%

---

# Melhorias no evento transacional {#transactional-event-improvements}

>[!AVAILABILITY]
>
>No momento, esses recursos estão disponíveis apenas para um conjunto de organizações (Disponibilidade limitada). Para obter mais informações, entre em contato com o representante do Adobe.

Atualmente, no Adobe Campaign Standard, os usuários sem o grupo de segurança Administrador não podem acessar, criar ou publicar eventos transacionais, causando problemas para os usuários corporativos que precisam configurar e publicar eventos, mas não têm direitos de Administrador. Além disso, não é possível duplicar eventos transacionais.

Implementamos as seguintes melhorias no controle de acesso de mensagens transacionais:

* Um novo **[!UICONTROL Role]**, chamada **Usuário do MC**, foi adicionado para permitir que usuários não administradores gerenciem a configuração de eventos transacionais. O **Usuário do MC** concede a esses usuários a capacidade de acessar, criar, publicar e cancelar a publicação de eventos e mensagens transacionais.

* Os deliveries de execução (ou seja, mensagens técnicas que são criadas sempre que uma mensagem transacional é editada e publicada novamente ou uma vez por mês, por padrão) agora são definidos como a variável **[!UICONTROL Organizational unit]** do grupo de segurança ao qual o usuário que está criando o evento pertence, em vez de ser restrito ao **[!UICONTROL Organizational unit]** do **Agente do Centro de Mensagens (mcExec)** grupo de segurança.

* **Administradores** agora pode duplicar eventos transacionais publicados, bem como usuários com a variável **Usuário do MC** função desde que estejam na mesma **Unidade organizacional** hierarquia como o usuário que criou o evento.

## Atribuir a função de usuário MC {#assign-role}

Para atribuir a variável **Usuário do MC** função para seu grupo de segurança:

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

## Atribuir o grupo de segurança do usuário MC {#assign-group}

1. Na Admin Console , selecione o **Produtos** guia .

1. Selecionar **Adobe Campaign Standard** em seguida, escolha sua instância.

1. No **Perfis de produto** selecione a **Usuário do MC** grupo.

1. Clique em **Adicionar usuário** e insira o nome, o grupo de usuários ou o endereço de email do perfil que deseja adicionar a este perfil de produto.

1. Depois de adicionado, clique em **Salvar**.

Usuários adicionados a isso **[!UICONTROL Security group]** Agora o pode acessar, criar e publicar eventos e mensagens transacionais.

## Eventos transacionais duplicados {#duplicate-transactional-events}

Um usuário com a **Administrador** grupo de segurança<!--([Functional administrators](../../administration/using/users-management.md#functional-administrators)?)--> agora pode duplicar uma configuração de evento se o evento tiver sido **publicado**.

Além disso, usuários não administradores com a variável **Usuário do MC** agora pode acessar configurações de evento, mas a permissão para duplicar é determinada pela função **Unidade organizacional** eles pertencem a. Se o usuário atual e o usuário que criou o evento pertencerem à mesma hierarquia de unidade organizacional, a duplicação será permitida.

Por exemplo, se um usuário pertencente à unidade organizacional &quot;Vendas da França&quot; criar uma configuração de evento:

* Outro usuário cuja unidade organizacional é &#39;Vendas de Paris&#39; poderá duplicar esse evento, pois &#39;Vendas de Paris&#39; faz parte da unidade organizacional &#39;Vendas da França&#39;.

* No entanto, um usuário cuja unidade organizacional é &#39;Vendas de São Francisco&#39; não poderá fazer isso, porque &#39;Vendas de São Francisco&#39; está na unidade organizacional &#39;Vendas dos EUA&#39;, que é separada da unidade organizacional &#39;Vendas da França&#39;.

Para duplicar uma configuração de evento, siga as etapas abaixo.

1. Clique no botão **Adobe** logotipo , no canto superior esquerdo, em seguida, selecione **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]**.

1. Passe o mouse sobre a configuração de evento publicada de sua escolha e selecione o **[!UICONTROL Duplicate element]** botão.

   ![](assets/message-center_duplicate-button.png)

   >[!CAUTION]
   >
   >Não é possível duplicar uma configuração de evento que não está publicada. [Saiba mais](publishing-transactional-event.md)

1. O evento duplicado é exibido automaticamente. Ele contém a mesma configuração que você definiu para o evento original, mas tem o **[!UICONTROL Draft]** status.

   ![](assets/message-center_duplicated-draft-event.png)

1. A mensagem transacional correspondente é criada automaticamente. Para acessá-lo, acesse **[!UICONTROL Transactional messages]** > **[!UICONTROL Transactional messages]**.

   ![](assets/message-center_duplicated-message.png)

1. Abra a mensagem recém-duplicada. Ele contém o mesmo design que você definiu para a mensagem original, mas tem o **[!UICONTROL Draft]** , mesmo se a mensagem transacional original tiver sido publicada.

   ![](assets/message-center_duplicated-draft-message.png)

1. Agora você pode editar e personalizar esta mensagem. Consulte [Edição de mensagens transacionais](../../channels/using/editing-transactional-message.md).

## Impactos {#impacts}

A tabela abaixo descreve o impacto dessas melhorias:

| Objetos | Antes desta alteração | Após esta alteração |
|:-: | :--: | :-:|
| Eventos transacionais | Somente usuários na **Administrador** grupo de segurança pode criar e publicar eventos. | O **Usuário do MC** permite que os usuários criem e publiquem eventos. |
| Mensagens transacionais | As mensagens transacionais são definidas para a variável **Unidade organizacional** do **Agente do Centro de Mensagens (mcExec)** grupo de segurança. | As mensagens transacionais são definidas para a variável **Unidade organizacional** do grupo de segurança ao qual o usuário que cria o evento/mensagem transacional pertence. |
| Deliveries de execução | Os deliveries de execução são definidos como **Unidade organizacional** do **Agente do Centro de Mensagens (mcExec)** grupo de segurança. | Os deliveries de execução são definidos como **Unidade organizacional** do grupo de segurança ao qual o usuário que cria o evento/mensagem transacional pertence. |
| Eventos transacionais publicados | A duplicação não é possível para nenhum usuário. | <ul><li>Usuários com a **Administrador** o grupo de segurança pode duplicar eventos publicados.</li> <li>Usuários com a **Usuário do MC** A função pode duplicar eventos publicados, desde que eles estejam na mesma **Unidade organizacional** hierarquia como o usuário que criou o evento.</li></ul> |


<!--Transactional Message Templates| Transactional Message templates are set to the Organizational unit **All**. | Transaction Message Template will be set to the **Organizational unit** of the security group to which the user creating the message template belongs.-->