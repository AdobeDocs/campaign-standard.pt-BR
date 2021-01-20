---
solution: Campaign Standard
product: campaign
title: Campanha e gestão de dados do Microsoft Dynamics 365
description: Saiba como o Campaign Standard e o Microsoft Dynamics 365 gerenciam dados comuns
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
translation-type: tm+mt
source-git-commit: cce30fd5cd3d5d63563d1dab3bb1e7554c26fb3e
workflow-type: tm+mt
source-wordcount: '2467'
ht-degree: 1%

---


# Práticas recomendadas e limitações {#acs-msdyn-best-practices}

## Gerenciar dados {#acs-msdyn-manage-data}

Para sincronização de contatos e entidades personalizadas, essa integração trata **o Microsoft Dynamics 365 como a fonte da verdade**.  Quaisquer alterações nos atributos sincronizados devem ser feitas no Dynamics 365 e não no Adobe Campaign Standard).  Se as alterações forem feitas na Campanha, elas poderão eventualmente ser substituídas na Campanha durante a sincronização, já que a sincronização está em uma direção.

Como opção, a integração pode ser configurada para emitir chamadas de exclusão de perfil para Campanha quando um contato é excluído no Dynamics 365 para ajudar a manter a integridade dos dados. No entanto, uma exclusão de perfil é diferente de uma exclusão de privacidade. Uma exclusão de privacidade na Campanha removerá o registro do perfil da Campanha e as entradas de registro associadas; enquanto que, uma exclusão regular do perfil excluirá apenas o registro do perfil da Campanha, deixando os remanescentes para trás nos registros da Campanha. Se o recurso de exclusão de perfil estiver ativado na integração, outras etapas deverão ser seguidas para processar corretamente as solicitações de privacidade do indivíduo de dados. Consulte as etapas na seção [Privacidade abaixo](#manage-privacy-requests).

## Privacidade{#acs-msdyn-manage-privacy}

Essa integração foi projetada para transferir dados do usuário final entre o Microsoft Dynamics 365 e o Adobe Campaign Standard. Esses dados incluem informações pessoais se estiverem contidos nos dados do usuário final.  Como controlador de dados, sua empresa é responsável por cumprir todas as leis e regulamentos de privacidade aplicáveis à sua coleta e uso de dados pessoais.

Essa integração foi projetada para transferir dados do usuário final (incluindo, mas não se limitando a, informações pessoais, se contidas em seus dados do usuário final), entre o Microsoft Dynamics 365 e o Adobe Campaign Standard. Como controlador de dados, sua empresa é responsável por cumprir todas as leis e regulamentos de privacidade aplicáveis à sua coleta e uso de dados pessoais.

A integração não emite nenhuma privacidade da pessoa de dados (por exemplo, o RGPD) exclui ou lida com outras solicitações de privacidade (com exceção da opção de não participação). Ao processar solicitações de privacidade, você deve fazê-lo no Microsoft Dynamics 365 e na Campanha (via Adobe Experience Platform Privacy Service), independentemente.

Se você configurou a integração para emitir chamadas de exclusão de perfil regulares para Campanha quando um contato é excluído no Dynamics 365, as etapas abaixo devem ser seguidas. Certifique-se de que não sejam feitas atualizações ao registro em questão durante este processo.

1. Emita solicitação de exclusão de privacidade para [Adobe Experience Platform Privacy Service](https://www.adobe.io/apis/experiencecloud/gdpr.html)

1. Monitorar solicitação até que seja concluída com êxito

1. Verifique se o registro não está mais em sua instância de Campanha

1. (Logo após) Problema de exclusão de privacidade no Dynamics 365

1. Verifique se o registro foi removido de ambos os sistemas

Abaixo estão links para ajudá-lo a implementar as solicitações de acesso e/ou excluir privacidade em cada sistema:

* [Microsoft Dynamics 365](https://docs.microsoft.com/en-us/dynamics365/get-started/gdpr/)

* [Adobe Campaign Standard](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html)

>[!IMPORTANT]
>
>Se qualquer registro de recurso personalizado de Campanha contiver informações pessoais, aplicáveis à utilização de Campanhas por um cliente, tais registros devem ser ligados a um registro de perfil de Campanha correspondente (diretamente ou através de outro recurso personalizado), de modo a que uma exclusão relacionada com a privacidade no registro de perfis possa também eliminar o registro de recursos personalizados que contém informações pessoais; as opções de vinculação e exclusão entre as entidades devem ser configuradas para permitir essa remoção em cascata dos registros vinculados. As informações pessoais não devem ser inseridas em um recurso personalizado que não esteja vinculado ao perfil.

## Recusar {#opt-out}

Devido às diferenças nos atributos de opção entre o Microsoft Dynamics 365 e a Campanha, e às diferenças nos requisitos de negócios de cada cliente, o mapeamento de opção de não participação foi deixado como um exercício para o cliente concluir.  É importante garantir que as opções de não participação sejam mapeadas corretamente entre os sistemas para que as preferências de não participação do usuário final sejam mantidas e que eles não recebam uma comunicação por meio de um canal de que tenham opt out.

Esteja ciente de que somente as seguintes opções podem ser usadas em mapeamentos de não participação:

* Atributos de campanha com o prefixo &quot;Não entrar em contato mais por&quot; (por exemplo, Não entrar em contato mais por email) ou

* o atributo específico para CCPA

Para obter mais informações sobre os campos de entidade do Perfil, consulte [here](../../developing/using/datamodel-profile.md).

No Dynamics 365, a maioria dos campos de opção de não participação tem o prefixo &quot;não&quot;, no entanto, você também pode utilizar outros atributos para fins de não participação se os tipos de dados forem compatíveis.

Ao provisionar a integração, você terá a oportunidade de especificar qual configuração de opção de não participação é necessária para sua empresa:

* **Unidirecional (Microsoft Dynamics 365 para Campanha)**: O Dynamics 365 é fonte de verdade para opções. Os atributos de não participação serão sincronizados em uma direção do Dynamics 365 para o Campaign Standard
* **Unidirecional (Campanha ao Microsoft Dynamics 365)**: O Campaign Standard é a fonte da verdade para opções. Os atributos de não participação serão sincronizados em uma direção do Campaign Standard para o Dynamics 365
* **Bidirecional**: O Dynamics 365 E o Campaign Standard são duas fontes de verdade. Os atributos de não participação serão sincronizados bidirecionalmente entre o Campaign Standard e o Dynamics 365

Como alternativa, se você tiver um processo separado para gerenciar a sincronização de não participação entre os sistemas, o fluxo de dados de não participação da integração poderá ser desativado.

A configuração de opção bidirecional usa a lógica para determinar qual valor gravar em ambos os sistemas. A lógica compara os carimbos de data e hora entre os dois sistemas (alteração no nível de registro no Dynamics 365, alteração no nível de atributo na Campanha) para determinar qual sistema prevalece. Se a Campanha contiver o carimbo de data e hora mais recente, o valor da Campanha prevalecerá. Se o Dynamics 365 contiver o carimbo de data e hora mais recente ou se forem iguais, então a opção opt-out=TRUE vencerá (presumindo que um dos valores seja VERDADEIRO).

Saiba como selecionar opções de aceitação/não participação em [esta seção](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf).

>[!NOTE]
>
>Revise e, se apropriado, atualize as regras de tipologia padrão e específicas do Adobe Campaign antes de fazer alterações aqui para garantir que essas alterações sejam aplicadas corretamente a todas as comunicações de saída. Por exemplo, certifique-se de que todos os mapeamentos para preferências de não participação refletem com precisão as opções de intenção/comunicação do recipient e não interrompem inadvertidamente o delivery de relacionamento ou mensagens transacionais, como confirmações de ordem do cliente.

Se você selecionou a **configuração Bidirecional** ou **Unidirecional (Campanha ao Microsoft Dynamics 365)** opção de não participação, os dados de opção de não participação da Campanha serão exportados periodicamente pelo fluxo de trabalho para a área de armazenamento SFTP da Campanha (consulte &quot;Uso SFTP da Campanha abaixo&quot;). No evento de que seus workflows de opção de não participação da Campanha parem de ser executados, será necessário reiniciar manualmente o mais rápido possível para reduzir a possibilidade de sincronizações de opção de não participação.

>[!IMPORTANT]
>
>Se você precisar da configuração de opção **Bidirecional** ou **Unidirecional (Campanha para Microsoft Dynamics 365)**, precisará fazer a solicitação para o contato técnico do Adobe para que os workflows de opção sejam configurados na instância de Campanha

## Uso de SFTP de campanha

Seu armazenamento SFTP de Campanha precisará ser utilizado pela integração nos casos de uso abaixo.  Você precisará garantir que sua conta SFTP tenha capacidade de armazenamento adequada para acomodar esses casos de uso. Exceder a capacidade licenciada do armazenamento SFTP pode prejudicar seriamente o uso funcional da Campanha, da integração e/ou da conta SFTP.

| Caso de uso | Descrição |
|---|---|
| Bidirecional e Unidirecional (Campanha para o Microsoft Dynamics 365) | Os fluxos de dados de opção bidirecional e unidirecional (Campanha para o Microsoft Dynamics 365) utilizarão o armazenamento SFTP Campanha. Um fluxo de trabalho de Campanha exportará alterações incrementais para a pasta SFTP. A partir daí, a integração pegará os registros e o processo. |
| Logs de recusa | Os registros de saída do conector serão úteis ao solucionar o problema da integração. Os logs de saída podem ser ativados/desativados. |


>[!IMPORTANT]
>
>Você é responsável pelas informações que acessa e baixa das pastas SFTP. Se as informações contiverem dados pessoais, você será responsável por seguir as leis e regulamentos de privacidade aplicáveis. [Saiba mais](#acs-msdyn-manage-privacy).

## Gerenciamento de dados

### Dados de Campanha existentes

Essa integração sincronizará contatos e entidades personalizadas do Microsoft Dynamics 365 com a Campaign. Os registros de campanha criados fora da integração (ou seja, não criados pela tarefa de sincronização) não serão modificados pela integração, incluindo registros de Campanha existentes no momento da configuração da integração.

Como essa integração usa o campo **[!UICONTROL externalId]** na Campanha para sincronizar registros de perfis de Campanha com registros de contato do Dynamics 365, esse campo de Campanha (**[!UICONTROL externalId]** ) deve ser preenchido com o Microsoft Dynamics 365 **[!UICONTROL contactId]** para os registros que você deseja sincronizar do Microsoft Dynamics 365.  As entidades personalizadas também são sincronizadas usando uma ID exclusiva do Microsoft Dynamics 365. A entidade personalizada Campanha precisará incluir esse atributo de ID como uma coluna de tabela. A coluna externalId pode ser usada para armazenar esse valor de atributo, mas não é necessária para entidades personalizadas de Campanha.

Lembre-se de que o Microsoft Dynamics 365 ainda é a fonte da verdade e que os dados do perfil da Campanha podem ser sobrescritos à medida que a integração detecta atualizações do lado do Dynamics 365.  Pode haver outras etapas necessárias para habilitar a integração, dependendo da implantação existente; portanto, recomenda-se que você trabalhe em conjunto com seu contato técnico com o Adobe.

>[!NOTE]
>
>Devido à complexidade das implantações de clientes existentes, recomenda-se trabalhar com seu contato técnico do Adobe ao planejar e configurar a integração.

### Frequência de sincronização de dados

A integração utiliza uma arquitetura que permite que as atualizações sejam detectadas e adicionadas à &quot;fila&quot; de processamento logo após sua ocorrência no Microsoft Dynamics 365 (ou seja, streaming, e não processamento em lote). Por isso, não há necessidade de especificar as frequências ou programações de execução do fluxo de dados.

A exceção a isso é a Campanha bidirecional e os fluxos de dados de opção de não participação do Dynamics 365. Para essas configurações de não participação, os registros de Campanha atualizados são exportados para SFTP por meio de um fluxo de trabalho de Campanha uma vez por dia, após o qual a ferramenta de integração lê o arquivo e processa o registro.

### Contrato de uso de dados

Se você estiver localizado em regiões EMEA ou APAC, alguns de seus dados serão processados nos EUA como parte dessa integração. Para saber mais, consulte [esta seção](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

## Garantias e limitações

>[!IMPORTANT]
>
>Determinadas ações de sua parte (por exemplo, assimilação inicial de registros, reprodução de dados de registro etc.) pode resultar na assimilação de um grande número de registros do Microsoft Dynamics 365 para a instância do Adobe Campaign. Para reduzir o risco de problemas de desempenho, recomenda-se interromper todos os processos de Campanha (por exemplo, sem atividade de marketing, sem execução de workflows etc.) até que a grande quantidade de registros tenha sido ingerida em Campanhas.

### Entidades personalizadas

A [integração do Microsoft Dynamics 365-Adobe Campaign Standard](../../integrating/using/d365-acs-get-started.md) oferece suporte a entidades personalizadas, permitindo que as entidades personalizadas no Dynamics 365 sejam sincronizadas com os recursos personalizados correspondentes na Campanha.

A integração suporta tabelas vinculadas e não vinculadas.

Ao configurar fluxos de dados de entidade personalizados, é importante ter em mente o seguinte:

* Criar e modificar recursos personalizados de Campanha são operações confidenciais que devem ser executadas somente por usuários especialistas.
* Para fluxos de dados de entidade personalizados, o rastreamento de alterações deve ser ativado no Dynamics 365 para entidades personalizadas sincronizadas.
* Se um registro pai e filho vinculado forem criados perto da mesma hora no Dynamics 365, devido ao processamento paralelo da integração, há uma pequena chance de que um novo registro filho possa ser gravado na Campanha antes de seu registro pai.

* Se o pai e o filho estiverem vinculados na Campanha usando a opção **1 cardinality simple link**, o registro filho permanecerá oculto e inacessível (por UI ou API) até que o registro pai chegue na Campanha.

* (Assumindo que **1 cardinality simple link** na Campanha) Se o registro filho for atualizado ou excluído no Dynamics 365 e essa alteração for gravada na Campanha antes que o registro pai seja exibido na Campanha (não é provável, mas uma possibilidade remota), essa atualização ou exclusão não será processada na Campanha e um erro será lançado. Em caso de atualização, o registro em questão terá de ser atualizado novamente no Dynamics 365 para sincronizar o registro atualizado. Em caso de supressão, o registro em questão terá de ser tratado separadamente do lado da Campanha, uma vez que já não existe um registro no Dynamics 365 para eliminar ou atualizar.

* Se você encontrar uma situação em que acredita ter ocultado registros secundários e não ter como acessá-los, é possível alterar temporariamente o tipo de link de cardinalidade para **0 ou 1 simples de cardinalidade** para acessar esses registros.

Uma visão geral mais abrangente dos recursos personalizados da Campanha pode ser encontrada [nesta seção](../../developing/using/key-steps-to-add-a-resource.md).

### Garantias de integração

Ao planejar utilizar essa integração, devem ser tidos em conta os seguintes aspectos: Consulte o seu representante técnico de Adobe, caso acredite que você excede esses guardadores.

* Você precisará licenciar o pacote de Campanha adequado para suportar o volume de chamada do mecanismo gerado pela integração. Exceder o volume de chamada do motor licenciado pode causar uma degradação do desempenho da Campanha.

   Use o seguinte para ajudar a estimar o volume de chamada do mecanismo da integração:

   * Inserções de registros (ou seja, novo registro): 1 chamada de motor
   * Exclusão de registro: 1 chamada de motor
   * Registrar atualizações: 2 chamadas de mecanismo (somente 1 chamada se o registro de destino for idêntico ao registro de origem - ou seja, se nenhuma alteração no registro de Campanha)

   Ao estimar o volume geral de chamadas do mecanismo de Campanha, é importante considerar outras fontes de chamadas do mecanismo, incluindo landing page, WebApps, JSSP, APIs, registros de aplicativos móveis etc.

   Informações do pacote de Campanha de visualização aqui: https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html

* A integração suporta um máximo de 30 milhões de contatos.

* A oferta de integração padrão inclui suporte para até cinco entidades personalizadas, cada uma com um máximo de 50 colunas de tamanho.

* Você precisará criar e publicar seus recursos personalizados antes de implementar a integração.

* A profundidade máxima da tabela ao vincular tabelas é de dois (ou seja, tabela1->tabela2->tabela3)

* Há suporte limitado para tipos de dados do Microsoft Dynamic 365. Se o modelo de dados contiver um tipo de dados diferente dos tipos simples de dados (por exemplo, sequências, números inteiros, decimais etc.), talvez seja necessário atualizar o modelo de dados antes de usar a integração.

* Se você optar por preservar os dados existentes em entidades personalizadas de Campanha, precisará preparar os dados para a integração.

* Talvez seja necessário estabelecer janelas de manutenção onboard entre o Adobe e o cliente.

* Esteja ciente de que aumentos significativos ou &quot;picos&quot; na utilização da integração (por exemplo, aumento acentuado de registros novos ou atualizados) podem causar lentidão na sincronização de dados.

* Como parte da integração, espera-se que você conclua as etapas de configuração de pré-integração no Microsoft Azure e no Dynamics 365. Consulte as etapas de configuração [nesta página](../../integrating/using/d365-acs-configure-d365.md)

* Espera-se que você incorpore seus modelos de dados do Dynamics 365 e Campanha à integração e os mantenha.

### Limites de integração

A integração foi projetada para resolver o caso de uso geral da movimentação comum de dados entre o Microsoft Dynamics 365 e a Campanha, mas não se destina a abordar todos os casos de uso específicos a cada cliente:

* A integração não emite privacidade (por exemplo, RGPD) para exclusão. A responsabilidade de satisfazer os pedidos de privacidade dos utilizadores finais incumbe ao cliente; essas solicitações devem ser feitas tanto na Campanha (via Adobe Experience Platform Privacy Service) quanto no Dynamics 365 independentemente. A integração pode emitir exclusões regulares para ajudar na sincronização de dados, se desejado.   Consulte [a seção Privacidade](#manage-privacy-requests) para obter mais informações.

* Nenhum dado de entidade personalizada ou perfil será sincronizado da Campanha para o Dynamics 365, com exceção das informações de opção de não participação (se configuradas pelo cliente).

* O gerenciamento de subscrições de campanha (ou seja, assina/cancela a assinatura) não é suportado nativamente.

* Não há suporte para a composição e o acionamento de campanhas de e-mail de Campanha no Dynamics 365.

* A integração **não** oferece suporte à remodelagem de dados entre os modelos de dados do Dynamics 365 e do Campaign Standard. Espera-se que a integração sincronize uma tabela do Dynamics 365 em uma tabela de Campanha.
