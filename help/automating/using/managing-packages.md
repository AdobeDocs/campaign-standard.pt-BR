---
title: Gerenciamento de pacotes
seo-title: Gerenciamento de pacotes
description: Gerenciamento de pacotes
seo-description: Os administradores podem definir pacotes para trocar recursos entre diferentes instâncias do Adobe Campaign por meio de arquivos XML estruturados.
page-status-flag: nunca ativado
uuid: d 041 f 549-bfc 5-4 e 6 b -87 bf-a 63 c 7 c 224 bca
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizando
content-type: reference
topic-tags: importar e exportar dados
discoiquuid: c 3015 cdc -8432-4 e 57-8 ac 0-43 ae 7827 e 3 b 0
context-tags: Packagedef, visão geral; Packageinstall, Main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Managing packages{#managing-packages}

Os administradores podem definir pacotes para trocar recursos entre diferentes instâncias do Adobe Campaign por meio de arquivos XML estruturados. Eles podem ser parâmetros de configuração ou dados.

Isso pode ser útil para transferir dados de um servidor para outro ou para replicar a configuração de uma instância.

Packages are available under the **[!UICONTROL Administration]** &gt; **[!UICONTROL Deployment]** &gt; **[!UICONTROL Package exports]** or **[!UICONTROL Package imports]** menus. Os dois menus funcionam da mesma forma.

Os elementos de cada lista são exibidos por padrão de acordo com sua data de modificação ou instalação, do mais recente ao menos recente.

![](assets/packages_1.png)

Para exibir e modificar o conteúdo de um elemento, clique em seu rótulo. Refer to the [Exporting a package](../../automating/using/managing-packages.md#exporting-a-package) and [Importing a package](../../automating/using/managing-packages.md#importing-a-package) sections.

## Package exports {#package-exports}

### Standard packages {#standard-packages}

**[!UICONTROL Platform]** e **[!UICONTROL Administration]** são dois pacotes incorporados, cada um contendo uma lista predefinida de recursos a serem exportados. Eles podem ser abertos no modo somente leitura e são adequados para exportação.

![](assets/packages_14.png)

>[!CAUTION]
>
>Exportar pacotes não é autorizado se os recursos exportados tiverem IDs padrão. Portanto, as IDs de recursos exportáveis devem ser alteradas usando um nome diferente dos modelos fornecidos como padrão pelo Adobe Campaign Standard. Por exemplo, para exportar perfis de teste, não é necessário usar uma ID contendo o valor "SDM" ou "sdm". Ao tentar exportar pacotes contendo IDs padrão, você pode ver erros como: " O tipo de entidade'Marcas ' (marca) usa uma ID padrão (' BRD 1 ') que pode causar um conflito ao importar o pacote. Altere esse nome e repita a operação. "

The package export steps are described in the [Exporting a package](../../automating/using/managing-packages.md#exporting-a-package) section.

* **[!UICONTROL Platform]** O pacote reúne todos os recursos adicionados durante a configuração técnica: recursos personalizados, conjuntos de recursos personalizados, acionadores e opções de aplicativo com o **[!UICONTROL System]** tipo.
* **[!UICONTROL Administration]** O pacote reúne todos os objetos adicionados durante a configuração de negócios, como: modelos de campanha, modelos de conteúdo, modelos de entrega, modelos de página de aterrissagem, modelos de programa e modelos de fluxo de trabalho.

   It also includes the following objects: content blocks, target mappings, external accounts, organizational units, application options with the **[!UICONTROL User]** type, roles, typologies, typology rules and users.

>[!NOTE]
>
>O conteúdo desses dois pacotes não me pode ser modificado. Por outro lado, esses pacotes sempre contêm os dados mais atualizados disponíveis. You can [create your own packages](../../automating/using/managing-packages.md#creating-a-package) to export specific elements.

### Creating a package {#creating-a-package}

É necessário criar um pacote se você precisar exportar conjuntos específicos de dados.

Para criar um pacote, você precisa dos direitos de administração.

1. From **[!UICONTROL Administration]** &gt; **[!UICONTROL Deployment]** &gt; **[!UICONTROL Package exports]**, click the **[!UICONTROL Create]** button in the list of package contents.

   O elemento é criado imediatamente. Para cancelar a criação, volte à lista e marque a caixa correspondente para excluí-la.

1. Na tela do conteúdo do pacote, especifique um nome e uma ID.
1. Click the **[!UICONTROL Edit properties]** button if you would like to add a description and restrict access to certain users.

   ![](assets/packages_18.png)

1. Use the **[!UICONTROL Create element]** button in the **[!UICONTROL Export content]** tab to select the resources you wish to export.

   ![](assets/packages_2.png)

1. Os recursos são mostrados em ordem alfabética e podem ser filtrados por nome. Seu nome técnico é exibido entre parênteses. Selecione um elemento na lista e confirme.

   ![](assets/packages_3.png)

1. The resource name is displayed in the **[!UICONTROL Export content]** tab. To modify a resource, check the corresponding box and use the **[!UICONTROL Show detail of the element selected]** button.

   ![](assets/packages_4.png)

1. O uso do editor de consulta permite que você filtre os elementos a serem exportados. For more on this, refer to the [Editing queries](../../automating/using/editing-queries.md#creating-queries) section.

   ![](assets/packages_5.png)

   >[!NOTE]
   >
   >É possível exportar até 5000 objetos por recurso.

1. Após especificar todos os recursos a serem exportados, salve sua seleção.

Seu pacote agora é criado e está pronto para ser exportado.

### Exporting a package {#exporting-a-package}

Exportar um pacote permite salvar um estado específico de um recurso que poderá ser reimportado em outra instância ou posteriormente na mesma instância.

>[!CAUTION]
>
>Exportar pacotes não é autorizado se os recursos exportados tiverem IDs inovadoras. Portanto, as IDs de recursos exportáveis devem ser alteradas usando um nome diferente dos modelos fornecidos como padrão pelo Adobe Campaign Standard. Por exemplo, para exportar perfis de teste, não é necessário usar uma ID contendo o valor "SDM" ou "sdm".

1. From **[!UICONTROL Administration]** &gt; **[!UICONTROL Deployment]** &gt; **[!UICONTROL Package exports]**, select a package to access its detail.
1. Verifique se o pacote contém os dados necessários.
1. Click the **[!UICONTROL Start export]** button.

O arquivo exportado é armazenado na pasta de download do navegador em uso. É chamado automaticamente de "package_xxx.xml", sendo que "xxx" corresponde à ID do pacote.

Quando a operação for concluída, várias seções serão exibidas:

* **[!UICONTROL Export status]**: esta seção mostra se a operação foi realizada corretamente.

   ![](assets/packages_6.png)

* You can consult the different steps of the export via the **[!UICONTROL Log]** tab. Isso contém os status de todas as exportações anteriores.

   ![](assets/packages_7.png)

>[!NOTE]
>
>When selecting an element from the package content list that has already been exported, the **[!UICONTROL Log]** and **[!UICONTROL Last export]** tabs are still available.

## Package imports {#package-imports}

### System updates {#system-updates}

A lista de importação do pacote acima contém as importações automáticas vinculadas às atualizações realizadas pela Adobe.

![](assets/packages_15.png)

**[!UICONTROL Execution logs]** A guia armazena todas as etapas de importação. Um painel lateral exibe as informações gerais.

![](assets/packages_11.png)

>[!NOTE]
>
>Esses elementos estão acessíveis no modo somente leitura.

### Importing a package {#importing-a-package}

Um administrador pode importar manualmente um pacote originado de uma exportação realizada anteriormente a partir de uma instância do Adobe Campaign. For more on this, refer to the [Package exports](../../automating/using/managing-packages.md#package-exports) section.

A importação do pacote manual consiste em duas etapas: primeiro, é necessário carregar um arquivo e, em seguida, importar seu conteúdo.

1. From **[!UICONTROL Administration]** &gt; **[!UICONTROL Deployment]** &gt; **[!UICONTROL Package imports]**, click the **[!UICONTROL Create]** button in the package import list.

   O elemento é criado imediatamente. Para cancelar a criação, volte à lista e marque a caixa correspondente para excluí-la.

1. Especifique um nome e uma ID para a nova importação.
1. Select the file you wish to upload by dragging and dropping it, or by clicking the **[!UICONTROL Select from folder]** link.

   Os arquivos importados devem ser XML ou ZIP (contendo um arquivo XML).

   ![](assets/packages_16.png)

   >[!NOTE]
   >
   >Para substituir o documento carregado, comece excluindo o arquivo por meio do ícone X à direita do nome e repita a operação.

1. Once the file is uploaded, import its content into the database by using the **[!UICONTROL Start import]** button.

   ![](assets/packages_19.png)

Quando a operação for concluída, várias seções serão exibidas:

* **[!UICONTROL Import status]**: esta seção mostra se a operação foi realizada corretamente.
* You can consult the different steps of the import via the **[!UICONTROL Execution logs]** tab. Isso é particularmente importante para exibir erros.

   ![](assets/packages_20.png)

Depois que um pacote é importado, não é possível importá-lo novamente do mesmo elemento. Você só pode modificar seu rótulo e ID.

Para importar novamente o mesmo pacote, volte à lista de importação do pacote, crie um elemento e carregue o arquivo selecionado novamente.
