---
title: Sobre a integração do Campaign-Experience Manager
description: Com a integração do Adobe Experience Manager, você pode criar conteúdo diretamente no AEM e usá-lo posteriormente no Adobe Campaign.
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a1bc9d23163d12517c4501a572fc92aac6aacbc6

---


# Mapear recursos personalizados da Campanha e entidades personalizadas do Dynamics 365

Saiba como mapear recursos personalizados e entidades personalizadas no contexto da integração entre o Adobe Campaign Standard e o Microsoft Dynamics 365.

## Pré-requisitos

A nova versão da integração [do](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md) Microsoft Dynamics 365-Adobe Campaign Standard oferece suporte para entidades personalizadas.  Isso permite que as entidades personalizadas no Dynamics 365 sejam replicadas para os recursos personalizados correspondentes na Campanha.

Depois de replicados, os novos dados nos recursos personalizados podem ser usados para vários fins, incluindo segmentação e personalização.

>[!CAUTION]
>
>Se qualquer registro de recurso personalizado de Campanha contiver informações pessoais, aplicáveis à utilização de Campanhas por um cliente, tais registros devem ser ligados a um registro de perfil de Campanha correspondente (diretamente ou através de outro recurso personalizado), de modo a que uma exclusão relacionada com a privacidade no registro de perfis possa também eliminar o registro de recursos personalizados que contém informações pessoais; as opções de vinculação e exclusão entre as entidades devem ser configuradas para permitir essa remoção em cascata dos registros vinculados. As informações pessoais não devem ser inseridas em um recurso personalizado que não esteja vinculado ao perfil.

Uma visão geral mais abrangente dos recursos personalizados da Campanha pode ser encontrada [neste link](../../developing/using/key-steps-to-add-a-resource.md).

Para configurar a integração para entidades personalizadas, entre em contato com [adobe-support@unifisoftware.com](mailto:adobe-support@unifisoftware.com) para solicitar que isso seja feito.  O Unifi exigirá os nomes das tabelas de entidade personalizadas em ambos os sistemas, bem como os mapeamentos de atributo desejados.  O Unifi criará as ordens de produção e programações correspondentes.

