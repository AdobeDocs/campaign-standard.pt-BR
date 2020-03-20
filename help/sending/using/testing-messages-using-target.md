---
title: Teste de mensagens de email usando perfis direcionados
description: Saiba como testar mensagens usando perfis direcionados e endereços de substituição.
page-status-flag: never-activated
uuid: eb4d893b-3724-4b15-9312-1ec74784368d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
discoiquuid: 37320ec5-196c-4260-8156-98932da3e4a5
context-tags: seedMember,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f7f90991ed4c7323e3a2f8ac7d38da9ff165ef76

---


# Teste de mensagens de email usando perfis direcionados {#testing-message-profiles}

## Visão geral {#overview}

Além de [testar perfis](../../audiences/using/managing-test-profiles.md), você pode testar uma mensagem de email colocando-se na posição de um dos perfis de destino. Isso permite obter uma representação exata da mensagem que o perfil receberá (campos personalizados, informações dinâmicas e personalizadas, incluindo dados adicionais dos fluxos de trabalho...).

>[!NOTE]
>
> Este recurso está disponível somente com mensagens de email.

As etapas principais são as seguintes:

1. Configure sua mensagem e inicie a fase **de preparação** .
1. **Selecione um ou vários perfis** entre os perfis direcionados pela mensagem.
1. Associe a cada perfil um endereço **de** substituição para o qual as provas serão enviadas.
1. (opcional) Para cada perfil, defina um **prefixo** a ser adicionado à linha de assunto da prova.
1. **Visualize** no Designer de email como a mensagem será exibida para os perfis.
1. Envie as provas.

>[!IMPORTANT]
>
>Este recurso permite que você envie informações pessoais de perfil para endereços de email externos. Lembre-se de que a execução de solicitações de privacidade (RGPD e CCPA) no Campaign Standard NÃO executará essa solicitação externamente.

## Selecionar perfis e endereços de substituição {#selecting-profiles}

