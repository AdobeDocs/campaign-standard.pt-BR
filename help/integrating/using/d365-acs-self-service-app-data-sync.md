---
title: Sincronizar dados entre o Campaign e o Microsoft Dynamics
description: Sincronizar dados entre o Campaign e o Dynamics
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
exl-id: 66623c76-96aa-45cd-9637-19d8a9732c04
source-git-commit: e7fdaa4b1d77afdae8004a88bbe41bbbe75a3f3c
workflow-type: tm+mt
source-wordcount: '1839'
ht-degree: 0%

---

# Sincronizar dados

Você pode sincronizar tabelas do Microsoft Dynamics 365 para métricas de marketing do Campaign e do Campaign para o Microsoft Dynamics 365. A sincronização é executada por meio de três fluxos de trabalho técnicos dedicados: **[!UICONTROL Microsoft Dynamics 365 to Campaign]**, **[!UICONTROL Campaign to Microsoft Dynamics 365]**, **[!UICONTROL Opt-In/Out]**. Consulte esta seção para [saber mais](../../integrating/using/d365-acs-self-service-app-workflows.md).

>[!IMPORTANT]
>Você precisa interromper/iniciar o fluxo de trabalho **[!UICONTROL Microsoft Dynamics 365 to Campaign]** para que suas alterações sejam consideradas. [Saiba mais](../../integrating/using/d365-acs-self-service-app-workflows.md)
>

## Mapear tabelas do Microsoft Dynamics 365 para o Campaign

A página **[!UICONTROL Microsoft Dynamics 365 to Campaign]** mostra uma lista de entidades no Microsoft Dynamics 365 e os recursos personalizados no Adobe Campaign com os quais eles serão sincronizados. É possível adicionar novos mapeamentos, editar ou excluir mapeamentos existentes.

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-top.png)

Aqui está uma descrição de cada uma das colunas nesta tabela:

* **[!UICONTROL MICROSOFT DYNAMICS 365 TABLE]**: esta coluna identifica qual entidade no Microsoft Dynamics 365 será a fonte de dados para o mapeamento.

* **[!UICONTROL CAMPAIGN TABLE]**: esta coluna identifica qual recurso no Adobe Campaign será o destino dos dados para o mapeamento.

* **[!UICONTROL ACTIONS]**: as ações possíveis estão listadas abaixo:

   * Clique no ícone **[!UICONTROL Edit]** para editar esse mapeamento.

   * Use o ícone **[!UICONTROL Delete]** para excluir um mapeamento de tabela.

   * Clique no ícone **[!UICONTROL Replay Data]** para sincronizar novamente todos os dados na tabela do Microsoft Dynamics 365. Normalmente, o aplicativo de integração só sincronizará os dados no Microsoft Dynamics 365 que foram alterados recentemente.  No entanto, em alguns casos (por exemplo, você fez uma alteração ou um erro), talvez você queira que todos os dados sejam ressincronizados.  Nesses casos, você clicaria nesse botão e, na próxima vez que interromper/iniciar o fluxo de trabalho do **[!UICONTROL Microsoft Dynamics 365 to Campaign]**, seus dados começariam a sincronizar.

     Se você clicar no botão **[!UICONTROL Replay Data]** e as verificações forem bem-sucedidas, o ícone será desabilitado: indica que os dados deste par de mapeamentos de tabela serão ressincronizados com a próxima execução do fluxo de trabalho **[!UICONTROL Microsoft Dynamics 365 to Campaign]**.

     Não é possível selecionar a repetição dos dados quando o seguinte é verdadeiro:

      * Se houver 2.000.000 (ou mais) itens na métrica de Backlog associados ao fluxo de trabalho **[!UICONTROL Microsoft Dynamics 365 to Campaign]** (exibidos na página **[!UICONTROL Workflows]**)
      * Se houver 2.000.000 ou mais registros na tabela do Microsoft Dynamics 365

     O número de registros que precisam ser ressincronizados varia. Se você tiver um grande número de registros, pode levar algum tempo para concluir o processo de sincronização. Consulte a métrica **[!UICONTROL Backlog]** na página **[!UICONTROL Workflows]** conforme o aplicativo de integração funciona para concluir o processo de sincronização.

     >[!IMPORTANT]
     >
     > É altamente recomendável interromper o fluxo de trabalho de integração ao publicar alterações no Adobe Campaign Standard ou no Microsoft Dynamics 365. As alterações aplicáveis incluem: atualizações de recursos/entidades (e seus campos associados), links, colunas de identificador etc. que estão atualmente em uso pela integração.
     >

