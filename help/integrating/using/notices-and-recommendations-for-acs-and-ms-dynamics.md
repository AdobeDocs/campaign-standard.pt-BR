---
solution: Campaign Standard
product: campaign
title: Campanha e gestão de dados do Microsoft Dynamics 365
description: Saiba como o Campaign Standard e o Microsoft Dynamics 365 gerenciam dados comuns
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '1448'
ht-degree: 1%

---


# Gerenciar dados entre o Campaign e o Microsoft Dynamics 365

## Fonte da verdade para sincronização unidirecional

Para sincronização de contatos e entidades personalizadas, essa integração trata o Dynamics 365 como a fonte da verdade.  Quaisquer alterações nos atributos sincronizados devem ser feitas no Dynamics 365, não na Campanha.  Se as alterações forem feitas na Campanha, elas poderão eventualmente ser substituídas na Campanha durante a sincronização, já que a sincronização está em uma direção.

## Exclusão de contato

Se desejar, a integração pode ser configurada para emitir chamadas de exclusão de perfil para Campanha quando um contato for excluído no Dynamics 365, para ajudar a manter a integridade dos dados.

No entanto, uma exclusão de perfil é diferente de uma exclusão de privacidade. Uma exclusão de privacidade na Campanha removerá o registro do perfil da Campanha e as entradas de registro associadas; enquanto que, uma exclusão regular de perfis só excluirá o registro de perfis ACS, deixando os remanescentes para trás nos registros de Campanhas.

