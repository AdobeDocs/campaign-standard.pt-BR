---
solution: Campaign Standard
product: campaign
title: Gerenciamento de dados do Campaign e do Microsoft Dynamics 365
description: Saiba como o Campaign Standard e o Microsoft Dynamics 365 gerenciam dados comuns
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '2473'
ht-degree: 1%

---


# Práticas recomendadas e limitações {#acs-msdyn-best-practices}

## Gerenciar dados {#acs-msdyn-manage-data}

Para sincronização de entidade de contato e personalizada, essa integração trata o **Microsoft Dynamics 365 como a fonte da verdade**.  Quaisquer alterações nos atributos sincronizados devem ser feitas no Dynamics 365 e não no Adobe Campaign Standard).  Se as alterações forem feitas no Campaign, elas poderão eventualmente ser substituídas no Campaign durante a sincronização, pois a sincronização está em uma direção.

A integração pode ser configurada opcionalmente para emitir chamadas de exclusão de perfil para o Campaign quando um contato for excluído no Dynamics 365 para ajudar a manter a integridade dos dados. No entanto, uma exclusão de perfil é diferente de uma exclusão de privacidade. Uma exclusão de privacidade no Campaign removerá o registro do perfil do Campaign e as entradas de log associadas; enquanto, uma exclusão de perfil regular excluirá apenas o registro do perfil do Campaign, deixando os remanescentes para trás nos logs do Campaign. Se o recurso de exclusão de perfil estiver ativado na integração, etapas adicionais precisarão ser seguidas para processar corretamente as solicitações de privacidade do titular de dados. Consulte as etapas na seção [Privacidade abaixo](#manage-privacy-requests).

## Privacidade{#acs-msdyn-manage-privacy}

Essa integração foi projetada para transferir dados do usuário final entre o Microsoft Dynamics 365 e o Adobe Campaign Standard. Esses dados incluem informações pessoais se estiverem contidos nos dados do usuário final.  Como controlador de dados, sua empresa é responsável por seguir todas as leis e regulamentos de privacidade aplicáveis à sua coleta e uso de dados pessoais.

Essa integração foi projetada para transferir dados do usuário final (incluindo, mas não se limitando a, informações pessoais, se contidas nos dados do usuário final), entre o Microsoft Dynamics 365 e o Adobe Campaign Standard. Como controlador de dados, sua empresa é responsável por seguir todas as leis e regulamentos de privacidade aplicáveis à sua coleta e uso de dados pessoais.

A integração não emite nenhuma privacidade do titular dos dados (por exemplo, o GDPR) exclui ou lida com outras solicitações de privacidade (com exceção da recusa). Ao processar solicitações de privacidade, você deve fazê-lo no Microsoft Dynamics 365 e no Campaign (por meio da Adobe Experience Platform Privacy Service), independentemente.

Se você configurou a integração para emitir chamadas regulares de exclusão de perfil para o Campaign quando um contato é excluído no Dynamics 365, as etapas abaixo devem ser seguidas. Certifique-se de que não sejam feitas atualizações no registro em questão durante esse processo.

1. Emita solicitação de exclusão de privacidade para [Adobe Experience Platform Privacy Service](https://www.adobe.io/apis/experiencecloud/gdpr.html)

1. Monitorar solicitação até que seja concluída com êxito

1. Verifique se o registro não está mais em sua instância do Campaign

1. (Logo após) Problema de exclusão de privacidade no Dynamics 365

1. Verifique se o registro foi removido de ambos os sistemas

Abaixo estão os links para ajudar a orientá-lo na implementação de solicitações de acesso e/ou de exclusão de privacidade em cada sistema:

* [Microsoft Dynamics 365](https://docs.microsoft.com/en-us/dynamics365/get-started/gdpr/)

* [Adobe Campaign Standard](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html)

>[!IMPORTANT]
>
>Se qualquer registro de recurso personalizado do Campaign contiver informações pessoais, aplicáveis ao uso do Campaign por um cliente, esse registro deverá ser vinculado a um registro de perfil do Campaign correspondente (diretamente ou por meio de outro recurso personalizado), de modo que uma exclusão relacionada à privacidade no registro de perfil também possa excluir o registro de recurso personalizado vinculado contendo informações pessoais; as opções de vinculação e exclusão entre as entidades devem ser configuradas para permitir essa remoção em cascata dos registros vinculados. As informações pessoais não devem ser inseridas em um recurso personalizado que não esteja vinculado ao perfil.

## Rejeitar {#opt-out}

Devido às diferenças nos atributos de opt out entre o Microsoft Dynamics 365 e o Campaign, e às diferenças nas necessidades de negócios de cada cliente, o mapeamento de opt out foi deixado como um exercício para o cliente concluir.  É importante garantir que as opções de não participação sejam mapeadas corretamente entre sistemas para que as preferências de não participação do usuário final sejam mantidas e eles não recebam uma comunicação por meio de um canal do qual tenham optado.

Esteja ciente de que somente as seguintes opções podem ser usadas em mapeamentos de recusa:

* Atributos de campanha com o prefixo &quot;Não entrar em contato mais por&quot; (por exemplo, Não entrar em contato mais por email) ou

* o atributo específico para CCPA

Mais informações sobre os campos de entidade do Perfil podem ser encontradas [aqui](../../developing/using/datamodel-profile.md).

No Dynamics 365, a maioria dos campos de opção de não participação tem o prefixo &quot;ponto a ponto&quot;. No entanto, também é possível utilizar outros atributos para fins de não participação, se os tipos de dados forem compatíveis.

Ao provisionar a integração, você terá a oportunidade de especificar qual configuração de opção de não participação é necessária para sua empresa:

* **Unidirecional (Microsoft Dynamics 365 para Campaign)**: O Dynamics 365 é fonte de verdade para opções de rejeição. Os atributos de rejeição serão sincronizados em uma direção do Dynamics 365 para o Campaign Standard
* **Unidirecional (Campanha para Microsoft Dynamics 365)**: O Campaign Standard é a fonte de verdade para opções de não participação. Os atributos de rejeição serão sincronizados em uma direção do Campaign Standard para o Dynamics 365
* **Bidirecional**: O Dynamics 365 E o Campaign Standard são ambas fontes de verdade. Os atributos de rejeição serão sincronizados bidirecionalmente entre o Campaign Standard e o Dynamics 365

Como alternativa, se você tiver um processo separado para gerenciar a sincronização de opt-out entre os sistemas, o fluxo de dados de opt-out da integração poderá ser desativado.

A configuração de recusa bidirecional usa a lógica para determinar qual valor gravar em ambos os sistemas. A lógica compara os carimbos de data e hora entre os dois sistemas (alteração no nível do registro no Dynamics 365, alteração no nível do atributo no Campaign) para determinar qual sistema prevalece. Se o Campaign contiver o carimbo de data e hora mais recente, o valor Campaign prevalecerá. Se o Dynamics 365 contiver o carimbo de data e hora mais recente ou se forem iguais, opt out=TRUE vencerá (presumindo que um dos valores seja TRUE).

Saiba como selecionar opções de aceitação/rejeição em [nesta seção](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf).

>[!NOTE]
>
>Revise e, se apropriado, atualize as regras de tipologia padrão e específicas no Adobe Campaign antes de fazer alterações aqui para garantir que essas alterações sejam aplicadas corretamente a todas as comunicações de saída. Por exemplo, verifique se os mapeamentos para preferências de recusa refletem com precisão as opções de intenção/comunicação do recipient e não interrompem inadvertidamente o delivery de mensagens de relacionamento ou transacionais, como confirmações de ordem do cliente.

Se você selecionou a configuração de rejeição **Bidirecional** ou **Unidirecional (Campanha para Microsoft Dynamics 365)**, os dados de recusa da campanha serão exportados periodicamente via workflow para a área de armazenamento SFTP da campanha (consulte &quot;Uso do SFTP da campanha abaixo&quot;). Caso os workflows de opt-out do Campaign parem de ser executados, será necessário reiniciar manualmente o mais rápido possível para reduzir a possibilidade de sincronizações de opt-out perdidas.

>[!IMPORTANT]
>
>Se você precisar da configuração de opção **Bidirecional** ou **Unidirecional (Campaign para Microsoft Dynamics 365)**, será necessário fazer a solicitação ao contato técnico do Adobe para que os workflows de opt-out sejam configurados na instância do Campaign

## Uso de SFTP da campanha

O armazenamento SFTP do Campaign precisará ser utilizado pela integração nos casos de uso abaixo.  Você precisará garantir que sua conta SFTP tenha capacidade de armazenamento adequada para acomodar esses casos de uso. Exceder a capacidade de armazenamento SFTP licenciada pode prejudicar seriamente o uso funcional do Campaign, a integração e/ou a conta SFTP.

| Caso de uso | Descrição |
|---|---|
| Bidirecional e Unidirecional (Campaign para Microsoft Dynamics 365) | Os fluxos de dados de rejeição bidirecional e unidirecional (Campaign para Microsoft Dynamics 365) utilizarão o armazenamento SFTP da campanha. Um fluxo de trabalho do Campaign exportará alterações adicionais para a pasta SFTP. A partir daí, a integração selecionará os registros e o processo. |
| Logs de rejeição | Os logs de saída do conector serão úteis ao solucionar problemas da integração. Os logs de saída podem ser ativados/desativados. |


>[!IMPORTANT]
>
>Você é responsável pelas informações que acessa e baixa das pastas SFTP. Se as informações contiverem dados pessoais, você será responsável por seguir todas as leis e regulamentos de privacidade aplicáveis. [Saiba mais](#acs-msdyn-manage-privacy).

## Gerenciamento de dados

### Dados existentes do Campaign

Essa integração sincronizará contatos e entidades personalizadas do Microsoft Dynamics 365 para o Campaign. Os registros de campanha criados fora da integração (ou seja, não criados pelo trabalho de sincronização) não serão modificados pela integração, incluindo registros do Campaign existentes no momento da configuração da integração.

Como essa integração usa o campo **[!UICONTROL externalId]** no Campaign para sincronizar registros de perfil do Campaign com registros de contato do Dynamics 365, esse campo do Campaign (**[!UICONTROL externalId]** ) deve ser preenchido com o Microsoft Dynamics 365 **[!UICONTROL contactId]** para os registros que você deseja sincronizar do Microsoft Dynamics 365.  As entidades personalizadas também são sincronizadas usando uma ID exclusiva do Microsoft Dynamics 365. A entidade personalizada Campanha precisará incluir esse atributo de ID como uma coluna de tabela. A coluna externalId pode ser usada para armazenar esse valor de atributo, mas não é necessária para entidades personalizadas do Campaign.

Lembre-se de que o Microsoft Dynamics 365 ainda é a fonte da verdade e que os dados do perfil do Campaign podem ser substituídos, pois a integração detecta atualizações no lado do Dynamics 365.  Também pode haver outras etapas necessárias para habilitar a integração, dependendo da implantação existente; portanto, é recomendável trabalhar em conjunto com o contato técnico do Adobe.

>[!NOTE]
>
>Devido à complexidade das implantações existentes do cliente, é recomendável trabalhar com o contato técnico do Adobe ao planejar e configurar a integração.

### Frequência de sincronização de dados

A integração utiliza uma arquitetura que permite que as atualizações sejam detectadas e adicionadas à &quot;fila&quot; de processamento logo após sua ocorrência no Microsoft Dynamics 365 (ou seja, streaming, e não processamento em lote). Por isso, não há necessidade de especificar frequências ou programações de execução do fluxo de dados.

A exceção a isso são os fluxos de dados de recusa bidirecionais e do Campaign para o Dynamics 365. Para essas configurações de opt-out, os registros atualizados do Campaign são exportados para SFTP por meio de um workflow do Campaign uma vez por dia, depois que a ferramenta de integração lê o arquivo e processa o registro.

### Contrato de uso de dados

Se você estiver localizado em regiões da EMEA ou APAC, alguns de seus dados serão processados nos EUA como parte dessa integração. Para saber mais, consulte [esta seção](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

## Medidas de proteção e limitações

>[!IMPORTANT]
>
>Determinadas ações de sua parte (por exemplo, assimilação inicial de registros, repetição de dados de registro etc.) pode resultar na assimilação de um grande número de registros do Microsoft Dynamics 365 para sua instância do Adobe Campaign. Para reduzir o risco de problemas de desempenho, é recomendável interromper todos os processos do Campaign (por exemplo, sem atividade de marketing, sem execução de workflows etc.) até que a grande carga de registros tenha sido assimilada no Campaign.

### Entidades personalizadas

A [integração do Microsoft Dynamics 365-Adobe Campaign Standard](../../integrating/using/d365-acs-get-started.md) oferece suporte a entidades personalizadas, permitindo que entidades personalizadas no Dynamics 365 sejam sincronizadas com recursos personalizados correspondentes no Campaign.

A integração oferece suporte a tabelas vinculadas e não vinculadas.

Ao configurar fluxos de dados de entidade personalizados, é importante estar ciente do seguinte:

* A criação e a modificação de recursos personalizados do Campaign são operações confidenciais que devem ser executadas apenas por usuários especialistas.
* Para fluxos de dados de entidade personalizados, o rastreamento de alterações deve ser ativado no Dynamics 365 para entidades personalizadas sincronizadas.
* Se um registro pai e um registro filho vinculado forem criados próximo ao mesmo tempo no Dynamics 365, devido ao processamento paralelo da integração, há uma pequena chance de que um novo registro filho possa ser gravado no Campaign antes de seu registro pai.

* Se o pai e o filho estiverem vinculados no lado da Campanha usando a opção **1 cardinality simple link**, o registro filho permanecerá oculto e inacessível (via interface do usuário ou API) até que o registro pai chegue ao Campaign.

* (Considerando **1 cardinality simple link** no Campaign) Se o registro filho for atualizado ou excluído no Dynamics 365 e essa alteração for gravada no Campaign antes que o registro pai seja exibido no Campaign (não é provável, mas uma possibilidade remota), essa atualização ou exclusão não será processada no Campaign e um erro será lançado. No caso de atualização, o registro em questão precisará ser atualizado novamente no Dynamics 365 para sincronizar o registro atualizado. No caso de exclusão, o registro em questão precisará ser tratado separadamente no lado da campanha, pois não há mais um registro no Dynamics 365 para excluir ou atualizar.

* Se você encontrar uma situação em que acredita ter registros secundários ocultos e nenhuma maneira de acessá-los, poderá alterar temporariamente o tipo de link de cardinalidade para **0 ou 1 cardinality simple link** para acessar esses registros.

Uma visão geral mais abrangente dos recursos personalizados do Campaign pode ser encontrada [nesta seção](../../developing/using/key-steps-to-add-a-resource.md).

### Medidas de proteção de integração

As seguintes medidas de proteção devem ser tomadas em consideração ao planejar utilizar essa integração. Entre em contato com o representante técnico do Adobe se achar que você está excedendo essas grades de proteção.

* Você precisará licenciar o pacote do Campaign correto para suportar o volume de chamada do mecanismo gerado pela integração. Exceder o volume de chamada do mecanismo licenciado pode causar uma degradação no desempenho do Campaign.

   Use o seguinte para ajudar a estimar o volume de chamadas do mecanismo da integração:

   * Inserções de registro (ou seja, novo registro): 1 chamada de motor
   * O registro exclui: 1 chamada de motor
   * Atualizações de registro: 2 chamadas de mecanismo (somente 1 chamada se o registro de destino for idêntico ao registro de origem - ou seja, se não houver alteração no registro do Campaign)

   Ao estimar o volume geral de chamadas do mecanismo do Campaign, é importante considerar outras fontes de chamadas do mecanismo, incluindo landing pages, WebApps, JSSP, APIs, registros de aplicativos móveis etc.

   Veja as informações do pacote do Campaign aqui: https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html

* A integração oferece suporte a no máximo 30 milhões de contatos.

* A oferta de integração padrão inclui suporte para até cinco entidades personalizadas, cada uma com um máximo de 50 colunas em tamanho.

* Será necessário criar e publicar os recursos personalizados antes de implementar a integração.

* A profundidade máxima da tabela ao vincular tabelas é de dois (ou seja, tabela1->tabela2->tabela3)

* Há suporte limitado para os tipos de dados do Microsoft Dynamic 365. Se o modelo de dados contiver um tipo de dados diferente dos tipos simples de dados (por exemplo, sequências, números inteiros, decimais, etc.), talvez seja necessário atualizar o modelo de dados antes de usar a integração.

* Se você optar por preservar os dados existentes nas entidades personalizadas do Campaign, será necessário preparar os dados para a integração.

* Talvez seja necessário estabelecer janelas de manutenção de integração entre o Adobe e o cliente.

* Esteja ciente de que aumentos ou &quot;picos&quot; significativos no uso da integração (por exemplo, aumento acentuado em registros novos ou atualizados) podem causar lentidão na sincronização de dados.

* Como parte da integração, você deve concluir as etapas de configuração de pré-integração no Microsoft Azure e Dynamics 365. Veja as etapas de configuração [nesta página](../../integrating/using/d365-acs-configure-d365.md)

* Espera-se que você traga seus modelos de dados do Dynamics 365 e do Campaign para a integração e os mantenha.

### Limites de integração

A integração foi projetada para resolver o caso de uso geral de movimentação de dados comum entre o Microsoft Dynamics 365 e o Campaign, mas não se destina a abordar todos os casos de uso específicos de cada cliente:

* A integração não emite privacidade (por exemplo, o GDPR). A responsabilidade de atender às solicitações de privacidade do usuário final cabe ao cliente; essas solicitações devem ser feitas independentemente no Campaign (via Adobe Experience Platform Privacy Service) e no Dynamics 365. A integração pode emitir exclusões regulares para ajudar na sincronização de dados, se desejado.   Revise [a seção Privacidade](#manage-privacy-requests) para obter mais informações.

* Nenhum dado de perfil ou entidade personalizada será sincronizado do Campaign para o Dynamics 365, com exceção das informações de recusa (se configuradas pelo cliente).

* O gerenciamento de assinaturas da campanha (ou seja, assinaturas/unsubscribes) não é nativamente suportado.

* Não há suporte para a composição e o acionamento das campanhas de email do Campaign a partir do Dynamics 365.

* A integração **não** oferece suporte à remodelagem de dados entre os modelos de dados Dynamics 365 e Campaign Standard. Espera-se que a integração sincronize uma tabela do Dynamics 365 com uma tabela do Campaign.