## Criar um novo mapeamento {#add-a-new-mapping}

Para criar um novo mapeamento, siga as etapas abaixo:

1. na página **[!UICONTROL Microsoft Dynamics 365 to Campaign]**, clique no botão **[!UICONTROL Add New Mapping]**.

1. Use as listas suspensas para selecionar as tabelas do Microsoft Dynamics 365 e do Campaign a serem mapeadas.
A maioria das outras entradas na página dependerá das tabelas escolhidas.

   ![](assets/do-not-localize/d365-to-acs-ui-page-ingress-choose-tables.png)

   >[!NOTE]
   >Não é possível mapear cada tabela mais de uma vez. Portanto, você observará que as seleções suspensas não incluirão tabelas que já foram mapeadas.

1. Clique em **[!UICONTROL OK]** para confirmar: o aplicativo precisará de um breve momento para ler as informações de campo associadas às tabelas selecionadas.

Em seguida, você pode continuar com a configuração de mapeamento. [Saiba mais](#new-mapping-settings)

>[!IMPORTANT]
>
>Você só poderá escolher as tabelas nesta página quando estiver adicionando o mapeamento pela primeira vez. Verifique se você selecionou as tabelas corretas antes de clicar no botão **[!UICONTROL Save]**: uma vez salvos, os campos de seleção da tabela serão **somente leitura**.

### Editar um mapeamento existente

Ao editar um mapeamento existente, você verá que as seleções de tabela não são editáveis.

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-table-read-only.png)

Isso ocorre por design porque as entradas mais abaixo na página são baseadas nos campos associados a essas tabelas. A alteração das tabelas tornaria todos os campos associados a essas tabelas inválidos.  Se quiser alterar a tabela para a qual mapear, você precisará retornar à página anterior, excluir o mapeamento que deseja alterar e adicionar um novo mapeamento.

### Configurar um mapeamento de tabela individual {#new-mapping-settings}

Nesta seção, você aprenderá a configurar um mapeamento **único** de uma tabela do Microsoft Dynamics 365 para uma tabela do Adobe Campaign.

Você pode definir as seguintes configurações:

* **[!UICONTROL Tables]**: esta seção lista o nome da tabela do Microsoft Dynamics 365 e a tabela do Campaign para a qual ela será mapeada.
* **[!UICONTROL Field Mappings]**: saiba mais em [esta seção](#field-mappings)
* **[!UICONTROL Field Replacements]**: saiba mais em [esta seção](#field-replacements)
* **[!UICONTROL Filters]**: saiba mais em [esta seção](#filters)
* **[!UICONTROL Advanced Settings]**: saiba mais em [esta seção](#advanced-settings)

### Mapeamentos de campos {#field-mappings}

#### Chaves Primárias

Ao adicionar um novo Microsoft Dynamics 365 ao mapeamento de tabela do Campaign, é necessário identificar o campo ID.

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-mappings-first-key.png)

A chave primária do Microsoft Dynamics 365 é somente leitura porque o aplicativo a detectará.

Para o Campaign, é necessário selecionar qual campo será a chave exclusiva. Ele deve ser configurado como um [recurso personalizado de ID do CRM](../../developing/using/uc-calling-resource-id-key.md) e não deve ter duplicatas.

>[!NOTE]
>
>Você só poderá escolher o campo de ID na tabela quando tiver selecionado **[!UICONTROL Add New Mapping]**. Se você clicar no botão editar para editar um mapeamento de tabela existente, o campo de ID será somente leitura.

As chaves primárias sempre serão os primeiros nomes de campo listados na seção **[!UICONTROL Field Mappings]**. Como lembrete, o ícone a seguir é listado à direita para lembrá-lo de que essas são as chaves primárias.

![](assets/do-not-localize/d365-to-acs-icon-primary-key.png)

#### Adicionar outros mapeamentos de campo

A seção **[!UICONTROL Field Mappings]** permite adicionar mapeamentos de campos diferentes das Chaves Primárias. Para adicionar um novo mapeamento de um campo do Microsoft Dynamics 365 para o Adobe Campaign, clique no botão **[!UICONTROL Add new field mapping]**.

Selecione os campos Microsoft Dynamics 365 e Campaign nas listas:

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-new-field-mapping.png)

Essas listas contêm os nomes de campo associados às tabelas do Microsoft Dynamics 365 e do Campaign selecionadas na parte superior da página.

O alternador **[!UICONTROL Apply updates]** permite controlar se as atualizações para esse campo serão propagadas do Microsoft Dynamics 365 para o Campaign:
* Se estiver ligado ![](assets/do-not-localize/d365-to-acs-icon-switch-on.png), as atualizações do(s) valor(es) no Microsoft Dynamics 365 serão propagadas para o Adobe Campaign à medida que ocorrerem.

* Se você desligou o ![](assets/do-not-localize/d365-to-acs-icon-switch-off.png), o valor será propagado quando os dados forem carregados inicialmente (ou repetidos), mas as atualizações incrementais para o campo no Microsoft Dynamics 365 não serão propagadas.

>[!NOTE]
>
>Clique no cabeçalho da coluna **[!UICONTROL Apply updates]** para atualizar **all** das opções para ativado ou desativado.
>

Ao selecionar valores de campo, você verá que o tipo de dados é exibido abaixo dos menus suspensos.   Isso é algo para ter em mente ao mapear valores de um campo para o outro.

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-mappings-fields-selected.png)

>[!NOTE]
>
> Não é possível mapear vários campos do Microsoft Dynamics 365 para um único campo do Campaign.

### Substituições de campo {#field-replacements}

Use o botão **[!UICONTROL Add New Field Replacement]** para definir uma nova substituição de campo.

As substituições de campo permitem identificar:

* um nome de campo do Microsoft Dynamics 365 (que foi adicionado acima na seção mapeamentos de campo),
* um valor existente (que existe no Microsoft Dynamics 365) e
* um novo valor para gravar no Adobe Campaign

Uma lista suspensa será fornecida para valores de lista de seleção, enumeração e booleanos. Uma caixa de texto será usada para outros tipos de cadeia de caracteres e numéricos.

### Filtros {#filters}

Use o botão **[!UICONTROL Add New Filter]** para selecionar quais registros do Microsoft Dynamics 365 serão propagados para o Campaign. Você pode escolher qualquer campo associado a um registro para adicionar aos filtros (o nome do campo não precisa ser adicionado aos mapeamentos de campo).

Especifique um filtro preenchendo as seguintes informações:

* Nome de campo do Microsoft Dynamics 365
* um valor de comparação, e
* um valor (do Microsoft Dynamics 365)
Se o nome do campo, a comparação e o valor forem avaliados como true para um determinado registro, o registro será propagado para o Adobe Campaign.

Você pode escolher como esses filtros são avaliados definindo a entrada rotulada **[!UICONTROL Choose the filter comparison operator]**.  Se você escolher **And**, todos os filtros deverão ser verdadeiros para que um registro seja propagado para o Campaign. Se você escolher **Or**, o registro será propagado se qualquer um deles for avaliado como verdadeiro.

A opção **[!UICONTROL Do you want to delete records in Adobe Campaign Standard that will be filtered out from Microsoft Dynamics 365?]** controla se você deseja que os registros filtrados sejam excluídos do Campaign. Se você selecionar **Não**, os registros permanecerão no Adobe Campaign. Selecione **Sim** para excluí-los pela lógica de integração.

>[!NOTE]
>
> Se nenhum filtro for adicionado, todos os registros que foram modificados serão propagados para o Adobe Campaign.
>

### Configurações avançadas {#advanced-settings}

Você pode definir as seguintes opções adicionais ao configurar um mapeamento:

* Defina a opção **[!UICONTROL Apply deletes in Microsoft Dynamics 365 to Campaign?]** como **Sim**, se desejar propagar exclusões que ocorrem no Microsoft Dynamics 365 para o campo correspondente no Adobe Campaign (com base no mapeamento do nome do campo). Selecione **Não** para ignorar exclusões no Microsoft Dynamics 365.

* Defina a opção **[!UICONTROL Use technical values in Microsoft Dynamics 365 picklists?]** como **Não** se desejar propagar para o Campaign o valor de exibição associado a uma lista de opções do Microsoft Dynamics 365. Selecione **Sim** para propagar o valor técnico.

## Sincronizar eventos de marketing do Campaign com o Microsoft Dynamics 365

A página **[!UICONTROL Campaign to Microsoft Dynamics 365]** permite identificar quais eventos de marketing por email serão mapeados do Adobe Campaign para o Microsoft Dynamics 365.

As quatro métricas que você pode controlar são: **Envios**, **Cliques**, **Aberturas** e **Rejeições**.

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-egress.png)

