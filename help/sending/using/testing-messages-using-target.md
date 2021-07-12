---
solution: Campaign Standard
product: campaign
title: Teste de mensagens de email usando perfis direcionados
description: Saiba como testar mensagens usando perfis direcionados e endereços de substituição.
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
context-tags: seedMember,overview
feature: Grupos de controle
role: User
level: Intermediate
exl-id: aa68914f-0497-40ba-98c8-4d4b2c6705fb
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '1516'
ht-degree: 5%

---

# Teste de mensagens de email usando perfis direcionados {#testing-message-profiles}

## Visão geral {#overview}

Além de [testar perfis](../../audiences/using/managing-test-profiles.md), você pode testar uma mensagem de email colocando-se na posição de um dos perfis segmentados. Isso permite obter uma representação exata da mensagem que o perfil receberá (campos personalizados, informações dinâmicas e personalizadas, incluindo dados adicionais de workflows...).

>[!NOTE]
>
> Esse recurso está disponível somente com mensagens de email.

As principais etapas são as seguintes:

1. Configure sua mensagem e inicie a fase **Preparation**.
1. **Selecione um ou vários** perfis entre os perfis direcionados pela mensagem.
1. Associe a cada perfil um **endereço de substituição** para o qual serão enviadas provas.
1. (opcional) Para cada perfil, defina um **prefixo** para adicionar à linha de assunto da prova.
1. **** Visualizar o Designer de email como a mensagem será exibida para os perfis.
1. Envie as provas.

>[!IMPORTANT]
>
>Esse recurso permite enviar informações pessoais do perfil para endereços de email externos. Lembre-se de que a execução de solicitações de privacidade (GDPR e CCPA) no Campaign Standard NÃO executará externamente essa solicitação.

