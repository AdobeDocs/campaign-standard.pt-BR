---
title: Gerenciamento de dados do Campaign e do Microsoft Dynamics 365
description: Saiba como o Campaign Standard e o Microsoft Dynamics 365 gerenciam dados comuns
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: aab6f005-f3da-4c0b-b856-da8504e611dc
source-git-commit: 17522f4df86c7fb46593472316d57b4ba4acee2b
workflow-type: tm+mt
source-wordcount: '2523'
ht-degree: 1%

---

# Práticas recomendadas e limitações {#acs-msdyn-best-practices}

## Gerenciar dados {#acs-msdyn-manage-data}

Para sincronização de contatos e entidades personalizadas, essa integração trata **Microsoft Dynamics 365 como fonte da verdade**.  Quaisquer alterações nos atributos sincronizados devem ser feitas no Dynamics 365 e não no Adobe Campaign Standard).  Se forem feitas alterações no Campaign, elas poderão ser substituídas no Campaign durante a sincronização, pois a sincronização está em uma direção.

A integração pode ser configurada opcionalmente para emitir chamadas de exclusão de perfil para o Campaign quando um contato é excluído no Dynamics 365 para ajudar a manter a integridade dos dados. No entanto, uma exclusão de perfil é diferente de uma exclusão de privacidade. Uma exclusão de privacidade no Campaign removerá o registro do perfil do Campaign e as entradas de log associadas; enquanto uma exclusão de perfil regular excluirá somente o registro do perfil do Campaign, deixando vestígios nos logs do Campaign. Se o recurso de exclusão de perfil estiver habilitado na integração, etapas adicionais precisarão ser seguidas para processar corretamente as solicitações de privacidade do titular dos dados. Consulte as etapas na [Seção Privacidade abaixo](#manage-privacy-requests).

## Privacidade{#acs-msdyn-manage-privacy}

Essa integração foi projetada para transferir dados do usuário final entre o Microsoft Dynamics 365 e o Adobe Campaign Standard. Esses dados incluem informações pessoais se estiverem contidos nos dados do usuário final.  Como controlador de dados, sua empresa é responsável por cumprir todas as leis e regulamentos de privacidade aplicáveis à coleta e ao uso de dados pessoais.

Essa integração foi projetada para transferir dados do usuário final (incluindo, mas não se limitando a, informações pessoais, se estiverem contidas nos dados do usuário final) entre o Microsoft Dynamics 365 e o Adobe Campaign Standard. Como controlador de dados, sua empresa é responsável por cumprir todas as leis e regulamentos de privacidade aplicáveis à coleta e ao uso de dados pessoais.

A integração não emite nenhuma privacidade do titular dos dados (por exemplo, o GDPR) e exclui ou lida com outras solicitações de privacidade (com exceção da recusa). Ao processar solicitações de privacidade, você deve fazer isso no Microsoft Dynamics 365 e no Campaign (por meio do Adobe Experience Platform Privacy Service), independentemente.

Se você tiver configurado a integração para emitir chamadas de exclusão de perfil regulares para o Campaign quando um contato for excluído no Dynamics 365, as etapas abaixo deverão ser seguidas. Verifique se nenhuma atualização foi feita no registro em questão durante esse processo.

1. Enviar solicitação de exclusão de privacidade para [Adobe Experience Platform Privacy Service](https://developer.adobe.com/experience-platform-apis/references/privacy-service)

1. Monitorar solicitação até que ela seja concluída com sucesso

1. Verifique se o registro não está mais na instância do Campaign

1. (Logo depois) Exclusão de privacidade de problema no Dynamics 365

1. Verificar se o registro foi removido de ambos os sistemas


>[!IMPORTANT]
>
>Se qualquer registro de recurso personalizado do Campaign contiver informações pessoais, aplicáveis ao uso do Campaign por um cliente, esse registro deverá ser vinculado a um registro de perfil do Campaign correspondente (diretamente ou por meio de outro recurso personalizado) para que uma exclusão relacionada à privacidade no registro de perfil também possa excluir o registro de recurso personalizado vinculado que contém informações pessoais; as opções de vinculação e exclusão entre as entidades devem ser configuradas para habilitar essa remoção em cascata dos registros vinculados. As informações pessoais não devem ser inseridas em um recurso personalizado que não esteja vinculado ao perfil.

## Recusar {#opt-out}

Devido às diferenças nos atributos de recusa entre o Microsoft Dynamics 365 e o Campaign, bem como às diferenças nos requisitos de negócios de cada cliente, o mapeamento de recusa foi deixado como um exercício a ser concluído pelo cliente.  É importante garantir que as opções de não participação sejam mapeadas corretamente entre os sistemas, para que as preferências de não participação do usuário final sejam mantidas e ele não receba uma comunicação por meio de um canal do qual tenha optado.

Esteja ciente de que somente os seguintes itens podem ser usados em mapeamentos de recusa:

* Atributos de campanha com o prefixo &quot;Não entrar mais em contato por&quot; (por exemplo, Não entrar mais em contato por email) ou

* o atributo específico para a CCPA

Mais informações sobre campos de entidade de perfil podem ser encontradas [aqui](../../developing/using/datamodel-profile.md).

No Dynamics 365, a maioria dos campos de recusa tem o prefixo &quot;donot&quot;. No entanto, você também pode utilizar outros atributos para fins de recusa, se os tipos de dados forem compatíveis.

Ao provisionar a integração, você terá a oportunidade de especificar qual configuração de recusa é necessária para sua empresa:

* **Unidirecional (Microsoft Dynamics 365 para Campaign)**: o Dynamics 365 é a fonte da verdade para cancelamentos. Os atributos de recusa serão sincronizados em uma direção do Dynamics 365 para o Campaign Standard
* **Unidirecional (Campaign para Microsoft Dynamics 365)**: o Campaign Standard é a fonte da verdade para os cancelamentos. Os atributos de recusa serão sincronizados em uma direção do Campaign Standard para o Dynamics 365
* **Bidirecional**: Dynamics 365 E Campaign Standard são ambas fontes da verdade. Os atributos de recusa serão sincronizados bidirecionalmente entre o Campaign Standard e o Dynamics 365

Como alternativa, se você tiver um processo separado para gerenciar a sincronização de recusa entre os sistemas, o fluxo de dados de recusa da integração poderá ser desativado.

A configuração de recusa bidirecional usa a lógica para determinar qual valor gravar em ambos os sistemas. A lógica compara os carimbos de data e hora entre os dois sistemas (alteração no nível de registro no Dynamics 365, alteração no nível de atributo no Campaign) para determinar qual sistema prevalece. Se o Campaign contiver o carimbo de data e hora mais recente, o valor do Campaign prevalecerá. Se o Dynamics 365 contiver o carimbo de data e hora mais recente ou se forem iguais, opt-out=TRUE vencerá (supondo que um dos valores seja TRUE).

Saiba como selecionar opções de aceitação/recusa no [nesta seção](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf).

>[!NOTE]
>
>Revise e, se apropriado, atualize as regras de tipologia padrão e específica no Adobe Campaign antes de fazer alterações aqui para garantir que essas alterações sejam aplicadas corretamente a todas as comunicações de saída. Por exemplo, certifique-se de que todos os mapeamentos das preferências de recusa reflitam com precisão as opções de intenção/comunicação do destinatário e não interrompam inadvertidamente o delivery de mensagens de relacionamento ou transacionais, como confirmações de pedidos de clientes.

Se você selecionou a variável **Bidirecional** ou **Unidirecional (Campaign para Microsoft Dynamics 365)** Configuração de recusa, os dados de recusa do Campaign serão exportados periodicamente por meio de fluxo de trabalho para a área de armazenamento do Campaign SFTP (consulte &quot;Uso de SFTP da campanha abaixo&quot;). Caso seus workflows de opção de não participação do Campaign parem de ser executados, será necessário reiniciar manualmente o mais rápido possível para reduzir a possibilidade de sincronizações de recusa perdidas.

>[!IMPORTANT]
>
>Se você precisar de **Bidirecional** ou **Unidirecional (Campaign para Microsoft Dynamics 365)** configuração de recusa, será necessário fazer a solicitação ao contato técnico do Adobe para que os workflows de recusa sejam configurados na instância do Campaign

## Uso do SFTP da campanha

O armazenamento SFTP do Campaign precisará ser usado pela integração nos casos de uso abaixo.  Será necessário garantir que sua conta SFTP tenha capacidade de armazenamento adequada para acomodar esses casos de uso. Exceder a capacidade de armazenamento SFTP licenciada pode prejudicar seriamente o uso funcional do Campaign, a integração e/ou a conta SFTP.

| Caso de uso | Descrição |
|---|---|
| Bidirecional e Unidirecional (Campaign para Microsoft Dynamics 365) | Fluxos de dados de recusa bidirecionais e unidirecionais (Campaign para Microsoft Dynamics 365) utilizarão o armazenamento SFTP do Campaign. Um workflow do Campaign exportará alterações incrementais para a pasta SFTP. A partir daí, a integração selecionará os registros e processará. |
| Logs de recusa | Os logs de saída do conector serão úteis ao solucionar problemas da integração. Os logs de saída podem ser ativados/desativados. |


>[!IMPORTANT]
>
>Você é responsável pelas informações que acessar e baixar das pastas SFTP. Se as informações contiverem dados pessoais, você será responsável por cumprir as leis e regulamentos de privacidade aplicáveis. [Saiba mais](#acs-msdyn-manage-privacy).

## Gerenciamento de dados

### Dados existentes do Campaign

Essa integração sincronizará contatos e entidades personalizadas do Microsoft Dynamics 365 para o Campaign. Os registros de campanha criados fora da integração (ou seja, não criados pelo trabalho de sincronização) não serão modificados pela integração, incluindo registros de Campanha existentes no momento da configuração da integração.

Como essa integração usa o **[!UICONTROL externalId]** no Campaign para sincronizar registros de perfil do Campaign com registros de contato do Dynamics 365, este campo do Campaign (**[!UICONTROL externalId]** ) deve ser preenchida com o Microsoft Dynamics 365 **[!UICONTROL contactId]** para os registros que você deseja sincronizar do Microsoft Dynamics 365.  As entidades personalizadas também são sincronizadas usando uma ID exclusiva do Microsoft Dynamics 365. A entidade personalizada do Campaign precisará incluir esse atributo de ID como uma coluna da tabela. A coluna externalId pode ser usada para armazenar esse valor de atributo, mas não é necessária para entidades personalizadas do Campaign.

Lembre-se, que o Microsoft Dynamics 365 ainda é a fonte da verdade e que os dados do perfil do Campaign podem ser substituídos, pois a integração detecta atualizações no Dynamics 365.  Também pode haver outras etapas necessárias para habilitar a integração, dependendo de sua implantação existente; portanto, é recomendável que você trabalhe em conjunto com seu contato técnico em Adobe.

>[!NOTE]
>
>Devido à complexidade das implantações existentes de clientes, é recomendável que você trabalhe com seu contato técnico de Adobe ao planejar e configurar a integração.

### Frequência de sincronização de dados

A integração utiliza uma arquitetura que permite que as atualizações sejam detectadas e adicionadas à &quot;fila&quot; de processamento logo após ocorrerem no Microsoft Dynamics 365 (ou seja, transmissão, não processamento em lote). Por esse motivo, não há necessidade de especificar frequências ou agendamentos de execução de fluxo de dados.

A exceção a isso são os fluxos de dados bidirecionais e de recusa do Campaign para o Dynamics 365. Para essas configurações de recusa, os registros atualizados do Campaign são exportados para SFTP por meio de um fluxo de trabalho do Campaign uma vez por dia, após o qual a ferramenta de integração lê o arquivo e processa o registro.

### Contrato de uso de dados

Se você estiver em regiões da EMEA ou APAC, alguns de seus dados serão processados nos EUA como parte dessa integração. Para obter mais informações, consulte [esta seção](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

## Medidas de proteção e limitações

>[!IMPORTANT]
>
>Determinadas ações de sua parte (por exemplo, assimilação inicial de registros, repetição de dados de registro etc.) O pode resultar na assimilação de uma grande quantidade de registros do Microsoft Dynamics 365 na instância do Adobe Campaign. Para reduzir o risco de problemas de desempenho, é recomendável interromper todos os processos do Campaign (por exemplo, nenhuma atividade de marketing, nenhuma execução de workflows etc.) até depois que a grande carga de registros for assimilada no Campaign.

### Entidades personalizadas

A variável [Integração com o Microsoft Dynamics 365-Adobe Campaign Standard](../../integrating/using/d365-acs-get-started.md) O oferece suporte a entidades personalizadas, permitindo que as entidades personalizadas no Dynamics 365 sejam sincronizadas com os recursos personalizados correspondentes no Campaign.

A integração oferece suporte a tabelas vinculadas e não vinculadas.

Ao configurar fluxos de dados de entidade personalizados, é importante estar ciente do seguinte:

* A criação e a modificação dos recursos personalizados do Campaign são operações confidenciais que só devem ser executadas por usuários especialistas.
* Para fluxos de dados de entidade personalizados, o controle de alterações deve ser habilitado no Dynamics 365 para entidades personalizadas sincronizadas.
* Se um registro primário e um registro secundário vinculado forem criados quase ao mesmo tempo no Dynamics 365, devido ao processamento paralelo da integração, haverá uma pequena chance de um novo registro secundário ser gravado no Campaign antes do registro primário.

* Se o pai e o filho estiverem vinculados no lado da Campanha usando o **Link simples de cardinalidade 1** o registro secundário permanecerá oculto e inacessível (por meio da interface do usuário ou da API) até que o registro primário chegue ao Campaign.

* (Presumindo **Link simples de cardinalidade 1** no Campaign) Se o registro filho for atualizado ou excluído no Dynamics 365 e essa alteração for gravada no Campaign antes que o registro pai seja exibido no Campaign (não é provável, mas uma possibilidade remota), essa atualização ou exclusão não será processada no Campaign e um erro será lançado. No caso de atualização, o registro em questão precisará ser atualizado no Dynamics 365 novamente para sincronizar o registro atualizado. No caso de exclusão, o registro em questão precisará ser tratado separadamente no lado da campanha, pois não há mais um registro no Dynamics 365 para excluir ou atualizar.

* Se você encontrar uma situação em que acredita ter registros secundários ocultos e não tiver como acessá-los, poderá alterar temporariamente o tipo de link de cardinalidade para **Link simples de cardinalidade 0 ou 1** para acessar esses registros.

Uma visão geral mais abrangente dos recursos personalizados do Campaign pode ser encontrada [nesta seção](../../developing/using/key-steps-to-add-a-resource.md).

### Proteções de integração

As medidas de proteção a seguir devem ser consideradas ao planejar a utilização dessa integração. Consulte seu representante técnico da Adobe se achar que essas medidas de proteção estão ultrapassadas.

* Você precisará licenciar o pacote adequado do Campaign para dar suporte ao volume de chamadas do mecanismo gerado pela integração. Exceder o volume de chamadas do mecanismo licenciado pode causar uma degradação no desempenho do Campaign.

  Use o seguinte para ajudar a estimar o volume de chamadas do mecanismo da integração:

   * Inserções de registro (ou seja, novo registro): 1 chamada de mecanismo
   * Exclusões de registro: 1 chamada de mecanismo
   * Atualizações de registro: 2 chamadas de mecanismo (apenas 1 chamada se o registro de destino for idêntico ao registro de origem, ou seja, se nenhuma alteração for feita no registro do Campaign)

  Ao estimar o volume geral de chamadas do mecanismo do Campaign, é importante considerar outras fontes de chamadas do mecanismo, incluindo páginas de aterrissagem, WebApps, JSSP, APIs, registros de aplicativos móveis etc.

  Veja as informações do pacote do Adobe Campaign Standard aqui: [https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html](https://helpx.adobe.com/br/legal/product-descriptions/campaign-standard.html)

* A integração oferece suporte a um máximo de 15 milhões de registros totais para a sincronização inicial com os recursos no Campaign. A sincronização incremental é limitada pelo pacote do Adobe Campaign Standard.

* A oferta de integração padrão inclui suporte para até vinte entidades personalizadas, cada uma com um máximo de 50 colunas de tamanho.

* Será necessário criar e publicar os recursos personalizados antes de implementar a integração.

* A profundidade máxima da tabela ao vincular tabelas é duas (ou seja, table1->table2->table3)

* A integração aceita até 5 colunas vinculadas por recurso personalizado. A vinculação de várias colunas entre recursos personalizados pode ter grandes impactos no desempenho. **Link simples de cardinalidade 0 ou 1** é preferível sobre **Link simples de cardinalidade 1**.

* A integração oferece suporte à transformação entre tipos de dados primitivos do Microsoft Dynamics 365 (Booleano, Inteiro, Decimal, Duplo, String, DateTime, Date) e tipos de dados do Adobe Campaign Standard (inteiro, booleano, flutuante, duplo, data, data e hora, string). Os tipos de dados mais avançados são interpretados como cadeias de caracteres e sincronizados como estão.

* Talvez seja necessário estabelecer janelas de manutenção de integração entre o Adobe e o cliente.

* Esteja ciente de que aumentos significativos ou &quot;picos&quot; no uso da integração (por exemplo, aumento acentuado em registros novos ou atualizados) podem causar lentidão na sincronização de dados.

* Como parte da integração, você deverá concluir as etapas de configuração de pré-integração no Microsoft Azure e no Dynamics 365. Consulte as etapas de configuração [nesta página](../../integrating/using/d365-acs-configure-d365.md)

* Espera-se que você traga seus modelos de dados do Dynamics 365 e Campaign para a integração e os mantenha.

### Limites de integração

A integração foi projetada para resolver o caso de uso geral de movimentação de dados comum entre o Microsoft Dynamics 365 e o Campaign, mas não tem como objetivo abordar cada caso de uso específico de cada cliente:

* A integração do não emite exclusões de privacidade (por exemplo, GDPR). A responsabilidade de atender às solicitações de privacidade do usuário final cabe ao cliente; essas solicitações devem ser feitas tanto no Campaign (por meio do Adobe Experience Platform Privacy Service) quanto no Dynamics 365 independentemente. A integração pode emitir exclusões regulares para ajudar na sincronização de dados, se desejado.   Revisão [a seção Privacidade](#manage-privacy-requests) para obter mais informações.

* Nenhum dado de perfil ou de entidade personalizado será sincronizado do Campaign para o Dynamics 365, com exceção das informações de recusa (se configuradas pelo cliente).

* O gerenciamento de assinaturas de campanha (ou seja, assinaturas/cancelamentos de assinaturas) não é compatível nativamente.

* Não há suporte para a composição e o acionamento de campanhas de email do Campaign no Dynamics 365.

* A integração faz **não** oferecem suporte à remodelagem de dados entre os modelos de dados do Dynamics 365 e Campaign Standard. Espera-se que a integração sincronize uma tabela do Dynamics 365 com uma tabela do Campaign.
