---
title: Sobre a integração do Microsoft Dynamics 365
description: Saiba mais sobre avisos e recomendações para trabalhar com o Campaign Standard e o Microsoft Dynamics 365
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
source-git-commit: 277663c4cf0e810f691eeebfade17bf8dd73698e

---


# Sobre a integração do Microsoft Dynamics 365

## Apoio regional

Essa integração está disponível nas regiões da América do Norte, EMEA e APAC.

Se você estiver localizado em regiões EMEA ou APAC, alguns de seus dados serão processados nos EUA como parte dessa integração. Para obter mais informações, consulte [esta seção](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

## Fonte da verdade para sincronização de contato unidirecional

Para a sincronização de entidade de Contato e personalizada, essa integração trata o Dynamics 365 como a fonte da verdade. Quaisquer alterações nos atributos sincronizados devem ser feitas no Microsoft Dynamics 365, não no Adobe Campaign Standard. Se as alterações forem feitas na Campanha, elas poderão eventualmente ser substituídas na Campanha durante a sincronização, já que a sincronização está em uma direção.  Além disso, a Sincronização de Contatos foi projetada para obter todos os registros de Contato, independentemente de estarem marcados como ativos ou inativos no Microsoft Dynamics 365.

## Gerenciando solicitações de privacidade

Essa integração foi projetada para transferir dados do usuário final (incluindo, mas não se limitando a, informações pessoais, se contidas em seus dados do usuário final), entre o Microsoft Dynamics 365 e o Adobe Campaign Standard.  Como controlador de dados, sua empresa é responsável por cumprir todas as leis e regulamentos de privacidade aplicáveis à sua coleta e uso de dados pessoais.

Para essa integração, você deve processar cada solicitação de pessoa de dados em cada sistema de forma independente para que a alteração seja refletida em ambos os bancos de dados. A alteração deve ser executada primeiro no Microsoft Dynamics 365 e depois no Adobe Campaign Standard. A única exceção a isso é que uma solicitação de exclusão relacionada à privacidade será adicionada à fila de Ferramentas de privacidade no Campaign Standard quando um contato for excluído no Dynamics 365.

Abaixo estão links para ajudá-lo a implementar as solicitações de acesso e/ou excluir privacidade em cada sistema:

* [Microsoft Dynamics 365](https://docs.microsoft.com/en-us/microsoft-365/compliance/gdpr-dsr-dynamics365?toc=/microsoft-365/enterprise/toc.json)

* [Adobe Campaign Standard](https://www.adobe.io/apis/experiencecloud/gdpr/docs.html)

## Exclusão de contato

Como o Dynamics 365 é a fonte da verdade, as exclusões de contato no Dynamics 365 serão refletidas na Campanha.

Quando um Contato é excluído no Dynamics 365, a integração enfileira uma solicitação de exclusão relacionada à privacidade na tela de ferramentas/solicitação de privacidade da Campanha.  Se você tiver desabilitado o processo de duas etapas para solicitações de exclusão relacionadas à privacidade, a Campanha cuidará da exclusão para você.

No entanto, se o processo de 2 etapas estiver ativado, você precisará acessar a tela Solicitação de privacidade/ferramentas, depois que os workflows técnicos de privacidade tiverem sido executados e confirmar se os registros estão ok para serem excluídos.  Só então a Campanhas cuidará da exclusão.

Para obter mais detalhes, consulte [Como executar solicitações de exclusão relacionadas à privacidade no Adobe Campaign Standard](https://docs.adobe.com/content/help/pt-BR/campaign-learn/campaign-standard-tutorials/privacy/execute-privacy-requests.html)

>[!CAUTION]
>
>Se você tiver o processo de 2 etapas ativado para solicitações de privacidade na Campanha, suas exclusões no Dynamics 365 não serão refletidas automaticamente na Campanha.  Você precisará acessar a tela de solicitação de privacidade da Campanha para confirmar as exclusões.

>[!NOTE]
>
>Essa integração cria uma solicitação usando a ID externa (isto é, a ID de contato do Dynamics 365) como o identificador de registro/perfil.

## Recusar

Devido às diferenças nos atributos de opção entre o Dynamics 365 e a Campanha, e às diferenças nos requisitos de negócios de cada cliente, o mapeamento de opção de não participação foi deixado como um exercício para o cliente concluir. É importante garantir que as opções de não participação sejam mapeadas corretamente entre os sistemas para que as preferências de não participação do usuário final sejam mantidas e que eles não recebam uma comunicação por meio de um canal de que tenham opt out.

Esteja ciente de que somente os atributos de Campanha com o prefixo &quot;blackList&quot; (por exemplo, blackListEmail) ou o atributo específico para opção de não participação CCPA podem ser usados em mapeamentos de opção de não participação.  No Dynamics 365, a maioria dos campos de opção de não participação têm o prefixo &quot;doNot&quot;; no entanto, você também pode utilizar atributos personalizados criados para fins de não participação se os tipos de dados forem compatíveis.

Ao provisionar a integração, você terá a oportunidade de especificar qual configuração de opção de não participação é necessária para sua empresa:

* O Dynamics 365 é fonte de verdade para opções de não participação: os atributos de opção de não participação serão sincronizados em uma direção do Dynamics 365 para o Campaign Standard
* O Campaign Standard é a fonte da verdade para opções de não participação: os atributos de opção de não participação serão sincronizados em uma direção do Campaign Standard para o Dynamics 365
* O Dynamics 365 E o Campaign Standard são duas fontes de verdade: os atributos de opção de não participação serão sincronizados bidirecionalmente entre o Campaign Standard e o Dynamics 365

Siga as instruções pós-provisionamento no guia [do usuário](https://drive.google.com/drive/folders/16seHF45e6bFxHX15zWLqFLEXymCuA_wn) Unifi para mapear esses valores corretamente.

A configuração de opção bidirecional usa a lógica para determinar qual valor gravar em ambos os sistemas.  A lógica compara os carimbos de data e hora entre os dois sistemas (alteração no nível de registro no Dynamics 365, alteração no nível de atributo na Campanha) para determinar qual sistema prevalece.  Se a Campanha contiver o carimbo de data e hora mais recente, o valor da Campanha prevalecerá.  Se o Dynamics 365 contiver o carimbo de data e hora mais recente ou se forem iguais, então a opção opt-out=TRUE vencerá (presumindo que um dos valores seja VERDADEIRO).

**Recusa ao abrigo da lei California Consumer Protection Act (CCPA) e legislação semelhante.**

No momento, o recurso de configuração de opção bidirecional não é capaz de suportar a conformidade com determinados requisitos estatutários no CCPA e/ou outras leis de privacidade de dados prontos para uso. Os clientes que precisam cumprir os requisitos legais do CCPA ou semelhantes relacionados às opções de não participação são responsáveis pela implementação de sua própria solução de terceiros para executar sincronizações bidirecionais.

>[!NOTE]
>
>É recomendável que, se sua empresa não exigir suporte bidirecional para opção de não participação, você selecione uma opção de opção de não participação unidirecional.

>[!NOTE]
>
>Revise e, se apropriado, atualize as regras de tipologia padrão e específicas do Adobe Campaign antes de fazer alterações aqui para garantir que essas alterações sejam aplicadas corretamente a todas as comunicações de saída. Por exemplo, certifique-se de que todos os mapeamentos para preferências de não participação refletem com precisão as opções de intenção/comunicação do recipient e não interrompem inadvertidamente o delivery de relacionamento ou mensagens transacionais, como confirmações de ordem do cliente.

## Dados de Campanha existentes

Essa integração sincronizará Contatos e entidades personalizadas do Dynamics 365 para a Campanha. Os registros de Campanha criados fora da integração (ou seja, não criados pela tarefa de sincronização) não serão tocados pela integração, incluindo registros de Campanha existentes no momento da configuração da integração.

Como essa integração usa o **[!UICONTROL externalId]** campo no Campaign Standard para sincronizar registros de perfis de Campanha com registros de Contato do Dynamics 365, esse campo de Campanha (**[!UICONTROL externalId]** ) deve ser preenchido com o Dynamics 365 **[!UICONTROL contactId]** para os registros que você deseja sincronizar do Dynamics 365.  As entidades personalizadas também precisarão ter esse campo presente e preenchido corretamente para manter a sincronização.  Lembre-se, no entanto, de que o Dynamics 365 ainda será a fonte da verdade e que os dados do perfil da Campanha poderão ser sobrescritos à medida que a integração detecta atualizações do lado do Dynamics 365.  Pode haver outras etapas necessárias para habilitar a integração, dependendo da implantação existente; portanto, recomenda-se que você trabalhe em conjunto com seu contato técnico da Adobe.

>[!NOTE]
>
>Devido à complexidade das implantações de clientes existentes, recomenda-se trabalhar com seu contato técnico da Adobe ao planejar e configurar a integração.