![](assets/do-not-localize/how-to-video.png) [Descubra este recurso no vídeo](#video)

## Seleção de perfis e endereços de substituição {#selecting-profiles}

Para usar perfis direcionados para testes, primeiro você deve selecioná-los e definir os endereços de substituição que receberão as provas. Para fazer isso, você pode [selecionar perfis específicos](#selecting-individual-profiles) entre os perfis direcionados ou [importar perfis de um público existente](#importing-from-audience).

>[!NOTE]
>
>Você pode selecionar no máximo 100 perfis para teste.

### Seleção de perfis individuais {#selecting-individual-profiles}

1. No painel de mensagens, verifique se a preparação da mensagem foi bem-sucedida e clique no bloco **[!UICONTROL Audience]** .

   ![](assets/substitution_preparation.png)

1. Na guia **[!UICONTROL Profile substitutions]** , clique no botão **[!UICONTROL Create element]** para selecionar os perfis a serem usados para testes.

   ![](assets/substitution_tab.png)

1. Clique no botão de seleção de perfil para exibir a lista de perfis segmentados pela mensagem.

   ![](assets/substitution_recipient_selection.png)

1. Selecione o perfil a ser usado para teste e insira no campo **[!UICONTROL Address]** o endereço de substituição desejado e clique em **[!UICONTROL Confirm]**. Todas as provas que direcionam o perfil serão enviadas para este endereço de email, em vez do endereço definido no banco de dados para este perfil.

   Se desejar adicionar um prefixo específico à linha de assunto das provas, preencha o campo **[!UICONTROL Subject line prefix]**.

   >[!NOTE]
   >
   >O prefixo da linha de assunto pode conter até 500 caracteres.

   ![](assets/substitution_address.png)

   O prefixo será exibido como abaixo:

   ![](assets/substitution_prefixsample.png)

1. O perfil é adicionado à lista, com o endereço e prefixo de substituição associados. Repita as etapas acima para todos os perfis que deseja usar para testes e clique em **[!UICONTROL Confirm]**.

   ![](assets/substitution_recipients_confirm.png)

   Se quiser enviar uma prova para vários endereços de substituição de um mesmo perfil, você deve adicionar esse perfil quantas vezes forem necessárias.

   No exemplo abaixo, a prova baseada no perfil John Smith será enviada para dois endereços de substituição diferentes:

   ![](assets/substitution_multiple_addresses.png)

1. Depois que todos os perfis e endereços de substituição forem definidos, você poderá enviar uma prova para testar a mensagem. Para fazer isso, clique no botão **[!UICONTROL Test]** e selecione o tipo de teste a ser executado.

   Observe que, se nenhum perfil de teste tiver sido adicionado ao destino da mensagem, as opções **[!UICONTROL Email rendering]** e **[!UICONTROL Proof + Email rendering]** não estarão disponíveis.  Para obter mais informações sobre o envio de provas, consulte [esta seção](../../sending/using/sending-proofs.md).

   ![](assets/substitution_send_test.png)

>[!IMPORTANT]
>
>Se você fizer qualquer alteração na mensagem, certifique-se de iniciar a preparação da mensagem novamente. Caso contrário, as alterações não serão refletidas na prova.

### Importação de perfis de um público {#importing-from-audience}

O Campaign Standard permite importar um público-alvo de perfis que você pode usar para testes. Isso permite, por exemplo, enviar para um endereço de email exclusivo um conjunto inteiro de mensagens direcionadas a diferentes perfis.

Além disso, se o público-alvo já estiver configurado com as colunas de endereço e prefixo, é possível importar essas informações na guia **[!UICONTROL Profile substitutions]**. Um exemplo de importação de público-alvo com endereços de substituição é detalhado em [this section](#use-case).

>[!NOTE]
>
>Ao importar um público-alvo, somente os perfis correspondentes ao público-alvo da mensagem são selecionados e adicionados à guia **[!UICONTROL Profile substitutions]** .

Para importar perfis para uso no teste de um público-alvo, siga estas etapas:

1. No painel de mensagens, verifique se a preparação da mensagem foi bem-sucedida e clique no bloco **[!UICONTROL Audience]** .

   ![](assets/substitution_preparation.png)

1. Na guia **[!UICONTROL Profile substitutions]**, clique em **[!UICONTROL Import from an audience]**.

   ![](assets/substitution_audience_import.png)

1. Selecione o público-alvo a ser usado e insira o endereço de substituição e o prefixo para usar nas provas enviadas para o público-alvo.

   >[!NOTE]
   >
   >O prefixo da linha de assunto pode conter até 500 caracteres.

   ![](assets/substitution_audience_define.png)

   Se os endereços de substituição e/ou prefixos a serem usados já tiverem sido definidos no público-alvo, selecione a opção **[!UICONTROL From Audience]** e especifique a coluna a ser usada para recuperar essas informações.

   ![](assets/substitution_fromaudience.png)

1. Clique no botão **[!UICONTROL Import]**. Os perfis do público-alvo correspondentes ao direcionamento da mensagem são adicionados à guia **[!UICONTROL Profile substitution]** , bem como os endereços de substituição e prefixos associados.

![](assets/substitution_audience_imported.png)

>[!NOTE]
>
>Se você importar o mesmo público-alvo novamente, com endereços de substituição e/ou prefixos diferentes, os perfis serão adicionados à lista, além dos da importação anterior.

## Pré-visualização da mensagem com perfis direcionados

>[!NOTE]
>
>A visualização está disponível somente com o Designer de email.

Para visualizar mensagens usando perfis direcionados, adicione esses perfis à lista **[!UICONTROL Profile substitution]** (consulte [Definição de perfis e endereços de substituição](#selecting-profiles)).

Se você quiser usar campos de personalização na mensagem, eles deverão ser adicionados **antes de** iniciar a preparação da mensagem. Caso contrário, elas não serão consideradas na visualização. Como resultado, inicie a preparação da mensagem novamente se alguma alteração for feita nos campos de personalização.

Para visualizar mensagens usando substituição de perfil, siga estas etapas:

1. No painel de mensagens, clique no instantâneo de conteúdo para abrir a mensagem no Designer de email.

   ![](assets/substitution_preview_access.png)

1. Selecione a guia **[!UICONTROL Preview]** e clique em **[!UICONTROL Change profile]**.

   ![](assets/substitution_preview_changeprofile.png)

1. Clique na guia **[!UICONTROL Profile Substitution]** para exibir os perfis de substituição que foram adicionados para teste.

   Selecione os perfis que deseja usar na visualização e clique em **[!UICONTROL Select]**.

   ![](assets/substitution_preview_selection.png)

1. Uma pré-visualização da mensagem é exibida. Use as setas para navegar entre os perfis selecionados.

   ![](assets/substitution_preview.png)

## Caso de uso {#use-case}

Nesse caso de uso, queremos enviar para um conjunto de perfis específicos um boletim informativo de email personalizado. Antes de enviar o boletim informativo, queremos pré-visualizá-lo usando alguns dos perfis segmentados e enviar provas para endereços de email internos definidos em um arquivo externo.

As principais etapas para esse caso de uso são as seguintes:

1. Crie o público-alvo a ser usado para teste.
1. Crie um workflow para direcionar perfis e enviar o boletim informativo.
1. Configure as substituições de perfil da mensagem.
1. Visualize a mensagem usando perfis direcionados.
1. Envie provas.

### Etapa 1: Criar o público-alvo a ser usado para teste

1. Prepare o arquivo a ser importado para criar o público-alvo. No nosso caso, ele deve conter o endereço de substituição a ser usado para a prova e um prefixo para ser adicionado à linha de assunto da prova.

   Neste exemplo, o endereço de email &quot;oliver.vaughan@internal.com&quot; receberá uma prova da mensagem direcionada ao perfil com o endereço de email &quot;john.doe@mail.com&quot;. O prefixo &quot;JD&quot; será adicionado à linha de assunto da prova.

   ![](assets/substitution_uc1.png)

1. Crie o workflow para criar um público-alvo a partir do arquivo . Para fazer isso, adicione e configure as atividades abaixo:

   * **[!UICONTROL Load file]** atividade : Importa o arquivo CSV (para obter mais informações sobre essa atividade, consulte  [esta seção](../../automating/using/load-file.md)).
   * **[!UICONTROL Reconciliation]** atividade : Vincula informações do arquivo às informações do banco de dados. Neste exemplo, usaremos o endereço de email do perfil como campo de reconciliação (para obter mais informações sobre essa atividade, consulte [esta seção](../../automating/using/reconciliation.md)).
   * **[!UICONTROL Save audience]** atividade : Cria um público-alvo com base no arquivo importado (para obter mais informações sobre essa atividade, consulte  [esta seção](../../automating/using/save-audience.md)).

   ![](assets/substitution_uc2.png)

1. Execute o workflow e vá para a guia **[!UICONTROL Audiences]** para verificar se o público-alvo foi criado com as informações desejadas.

   Neste exemplo, o público-alvo é composto de três perfis. Cada um deles está vinculado a um endereço de email de substituição que receberá a prova, com um prefixo a ser usado na linha de assunto da prova.

   ![](assets/substitution_uc3.png)

### Etapa 2: Crie um workflow para direcionar perfis e enviar o boletim informativo

1. Adicione **[!UICONTROL Query]** e **[!UICONTROL Email delivery]** atividades, em seguida, configure-as de acordo com suas necessidades (consulte as seções [Query](../../automating/using/query.md) e [Email delivery](../../automating/using/email-delivery.md)).

   ![](assets/substitution_uc4.png)

1. Execute o fluxo de trabalho e verifique se a preparação da mensagem foi bem-sucedida.

### Etapa 3: Configure a guia Substituição de perfil da mensagem

1. Abra a atividade **[!UICONTROL Email delivery]**. No painel de mensagens, clique no bloco **[!UICONTROL Audience]** .

   ![](assets/substitution_uc5.png)

1. Selecione a guia **[!UICONTROL Profile substitutions]** e clique em **[!UICONTROL Import from an audience]**.

   ![](assets/substitution_uc6.png)

1. No campo **[!UICONTROL Audience]** , selecione o público criado do arquivo.

   ![](assets/substitution_uc7.png)

1. Defina o endereço de substituição e o prefixo da linha de assunto a serem usados ao enviar as provas.

   Para fazer isso, selecione a opção **[!UICONTROL From audience]** e selecione a coluna do público-alvo que contém as informações.

   ![](assets/substitution_uc8.png)

1. Clique no botão **[!UICONTROL Import]**. Os perfis do público-alvo são adicionados à lista, com seus endereços de substituição associados e prefixos de linha de assunto.

   ![](assets/substitution_uc9.png)

   >[!NOTE]
   >
   >No nosso caso, todos os perfis do público-alvo são direcionados pela atividade **[!UICONTROL Query]** . Se um desses perfis não fizesse parte do público-alvo da mensagem, ele não seria adicionado à lista.

### Etapa 4: Visualizar a mensagem usando perfis direcionados

1. No painel de mensagens, clique no instantâneo de conteúdo para abrir a mensagem no Designer de email.

   ![](assets/substitution_uc10.png)

1. Selecione a guia **[!UICONTROL Preview]** e clique em **[!UICONTROL Change profile]**.

   ![](assets/substitution_uc_preview.png)

1. Clique na guia **[!UICONTROL Profile Substitution]** para exibir os perfis de substituição que foram adicionados anteriormente.

   Selecione os perfis que deseja usar na visualização e clique em **[!UICONTROL Select]**.

   ![](assets/substitution_uc_selectpreview.png)

1. Uma pré-visualização da mensagem é exibida. Use as setas para navegar entre os perfis selecionados.

   ![](assets/substitution_uc_previewprofile.png)

### Etapa 5: Enviar provas

1. No painel da mensagem, clique no botão **[!UICONTROL Test]** e confirme.

   ![](assets/substitution_uc_sendproof.png)

1. As provas são enviadas de acordo com o que foi configurado na guia **[!UICONTROL Profile substitutions]** .

   ![](assets/substitution_uc_proofs.png)

## Tutorial em vídeo {#video}

Este vídeo mostra como você pode testar suas mensagens de email usando a substituição do perfil.

>[!VIDEO](https://video.tv.adobe.com/v/32368?quality=12)

Os vídeos de instruções adicionais do Campaign Standard estão disponíveis [aqui](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=pt-BR).