Se o recurso de exclusão de perfil estiver ativado na integração, outras etapas deverão ser seguidas para processar corretamente as solicitações de privacidade do indivíduo de dados. Consulte as etapas na seção [abaixo](#manage-privacy-requests).

## Privacidade

### Gerenciar solicitações de privacidade {#manage-privacy-requests}

Essa integração foi projetada para transferir dados do usuário final (incluindo, mas não se limitando a, informações pessoais, se contidas em seus dados do usuário final), entre o Microsoft Dynamics 365 e o Adobe Campaign Standard. Como controlador de dados, sua empresa é responsável por cumprir todas as leis e regulamentos de privacidade aplicáveis à sua coleta e uso de dados pessoais.

A integração não emite nenhuma privacidade da pessoa de dados (por exemplo, o RGPD) exclui ou lida com outras solicitações de privacidade (com exceção da opção de não participação). Ao processar solicitações de privacidade, você deve fazê-lo no Dynamics 365 e na Campanha (via Adobe Experience Platform Privacy Service), independentemente.

Se você configurou a integração para emitir chamadas de exclusão de perfil regulares para Campanha quando um contato é excluído no Dynamics 365, as etapas abaixo devem ser seguidas. Certifique-se de que não sejam feitas atualizações ao registro em questão durante este processo.

1. Emita solicitação de exclusão de privacidade para [Adobe Experience Platform Privacy Service](https://www.adobe.io/apis/experiencecloud/gdpr.html)

1. Monitorar solicitação até que seja concluída com êxito

1. Verifique se o registro não está mais em sua instância de Campanha

1. (Logo após) Problema de exclusão de privacidade no Dynamics 365

1. Verifique se o registro foi removido de ambos os sistemas

Abaixo estão links para ajudá-lo a implementar as solicitações de acesso e/ou excluir privacidade em cada sistema:

* [Microsoft Dynamics 365](https://docs.microsoft.com/en-us/microsoft-365/compliance/gdpr-dsr-dynamics365?toc=/microsoft-365/enterprise/toc.json)

* [Adobe Campaign Standard](https://www.adobe.io/apis/experiencecloud/gdpr/docs.html)


### Privacidade e recursos vinculados {#privacy-linked-resources}

Se qualquer registro de recurso personalizado de Campanha contiver informações pessoais, aplicáveis à utilização de Campanhas por um cliente, tais registros devem ser ligados a um registro de perfil de Campanha correspondente (diretamente ou através de outro recurso personalizado), de modo a que uma exclusão relacionada com a privacidade no registro de perfis possa também eliminar o registro de recursos personalizados que contém informações pessoais; as opções de vinculação e exclusão entre as entidades devem ser configuradas para permitir essa remoção em cascata dos registros vinculados. As informações pessoais não devem ser inseridas em um recurso personalizado que não esteja vinculado ao perfil.

Saiba como mapear recursos de Campanha e entidades do Dynamics 365 [nesta seção](../../integrating/using/map-campaign-custom-resources-and-dynamics-365-custom-entities.md).

## Recusar

Devido às diferenças nos atributos de opção entre o Dynamics 365 e a Campanha, e às diferenças nos requisitos de negócios de cada cliente, o mapeamento de opção de não participação foi deixado como um exercício para o cliente concluir.  É importante garantir que as opções de não participação sejam mapeadas corretamente entre os sistemas para que as preferências de não participação do usuário final sejam mantidas e que eles não recebam uma comunicação por meio de um canal de que tenham opt out.

Esteja ciente de que somente os atributos de Campanha com o prefixo &quot;Não entrar em contato mais por&quot; (por exemplo, Não entrar em contato mais por email) ou o atributo específico para opção de não participação do CCPA podem ser usados em mapeamentos de opção de não participação. [Saiba mais](../../developing/using/datamodel-profile.md).
No Dynamics 365, a maioria dos campos de opção de não participação têm o prefixo &quot;não&quot;; no entanto, você também pode utilizar outros atributos para fins de não participação se os tipos de dados forem compatíveis.

Ao provisionar a integração, você terá a oportunidade de especificar qual configuração de opção de não participação é necessária para sua empresa:

* O Dynamics 365 é fonte de verdade para opções de não participação: os atributos de opção de não participação serão sincronizados em uma direção do Dynamics 365 para a Campanha
* A campanha é a fonte da verdade para opções de não participação: os atributos de opção de não participação serão sincronizados em uma direção da Campanha para o Dynamics 365
* O Dynamics 365 E a Campanha são duas fontes de verdade: os atributos de opção de não participação serão sincronizados bidirecionalmente entre a Campanha e o Dynamics 365

Como alternativa, se você tiver um processo separado para gerenciar a sincronização de não participação entre os sistemas, o fluxo de dados de não participação da integração poderá ser desativado.

A configuração de opção bidirecional usa a lógica para determinar qual valor gravar em ambos os sistemas. A lógica compara os carimbos de data e hora entre os dois sistemas (alteração no nível de registro no Dynamics 365, alteração no nível de atributo na Campanha) para determinar qual sistema prevalece. Se a Campanha contiver o carimbo de data e hora mais recente, o valor da Campanha prevalecerá. Se o Dynamics 365 contiver o carimbo de data e hora mais recente ou se forem iguais, então a opção opt-out=TRUE vencerá (presumindo que um dos valores seja VERDADEIRO).

>[!NOTE]
>
>Revise e, se apropriado, atualize as regras de tipologia padrão e específicas do Adobe Campaign antes de fazer alterações aqui para garantir que essas alterações sejam aplicadas corretamente a todas as comunicações de saída. Por exemplo, certifique-se de que todos os mapeamentos para preferências de não participação refletem com precisão as opções de intenção/comunicação do recipient e não interrompem inadvertidamente o delivery de relacionamento ou mensagens transacionais, como confirmações de ordem do cliente.

Se você selecionou a configuração bidirecional ou Campanha para a opção de não participação do Dynamics 365, os dados de opção de não participação da Campanha serão exportados periodicamente pelo fluxo de trabalho para a área de armazenamento SFTP da Campanha (consulte &quot;Uso do SFTP da Campanha abaixo&quot;). No evento de que seus workflows de opção de não participação da Campanha parem de ser executados, será necessário reiniciar manualmente o mais rápido possível para reduzir a possibilidade de sincronizações de opção de não participação.

## Uso de SFTP de campanha

Seu armazenamento SFTP de Campanha precisará ser utilizado pela integração nos casos de uso abaixo.  Você precisará garantir que sua conta SFTP tenha capacidade de armazenamento adequada para acomodar esses casos de uso.  Exceder a capacidade licenciada do armazenamento SFTP pode prejudicar seriamente o uso funcional da Campanha, da integração e/ou da conta SFTP.

| Caso de uso | Descrição |
|---|---|
| Carregamento de dados iniciais | As tabelas do Dynamics 365 com mais de 500 mil registros precisarão ser exportadas para o armazenamento SFTP de Campanha a ser importado por meio do fluxo de trabalho. A partir desse ponto, a integração usará APIs para atualizações incrementais. |
| Opção de não participação bidirecional e Campanha para a opção de não participação unidirecional do Dynamics 365 | A opção de não participação bidirecional e a Campanha para os fluxos de dados de não participação unidirecional do Dynamics 365 utilizarão o armazenamento SFTP Campanha. Um fluxo de trabalho ACS exportará alterações incrementais para a pasta SFTP. A partir daí, a integração pegará os registros e o processo. |
| Recuperação de desastres | No evento improvável de um desastre do sistema, o caso de uso &quot;Carregamento inicial de dados&quot; será seguido para alimentar as atualizações incrementais à Campanha que foram perdidas. |

## Dados de Campanha existentes

Essa integração sincronizará contatos e entidades personalizadas do Dynamics 365 com a Campanha. Os registros de campanha criados fora da integração (ou seja, não criados pela tarefa de sincronização) não serão modificados pela integração, incluindo registros de Campanha existentes no momento da configuração da integração.

Como essa integração usa o campo **[!UICONTROL externalId]** na Campanha para sincronizar registros de perfis de Campanha com registros de contato do Dynamics 365, esse campo de Campanha (**[!UICONTROL externalId]** ) deve ser preenchido com o Dynamics 365 **[!UICONTROL contactId]** para os registros que você deseja sincronizar do Dynamics 365.  As entidades personalizadas também são sincronizadas usando uma ID exclusiva do Dynamics 365. A entidade personalizada Campanha precisará incluir esse atributo de ID como uma coluna de tabela. A coluna externalId pode ser usada para armazenar esse valor de atributo, mas não é necessária para entidades personalizadas de Campanha.

Lembre-se de que o Dynamics 365 ainda é a fonte da verdade e que os dados do perfil da Campanha podem ser sobrescritos à medida que a integração detecta atualizações do lado do Dynamics 365.  Pode haver outras etapas necessárias para habilitar a integração, dependendo da implantação existente; portanto, recomenda-se que você trabalhe em conjunto com seu contato técnico com o Adobe.

>[!NOTE]
>
>Devido à complexidade das implantações de clientes existentes, recomenda-se trabalhar com seu contato técnico do Adobe ao planejar e configurar a integração.

## Frequência de sincronização de dados

A integração utiliza uma arquitetura que permite que as atualizações sejam detectadas e adicionadas à &quot;fila&quot; de processamento logo após sua ocorrência no Dynamics 365 (ou seja, streaming, e não processamento em lote). Por isso, não há necessidade de especificar as frequências ou programações de execução do fluxo de dados.

A exceção a isso é a Campanha bidirecional e os fluxos de dados de opção de não participação do Dynamics 365. Para essas configurações de não participação, os registros ACS atualizados são exportados para SFTP por meio do fluxo de trabalho ACS uma vez por dia, após o que a ferramenta de integração lê o arquivo e processa o registro.

## Contrato de uso de dados

Se você estiver localizado em regiões EMEA ou APAC, alguns de seus dados serão processados nos EUA como parte dessa integração. Para saber mais, consulte [esta seção](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).