Para usar perfis direcionados para testes, você deve primeiro selecioná-los e, em seguida, definir os endereços de substituição que receberão as provas. Para fazer isso, você pode [selecionar perfis](#selecting-individual-profiles) específicos entre os perfis direcionados ou [importar perfis de um público](#importing-from-audience)existente.

>[!NOTE]
>
>Você pode selecionar um máximo de 100 perfis para teste.

### Seleção de perfis individuais {#selecting-individual-profiles}

1. No painel de mensagens, verifique se a preparação da mensagem foi bem-sucedida e clique no **[!UICONTROL Audience]** bloco.

   ![](assets/substitution_preparation.png)

1. Na **[!UICONTROL Profile substitutions]** guia, clique no **[!UICONTROL Create element]** botão para selecionar os perfis a serem usados para teste.

   ![](assets/substitution_tab.png)

1. Clique no botão de seleção de perfil para exibir a lista de perfis direcionados pela mensagem.

   ![](assets/substitution_recipient_selection.png)

1. Selecione o perfil a ser usado para teste, digite no **[!UICONTROL Address]** campo o endereço de substituição desejado e clique em **[!UICONTROL Confirm]**. Todas as provas que direcionam o perfil serão enviadas para este endereço de email, em vez do endereço definido no banco de dados para este perfil.

   Se desejar adicionar um prefixo específico à linha de assunto das provas, preencha o **[!UICONTROL Subject line prefix]** campo.

   ![](assets/substitution_address.png)

   O prefixo será exibido como abaixo:

   ![](assets/substitution_prefixsample.png)

1. O perfil é adicionado à lista, com seu endereço de substituição e prefixo associados. Repita as etapas acima para todos os perfis que você deseja usar para teste e clique em **[!UICONTROL Confirm]**.

   ![](assets/substitution_recipients_confirm.png)

   Se quiser enviar uma prova para vários endereços de substituição para um mesmo perfil, você deve adicionar esse perfil quantas vezes for necessário.

   No exemplo abaixo, a prova baseada no perfil John Smith será enviada para dois endereços de substituição diferentes:

   ![](assets/substitution_multiple_addresses.png)

1. Depois que todos os perfis e endereços de substituição forem definidos, você poderá enviar uma prova para testar a mensagem. Para fazer isso, clique no **[!UICONTROL Test]** botão e selecione o tipo de teste a ser executado.

   Observe que se nenhum perfil de teste tiver sido adicionado ao destino da mensagem, as opções **[!UICONTROL Email rendering]** e **[!UICONTROL Proof + Email rendering]** não estarão disponíveis.  For more information on proofs sending, refer to [this section](../../sending/using/sending-proofs.md).

   ![](assets/substitution_send_test.png)

>[!IMPORTANT]
>
>Se você fizer alguma alteração na sua mensagem, certifique-se de iniciar a preparação da mensagem novamente. Caso contrário, as alterações não serão refletidas na prova.

### Importar perfis de um público-alvo {#importing-from-audience}

O Campaign Standard permite importar um público-alvo de perfis que você pode usar para testes. Isso permite, por exemplo, enviar para um endereço de email exclusivo um conjunto inteiro de mensagens direcionadas a perfis diferentes.

Além disso, se seu público-alvo já estiver configurado com as colunas de endereço e prefixo, você poderá importar essas informações na **[!UICONTROL Profile substitutions]** guia. Um exemplo de importação de público-alvo com endereços de substituição está detalhado na [seção](#use-case).

>[!NOTE]
>
>Ao importar um público-alvo, somente os perfis correspondentes ao destino da mensagem são selecionados e adicionados à **[!UICONTROL Profile substitutions]** guia.

Para importar perfis para uso em testes de um público-alvo, siga estas etapas:

1. No painel de mensagens, verifique se a preparação da mensagem foi bem-sucedida e clique no **[!UICONTROL Audience]** bloco.

   ![](assets/substitution_preparation.png)

1. Na **[!UICONTROL Profile substitutions]** guia, clique em **[!UICONTROL Import from an audience]**.

   ![](assets/substitution_audience_import.png)

1. Selecione o público-alvo a ser usado e insira o endereço de substituição e o prefixo a ser usado para as provas enviadas ao público-alvo.

   ![](assets/substitution_audience_define.png)

   Se os endereços de substituição e/ou prefixos a serem usados já tiverem sido definidos no público-alvo, selecione a **[!UICONTROL From Audience]** opção e especifique a coluna a ser usada para recuperar essas informações.

   ![](assets/substitution_fromaudience.png)

1. Clique no botão **[!UICONTROL Import]**. Os perfis do público-alvo correspondentes ao destino da mensagem são adicionados à **[!UICONTROL Profile substitution]** guia, bem como os endereços de substituição e prefixos associados.

>[!NOTE]
>
>Se você importar o mesmo público-alvo novamente, com endereços de substituição e/ou prefixos diferentes, os perfis serão adicionados à lista, além dos da importação anterior.

    ![](assets/substitution_audience_added.png)

## Visualização da mensagem com perfis direcionados

>[!NOTE]
>
>A visualização está disponível somente com o Designer de email.

Para visualizar mensagens usando perfis direcionados, certifique-se de ter adicionado esses perfis à **[!UICONTROL Profile substitution]** lista (consulte [Definição de perfis e endereços](#selecting-profiles)de substituição).

Se você quiser usar campos de personalização na mensagem, eles devem ser adicionados **antes** de iniciar a preparação da mensagem. Caso contrário, eles não serão considerados na visualização. Como resultado, certifique-se de iniciar a preparação da mensagem novamente se houver alguma alteração nos campos de personalização.

Para visualizar mensagens usando substituição de perfil, siga estas etapas:

1. No painel de mensagens, clique no instantâneo de conteúdo para abrir a mensagem no Designer de email.

   ![](assets/substitution_preview_access.png)

1. Selecione a **[!UICONTROL Preview]** guia e clique em **[!UICONTROL Change profile]**.

   ![](assets/substitution_preview_changeprofile.png)

1. Clique na **[!UICONTROL Profile Substitution]** guia para exibir os perfis de substituição que foram adicionados para teste.

   Selecione os perfis que deseja usar para visualização e clique em **[!UICONTROL Select]**.

   ![](assets/substitution_preview_selection.png)

1. Uma visualização da mensagem é exibida. Use as setas para navegar entre os perfis selecionados.

   ![](assets/substitution_preview.png)

## Caso de uso {#use-case}

Nesse caso de uso, queremos enviar para um conjunto de perfis específicos um boletim informativo por email personalizado. Antes de enviar o boletim informativo, queremos visualizá-lo usando alguns dos perfis direcionados e enviar provas para endereços de email internos definidos em um arquivo externo.

As principais etapas para esse caso de uso são as seguintes:

1. Crie o público-alvo a ser usado para teste.
1. Crie um fluxo de trabalho para direcionar perfis e envie o boletim informativo.
1. Configure as substituições de perfil da mensagem.
1. Visualize a mensagem usando perfis direcionados.
1. Enviar provas.

### Etapa 1: Criar o público-alvo a ser usado para teste

1. Prepare o arquivo a ser importado para criar o público-alvo. Em nosso caso, deve conter o endereço de substituição a ser usado para a prova e um prefixo a ser adicionado à linha de assunto da prova.

   Neste exemplo, o endereço de e-mail &quot;oliver.vaughan@internal.com&quot; receberá uma prova da mensagem direcionada ao perfil com o endereço de e-mail &quot;john.doe@mail.com&quot;. O prefixo &quot;JD&quot; será adicionado à linha de assunto da prova.

   ![](assets/substitution_uc1.png)

1. Crie o fluxo de trabalho para criar um público-alvo a partir do arquivo. Para fazer isso, adicione e configure as atividades abaixo:

   * **[!UICONTROL Load file]** atividade: Importa o arquivo CSV (para obter mais informações sobre essa atividade, consulte [esta seção](../../automating/using/load-file.md)).
   * **[!UICONTROL Reconciliation]** atividade: Vincula informações do arquivo a informações do banco de dados. Neste exemplo, usaremos o endereço de email do perfil como campo de reconciliação (para obter mais informações sobre essa atividade, consulte [esta seção](../../automating/using/reconciliation.md)).
   * **[!UICONTROL Save audience]** atividade: Cria um público-alvo com base no arquivo importado (para obter mais informações sobre essa atividade, consulte [esta seção](../../automating/using/save-audience.md)).
   ![](assets/substitution_uc2.png)

1. Execute o fluxo de trabalho e vá para a **[!UICONTROL Audiences]** guia para verificar se o público-alvo foi criado com as informações desejadas.

   Neste exemplo, o público-alvo é composto de três perfis. Cada um deles está vinculado a um endereço de email de substituição que receberá a prova, com um prefixo a ser usado na linha de assunto da prova.

   ![](assets/substitution_uc3.png)

### Etapa 2: Crie um fluxo de trabalho para direcionar perfis e envie o boletim informativo

1. Adicione **[!UICONTROL Query]** e **[!UICONTROL Email delivery]** as atividades, em seguida, configure-as de acordo com suas necessidades (consulte [Consultar](../../automating/using/query.md) e seções de entrega [de](../../automating/using/email-delivery.md) email).

   ![](assets/substitution_uc4.png)

1. Execute o fluxo de trabalho e verifique se a preparação da mensagem foi bem-sucedida.

### Etapa 3: Configure a guia Substituição de perfil da mensagem

1. Open the **[!UICONTROL Email delivery]** activity. No painel de mensagens, clique no **[!UICONTROL Audience]** bloco.

   ![](assets/substitution_uc5.png)

1. Selecione a **[!UICONTROL Profile substitutions]** guia e clique em **[!UICONTROL Import from an audience]**.

   ![](assets/substitution_uc6.png)

1. No **[!UICONTROL Audience]** campo, selecione o público-alvo criado no arquivo.

   ![](assets/substitution_uc7.png)

1. Defina o endereço de substituição e o prefixo da linha de assunto a serem usados ao enviar as provas.

   Para fazer isso, selecione a **[!UICONTROL From audience]** opção e a coluna do público-alvo que contém as informações.

   ![](assets/substitution_uc8.png)

1. Clique no botão **[!UICONTROL Import]**. Os perfis do público-alvo são adicionados à lista, com seus endereços de substituição associados e prefixos de linha de assunto.

   ![](assets/substitution_uc9.png)

   >[!NOTE]
   >
   >Em nosso caso, todos os perfis do público-alvo são direcionados pela **[!UICONTROL Query]** atividade. Se um desses perfis não fizesse parte do destino da mensagem, ele não seria adicionado à lista.

### Etapa 4: Visualizar a mensagem usando perfis direcionados

1. No painel de mensagens, clique no instantâneo de conteúdo para abrir a mensagem no Designer de email.

   ![](assets/substitution_uc10.png)

1. Selecione a **[!UICONTROL Preview]** guia e clique em **[!UICONTROL Change profile]**.

   ![](assets/substitution_uc_preview.png)

1. Clique na **[!UICONTROL Profile Substitution]** guia para exibir os perfis de substituição que foram adicionados anteriormente.

   Selecione os perfis que deseja usar para visualização e clique em **[!UICONTROL Select]**.

   ![](assets/substitution_uc_selectpreview.png)

1. Uma visualização da mensagem é exibida. Use as setas para navegar entre os perfis selecionados.

   ![](assets/substitution_uc_previewprofile.png)

### Etapa 5: Enviar provas

1. No painel de mensagens, clique no **[!UICONTROL Test]** botão e, em seguida, confirme.

   ![](assets/substitution_uc_sendproof.png)

1. As provas são enviadas de acordo com o que foi configurado na guia **[!UICONTROL[Profile substitutions ]**.

   ![](assets/substitution_uc_proofs.png)