Um exemplo de uso de suporte personalizado de entidade pode ser visto na seção [Caso de](../../integrating/using/map-campaign-custom-resources-and-dynamics-365-custom-entities.md#UC)uso.

>[!CAUTION]
>
>* Os recursos personalizados publicados antes da versão de Campaign Standard 19.4 **precisam ser republicados** para serem usados na integração.
>* Criar e modificar recursos personalizados do Campaign Standard são operações confidenciais que devem ser executadas somente por usuários especialistas.


## Caso de uso


### Estado inicial

O cliente tem um veículo de entidade personalizado predefinido no Dynamics 365 e um veículo de recurso personalizado correspondente predefinido no Campaign Standard.  O cliente forneceu detalhes personalizados de mapeamento de entidade para Unifi, e o Unifi configurou as ordens de produção e agendamentos para o recurso personalizado Veículo, no Unifi.

|   | Microsoft Dynamics 365 | Adobe Campaign Standard | Observações |
|---|---|---|---|
| Entidade de nível superior | Contato | Perfil | Entidades padrão e inovadoras |
| Entidade vinculada | Veículo - nova entidade personalizada | Veículo - novo recurso personalizado | Novas entidades personalizadas |
| Tipo de link | Vinculação dos pais ao contato com N:1 | Semelhante ao Dynamics 365 - consulte a seção Campanha abaixo para obter detalhes |   |

### Configuração no Dynamics 365

As entidades personalizadas deste cliente no Dynamics 365 podem ser visualizadas no Painel de vendas clicando na lista suspensa ao lado do Dynamics 365.  As entidades personalizadas deste cliente são agrupadas em **[!UICONTROL Extensions]**.

(../assets/SalesDashboard.png)

Os dados do veículo podem ser visualizados clicando-se na entidade **[!UICONTROL vehicle]** personalizada.  Veja a lista dos veículos abaixo.

(../assets/VehicleCustomEntity.png)

A relação da **[!UICONTROL vehicle]** entidade com a **[!UICONTROL Contact]** entidade pode ser vista abaixo. **[!UICONTROL Parental]** foi escolhido para o **[!UICONTROL Type of Behavior]**.

(../assets/ContactToVehicle.png)

### Configuração no Campaign Standard

Na Campanha, os recursos personalizados do cliente podem ser exibidos clicando-se **[!UICONTROL Adobe Campaign]** no canto superior esquerdo e selecionando-se **[!UICONTROL Client data]**.

(../assets/ClientDataMenu.png)

### Mapear recursos personalizados e entidades personalizadas

O recurso **[!UICONTROL vehicle]** personalizado deveria ter sido predefinido anteriormente pelo cliente e deve aparecer nos dados do cliente; no entanto, nós iremos percorrer as etapas da criação deste recurso **[!UICONTROL vehicle]** personalizado abaixo.

Clique **[!UICONTROL Adobe Campaign]** no canto superior esquerdo e clique em **[!UICONTROL Administration > Development > Custom Resources]**.

(../assets/CustomRes.png)

1. Clique em **[!UICONTROL Custom Resources]**.
1. Clique no botão **[!UICONTROL Create]**.  Isso abrirá uma janela pop-up.
1. Selecione **[!UICONTROL Create a new resource]** e insira **[!UICONTROL Vehicle]** como o rótulo e a ID.
1. Clique em **[!UICONTROL Create]**.

(../assets/CreateAcusRes.png)

A Campanha exibirá as estruturas de dados e a página de link.  É possível ver que vários campos foram adicionados.

* A identificação do veículo é o identificador único da **[!UICONTROL Vehicle]** entidade; sua ID deve ser exatamente **[!UICONTROL externalId]**, como mostrado abaixo, para que a integração funcione.
* O Perfil associado é a identificação do perfil ao qual o registro de veículos está ligado; quando vinculado, ele será vinculado ao **[!UICONTROL externalId]** campo da tabela do Perfil.
* VIN e nome do veículo são campos para capturar informações sobre o veículo.

(../assets/CusResConfig.png)

>[!CAUTION]
>
>Cada recurso personalizado deve ter um campo exclusivo com uma ID de externalId (exatamente).  Esse campo mapeará para o campo ID do recurso personalizado no Dynamics 365 (consulte abaixo).

(../assets/FieldsInDynamics.png)

### Definir as chaves de identificação

A próxima etapa é definir as chaves de identificação.  Primeiro, crie as chaves de identificação, como visto abaixo.

(../assets/IDkeys.png)

Na tela Definição de chave, selecione o **[!UICONTROL externalId]** campo.

(../assets/KeyDefinition.png)

>[!CAUTION]
>
>Cada recurso personalizado deve ter uma chave de identificação com um Caminho de &quot;externalId&quot; (exatamente).

### Definir o filtro

A próxima etapa é especificar a definição do filtro.

Em **[!UICONTROL Filter Definition]**, clique em **[!UICONTROL Add an element]**.\
Dê o nome ao rótulo e à ID **[!UICONTROL ExternalId]**.
Clique em **[!UICONTROL Add]**.

(../assets/FilterDefinition.png)

Agora, clique em editar no elemento de filtro recém-adicionado e configure o filtro de acordo com a imagem abaixo.  Se você inserir **[!UICONTROL externalId]** no **[!UICONTROL Parameters]** campo e clicar no sinal de mais, **[!UICONTROL externalId_parameter]** será exibido.  Selecione esse parâmetro como parâmetro.

(../assets/EditArule.png)

### Definir o link

Em seguida, especificaremos a vinculação do recurso personalizado.  Nesse caso, optamos por vincular a entidade **[!UICONTROL Vehicles]** personalizada (origem) à entidade perfis (público alvo) usando um **[!UICONTROL 1 cardinality simple link]**.

(../assets/DefineTheLink.png)

1. Na **[!UICONTROL Link definitions]** tela, escolha a opção Excluir: **[!UICONTROL Deleting the target record implies deleting records referenced by the link]**. Escolhemos essa opção para que, quando um perfil for excluído, todos os **[!UICONTROL Vehicle]** registros vinculados a esse perfil também sejam excluídos.
1. Em **[!UICONTROL Join Definitions]**, selecione **[!UICONTROL Define specific join conditions]**.
1. Then click **[!UICONTROL Add an element]**.

(../assets/LinkConfiguration.png)

Para a definição de junção, inserimos os valores abaixo.

Observe que a **[!UICONTROL @externalId]** entrada é o campo externalId da tabela de perfis e a **[!UICONTROL ProfileExternalId]** entrada é a ID do campo correspondente no recurso personalizado de veículos.  Quando o valor externoId de um registro de perfis for inscrito no **[!UICONTROL ProfileExternalId]** campo de um registro de um veículo, os dois registros serão ligados em conjunto.

(../assets/JoinDefinition.png)

Confirme as alterações e salve a entidade personalizada.

### Publicar e verificar atualizações

A etapa final é publicar o recurso personalizado.

1. Clique em **[!UICONTROL Adobe Campaign]** no canto superior esquerdo e clique em **[!UICONTROL Administration > Development > Publishing]**.
1. Manter a opção padrão: **[!UICONTROL Determine modifications since the last publication]**.
1. Clique **[!UICONTROL Prepare Publication]** e aguarde a conclusão.

(../assets/PublishModifications.png)

Em seguida, clique **[!UICONTROL Publish]** e aguarde a conclusão.

(../assets/Publish.png)

### Agendamento de ingresso unificado

Presumindo que o cliente já preencheu a entidade personalizada de veículo no Dynamics 365 e que o Unifi configurou as tarefas e programações da entidade personalizada de veículos com o, o cliente deverá ser capaz de iniciar o agendamento de entrada para a entidade de veículo.

(../assets/Schedule.png)

Após a conclusão do serviço de entrada, os dados do veículo agora podem ser vistos no recurso **[!UICONTROL Vehicle]** personalizado recém-preenchido na Campanha.

(../assets/ACSUpdate.png)

**Tópicos relacionados**

* Trabalhar com o Adobe Campaign Standard - Microsoft Dynamics 365
* Etapas principais para adicionar um recurso personalizado na Campanha
