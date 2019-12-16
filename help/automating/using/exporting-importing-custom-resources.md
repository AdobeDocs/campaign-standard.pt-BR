---
title: Exportar / importar recursos personalizados
description: Este tutorial explica como exportar e importar um pacote de recursos personalizados.
page-status-flag: never-activated
uuid: 631f0fbd-9e8d-4f77-a338-fcb7f4fc1774
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: a06509f9-4731-4187-b43d-3bfa361284d3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b10a4b3a81d676e279a9514530158286d58db813

---


# Exportar / importar recursos personalizados {#exporting-importing-custom-resources}

Este tutorial explica como exportar e importar um pacote de recursos personalizados de um ambiente de desenvolvimento para um ambiente de produção.

Este exemplo destina-se aos administradores funcionais vinculados ao Adobe Campaign.

Os pré-requisitos são:

* **Um ou vários recursos** personalizados que estão disponíveis e publicados.

   Além disso, você deve ter definido uma chave exclusiva para esses recursos, pois as chaves primárias automáticas não são exportadas nos pacotes. O recurso pode, portanto, ter uma chave primária e uma chave única adicional para garantir a exclusividade dos registros.
* **Os direitos** necessários para criar e exportar um pacote.

Recursos adicionais:

* [Gerenciamento de pacotes](../../automating/using/managing-packages.md)
* [Implantação de pacotes: Princípio de funcionamento](../../developing/using/data-model-concepts.md)
* [Adicionar ou estender um recurso](../../developing/using/key-steps-to-add-a-resource.md)

##  Exportação da estrutura {#exporting-the-structure}

Nesta seção, realizaremos uma primeira exportação de pacote que detalha a estrutura física dos dados de recursos personalizados.

Este exemplo tem dois recursos personalizados: **Produtos** e **pedidos**.

1. Vá para o menu **[!UICONTROL Administration]** / **[!UICONTROL Deployment]** / **[!UICONTROL Package exports]** .

   Vamos criar um novo pacote para exportar os **[!UICONTROL Custom resource (cusResource)]** filtrados com os dois recursos personalizados, "Produtos" e "Pedidos".

1. Na **[!UICONTROL Package exports]** página, clique em **[!UICONTROL Create]** para criar um novo pacote.
1. Preencha o rótulo e clique em **[!UICONTROL Create element]**.

   ![](assets/cusresources_export1.png)

1. Procure e selecione o **[!UICONTROL Custom resource (cusResource)]**.

   ![](assets/cusresources_export2.png)

1. Configure os detalhes do **[!UICONTROL Custom resource]** selecionando os dois recursos, **Produtos** e **Pedidos**, nas condições de filtragem.

   Certifique-se de não esquecer de alterar o operador lógico. O valor deve ser definido como **OU** para que a estrutura do recurso de produtos e do recurso de pedidos sejam integrados no pacote.

   ![](assets/cusresources_export3.png)

1. Confirme e salve a definição do pacote.

Agora você pode clicar em **[!UICONTROL Start export]**.

![](assets/cusresources_export4.png)

O pacote gerado está disponível na pasta Downloads. O nome do arquivo zip é gerado aleatoriamente. Você pode renomeá-lo.

## Exportação dos dados {#exporting-the-data}

Essa segunda exportação nos permitirá exportar os dados dos recursos personalizados **Produtos** e **Pedidos** .

Com base no mesmo tipo de exportação que a exportação da estrutura, você criará um segundo pacote que contém os dados.

1. Na **[!UICONTROL Package exports]** página, clique em **[!UICONTROL Create]** para criar um novo pacote.
1. Preencha o rótulo com **[!UICONTROL Export data of my resources]** e clique **[!UICONTROL Create element]** na **[!UICONTROL Export content]** guia.
1. Procure e selecione o recurso **Produtos** .

   ![](assets/cusresources_exportdata1.png)

1. Configure uma condição **de** filtragem avançada com **@Label NOT NULL**.

   ![](assets/cusresources_exportdata2.png)

1. Verifique a contagem.

   ![](assets/cusresources_exportdata3.png)

1. Repita a mesma operação para o recurso personalizado **Pedidos** .

   ![](assets/cusresources_exportdata4.png)

1. Confirme e salve a definição do pacote.

Agora você pode clicar em **[!UICONTROL Start export]**.

![](assets/cusresources_exportdata5.png)

O pacote gerado está disponível na pasta Downloads. O nome do arquivo zip é gerado aleatoriamente. Você pode renomeá-lo.

## Importação da estrutura {#importing-the-structure}

### Importação do pacote {#importing-the-structure-package}

1. Conecte-se à instância **de** destino na qual deseja importar os pacotes recém-criados.
1. Vá para o menu **[!UICONTROL Administration]** / **[!UICONTROL Deployment]** / **[!UICONTROL Package imports]** para criar um novo pacote para importar o arquivo da primeira exportação.
1. Arraste e solte o arquivo **de** estrutura na zona fornecida para essa finalidade. Os formatos aceitos são ZIP ou XML.

   ![](assets/cusresources_import2.png)

1. Modifique o rótulo, por exemplo, **Importe a estrutura** e clique em **[!UICONTROL Save]**.
1. Click **[!UICONTROL Start import]**.

   ![](assets/cusresources_import3.png)

### Publicar {#publish-structure}

1. Vá para o menu **[!UICONTROL Administration]** / **[!UICONTROL Development]** / **[!UICONTROL Publication]** .
1. Clique em **[!UICONTROL Prepare publication]** e **[!UICONTROL Publish]** para atualizar a instância com os dados dos novos recursos personalizados.
1. As entradas de menu correspondentes ao pacote instalado serão inseridas no **[!UICONTROL Client data]** menu.

   ![](assets/cusresources_import1.png)

## Importação de dados {#importing-the-data}

Nesta seção, vamos **importar os dados** vinculados ao pacote instalado na instância na etapa anterior.

Da mesma forma que para a etapa anterior, divide-se em duas partes: importar o pacote e a publicação.

### Importação do pacote {#importing-the-data-package}

1. Vá para o menu **[!UICONTROL Administration]** / **[!UICONTROL Deployment]** / **[!UICONTROL Package imports]** para criar um novo pacote para importar o arquivo que contém os dados.
1. Arraste e solte o arquivo de dados na zona fornecida para essa finalidade. Os formatos aceitos são ZIP ou XML.
1. Modifique o rótulo, por exemplo "Importar dados", e clique em **[!UICONTROL Save]**.
1. Click **[!UICONTROL Start import]**.

   ![](assets/cusresources_importdata.png)

### Publicar {#publish-data}

1. Vá para o menu **[!UICONTROL Administration]** / **[!UICONTROL Development]** / **[!UICONTROL Publication]** .
1. Clique em **[!UICONTROL Prepare publication]** e **[!UICONTROL Publish]** para atualizar a instância com os dados dos recursos personalizados.