Selecione **Sim** para confirmar se você deseja que os eventos desse tipo fluam para o Microsoft Dynamics 365.

Clique [aqui](../../integrating/using/d365-acs-self-service-app-workflows.md) para obter mais informações sobre esses fluxos de eventos de email.

## Fluxo de trabalho de aceitação/recusa {#opt-in-out-wf}

O fluxo de trabalho **Aceitar/Recusar** permite identificar o fluxo das informações de aceitação/recusa entre o Microsoft Dynamics 365 e o Adobe Campaign. Isso pressupõe que os dados estejam associados à entidade &quot;contato&quot; do Microsoft Dynamics 365 e ao &quot;perfil&quot; de recurso do Adobe Campaign.

Saiba mais sobre o gerenciamento de recusa em [esta seção](../../integrating/using/d365-acs-notices-and-recommendations.md#opt-out).

Lembre-se de que é necessário clicar em &quot;Salvar&quot; para salvar as seleções. Lembre-se também de que você deve interromper o fluxo de trabalho **Campaign to Microsoft Dynamics 365** e clicar em reproduzir para que a integração incorpore suas alterações.

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-optinout-disabled.png)

### Direção de sincronização de aceitação/recusa

Abaixo está a lista de opções disponíveis para sincronizar dados:

* **[!UICONTROL Disabled]**: quando essa opção é selecionada, nenhuma informação de aceitação/recusa é movida entre o Adobe Campaign e o Microsoft Dynamics 365.

* **[!UICONTROL Unidirectional (Microsoft Dynamics 365 to Campaign)]**: essa opção é usada para fluir a aceitação/recusa do Microsoft Dynamics 365 somente para o Adobe Campaign. O aplicativo de integração não permitirá a configuração do fluxo nesta tela; em vez disso, clique em **[!UICONTROL Save button]** e navegue até o fluxo de trabalho **[!UICONTROL Microsoft Dynamics 365 to Campaign]**. Nesse fluxo de trabalho, você pode editar o mapeamento da tabela de contatos/perfis para identificar como deseja mapear os campos de aceitação/recusa.

* **[!UICONTROL Unidirectional (Campaign to Microsoft Dynamics 365)]**: esta opção tornará visível a seção **Mapeamentos**. Essas entradas permitirão definir quais campos do Adobe Campaign mapearão dados para quais campos no Microsoft Dynamics 365. Isso significa que, se você atualizar manualmente um valor no Microsoft Dynamics 365, seu valor será substituído pelo valor do Adobe Campaign se ocorrer uma alteração.

* **[!UICONTROL Bidirectional]**: esta opção tornará visível a seção **Mapeamentos**. Esses pares identificarão quais campos no Microsoft Dynamics 365 e no Adobe Campaign serão mapeados entre si. [Saiba mais](../../integrating/using/d365-acs-notices-and-recommendations.md).

### Mapeamentos

Esta seção só se aplica quando o campo de direção de sincronização Aceitar/Recusar está definido como **[!UICONTROL Unidirectional (Campaign to Microsoft Dynamics 365)]** ou **[!UICONTROL Bidirectional]**. Você pode definir quais campos no Microsoft Dynamics 365 são mapeados para quais entradas no Adobe Campaign.

Os nomes de campo do Microsoft Dynamics 365 incluem todos do tipo **booleano**.

Os nomes de campo do Adobe Campaign são um conjunto fixo de valores específicos para aceitação/recusa. Os nomes de campo do Adobe Campaign são um conjunto fixo de valores específicos para aceitação/recusa. **Não é possível alterar o conjunto de valores desta lista**.
