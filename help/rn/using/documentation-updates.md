---
title: Atualizações da documentação
description: Saiba mais sobre todas as atualizações mais recentes da documentação do Adobe Campaign Standard
feature: Overview
role: User
level: Beginner
exl-id: 3f77825e-cb98-4cb1-9775-a8b6995e9da1
source-git-commit: 71f8348488596598f3d3b4f439dc25fb10ab8433
workflow-type: tm+mt
source-wordcount: '7127'
ht-degree: 97%

---

# Atualizações da documentação{#documentation-updates}

Além das [Notas de versão](../../rn/using/release-notes.md) do Adobe Campaign, esta página lista todas as atualizações na documentação do Adobe Campaign Standard.

## Versão 22.1 - Fevereiro de 2022 {#release-22-1}

**Melhorias incluídas na versão**

Aprimorado o mecanismo de repetição para deliveries, incluindo conteúdo importado de um URL. [Saiba mais](../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time)

Atualização do nível de acesso das opções que controlam Auditoria: opções anteriores para ativar/desativar [Trilha de auditoria](../../administration/using/audit.md) não estão acessíveis para [administradores funcionais](../../administration/using/users-management.md#functional-administrators). Com essa alteração, o nível de acesso da auditoria é modificado para fornecer controle aos administradores funcionais. [Saiba mais](../../administration/using/audit.md#enable-disable-audit)

O novo **Histórico de tarefas** foi adicionado ao painel de mensagem. [Leia mais](../../sending/using/monitoring-a-delivery.md)

**Outras alterações**

Adição de uma observação de aviso sobre palavras-chave que acionam respostas automáticas de SMS: eles devem conter somente caracteres alfanuméricos. [Saiba mais](../../channels/using/managing-incoming-sms.md)

Adição de uma observação à seção de email de teste A/B: se a população total for inferior a 50 mil, cada variante precisa representar pelo menos 10% da população total. Caso contrário, os logs exibirão um aviso. [Saiba mais](../../channels/using/designing-an-a-b-test-email.md)

Atualização da descrição do **[!UICONTROL Delete the source files after transfer]** na **Transferir arquivo** , incluindo um lembrete para monitorar manualmente o tamanho do conteúdo arquivado no diretório SFTP, caso a opção não esteja selecionada. [Saiba mais](../../automating/using/transfer-file.md)

Atualização de todos os links obsoletos no **Privacidade** seções. [Saiba mais](../../start/using/privacy.md)

Adição de um link direto para a documentação do Painel de controle do Campaign na tabela de documentação do Campaign Standard.

## Versão 21.3 - Setembro de 2021 {#release-21-3---september-2021}

**Novos recursos incluídos na versão**

Interface unificada aprimorada da Experience Cloud — [Leia mais](../../start/using/interface-description.md#top-bar)

Novo recurso de trilha de auditoria — [Leia mais](../../administration/using/audit.md)

Modo de diagnóstico de fluxo de trabalho — [Leia mais](../../automating/using/managing-execution-options.md)

**Outras atualizações de documentação que vêm com a versão**

Uma nova seção foi adicionada sobre como remover um endereço da lista de quarentena. [Leia mais](../../sending/using/understanding-quarantine-management.md#removing-a-quarantined-address)

A seção **Quarentena versus Lista de bloqueios** foi esclarecida. [Leia mais](../../sending/using/understanding-quarantine-management.md#quarantine-vs-denylist)

## Julho de 2021 {#doc-updates-july-2021}

Uma nova seção foi adicionada para descrever como permitir que os usuários assinem ou cancelem a inscrição de vários serviços em uma única página de aterrissagem. [Leia mais](../../channels/using/managing-landing-page-form-data.md#multiple-subscriptions)

A seção **Gerenciamento de dados de formulário da página de aterrissagem** foi atualizada e explicada. [Leia mais](../../channels/using/managing-landing-page-form-data.md)

## Versão 21.2 — junho de 2021 {#release-21-2---june-2021}

**Novos recursos incluídos na versão**

Validação de páginas de aterrissagem — agora é possível adicionar uma opção de contrato obrigatório às páginas de aterrissagem [Leia mais](../../channels/using/managing-landing-page-form-data.md#agreement-checkbox)

A seção **Tamanho do email** foi atualizada com informações sobre o tamanho máximo de um email, que agora é definido como 100 MB por padrão. [Leia mais](../../sending/using/design-and-personalize.md#email-size)

**Outras atualizações de documentação incluídas na versão**

Foram adicionadas informações sobre como alterar o target mapping em uma notificação por push transacional. [Leia mais](../../channels/using/transactional-push-notifications.md#change-target-mapping)

## Maio de 2021 {#doc-updates-may-2021}

A seção de relatório **Perfis ativos** foi atualizada. [Leia mais](../../audiences/using/active-profiles.md)

A página **Planejamento de versão** foi atualizada com novas datas. [Leia mais](../../rn/using/release-planning.md)


## Abril de 2021 {#doc-updates-april-2021}

Uma nova seção foi adicionada sobre como trabalhar com Fontes e Destinos da Adobe Experience Platform para compartilhar dados entre o Campaign Standard e o a Adobe Real-time Customer Data Platform (RTCDP). [Leia mais](../../integrating/using/get-started-sources-destinations.md)

## Março de 2021 {#doc-updates-march-2021}

Nova página **Ajuda e opções de suporte**. [Leia mais](../../support.md)

A seção que lista as principais etapas para enviar uma mensagem foi aprimorada com informações e referências adicionais. [Leia mais](../../channels/using/key-steps-to-send-a-message.md)

Foram adicionadas informações para especificar que, ao selecionar uma audiência em um query, sua definição é copiada e não referenciada. [Leia mais](../../audiences/using/selecting-an-audience-in-a-message.md)

As informações relacionadas ao Serviço Audience Destinations e ao Conector de dados da Adobe Experience Platform foram reagrupadas em uma nova seção. [Leia mais](../../integrating/using/aep-about-audience-destinations-service.md)

A fonte de dados **ID declarada** agora também pode ser usada com a integração do serviço principal Pessoas. Foram adicionadas informações à documentação de integração do Campaign-Audience Manager ou do serviço principal Pessoas. [Leia mais](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md)

Foram adicionadas informações sobre como implementar o rastreamento local para aplicativo para dispositivos móveis. [Leia mais](../../administration/using/local-tracking.md)

A seção [Capacidade de delivery](../../sending/using/about-deliverability.md) foi atualizada e agora inclui links para o novo [Manual de práticas recomendadas de capacidade de delivery da Adobe](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=pt-BR). Todas as informações genéricas relacionadas à capacidade de delivery que podem ser aplicadas a várias soluções da Adobe foram movidas para o [Apêndice do manual de práticas recomendadas](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/general-resources.html?lang=pt-BR#additional-resources).

## Versão 21.1 - Fevereiro de 2021 {#release-21-1---february-2021}

**Novos recursos incluídos na versão**

Serviço de feedback por email - [Leia mais](../../sending/using/confirming-the-send.md#message-indicators)

Melhorias na integração do Adobe Experience Manager: [leia mais](../../integrating/using/creating-multilingual-email-aem.md)

Interface unificada da Experience Cloud: [leia mais](../../start/using/interface-description.md#top-bar)

**Outras atualizações de documentação que vêm com a versão**

Foram adicionadas informações sobre como procurar um perfil com base no email, nome, sobrenome ou qualquer campo personalizado. [Leia mais](../../audiences/using/integrated-customer-profile.md)

Foram adicionadas informações sobre a nova função GetOption que permite retornar o valor de uma função especificada ao chamar um fluxo de trabalho com parâmetros externos. [Leia mais](../../automating/using/customizing-workflow-external-parameters.md#using-events-variables)

Foram adicionadas informações sobre a nova variável de saída **[!UICONTROL filesCount]** disponível depois de usar uma atividade **[!UICONTROL Transfer file]**. [Leia mais](../../automating/using/transfer-file.md#output-variables)

A seção **Configuração do canal de email** foi atualizada para esclarecer quais são as configurações de email mais recentes aplicáveis. Alguns parâmetros herdados ainda em uso para determinados clientes estão listados na parte inferior da página. [Leia mais](../../administration/using/configuring-email-channel.md)

Foram adicionadas informações sobre como garantir que um fluxo de trabalho agendado não seja reagendado até que uma ou mais tarefas de uma execução anterior ainda estejam pendentes. [Leia mais](../../automating/using/scheduled-workflows-execution.md)

## Dezembro de 2020 {#doc-updates-december-2020}

**O recurso Linha de assunto preditiva** está obsoleto agora. [Leia mais](../../rn/using/deprecated-features.md)

A seção **Introdução a mensagens transacionais** agora inclui [esquemas aprimorados](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle) para obter uma melhor compreensão do processo.

Um caso de uso completo para ilustrar o processo de implementação de mensagens transacionais está disponível agora. [Leia mais](../../channels/using/transactional-messaging-use-case.md)

A seção **Privacidade** foi movida para [este local](../../start/using/privacy.md).

Uma nova página **Acessibilidade** está disponível: ela detalha o suporte de acessibilidade no workspace do Adobe Campaign Standard. [Leia mais](../../start/using/accessibility.md)

Uma nota de advertência foi adicionada informando que, para um desempenho ideal, o número de mensagens transacionais publicadas deve permanecer abaixo de 100. [Leia mais](../../channels/using/transactional-messaging-limitations.md#transactional-message-number)

O protocolo e a página de configurações do conector SMS foram movidos para [este local](../../administration/using/sms-protocol.md).

A seção **Utilizar listas de produtos em uma mensagem transacional** foi movida para [este local](../../designing/using/using-product-listings.md).

## Novembro de 2020 {#doc-updates-november-2020}

A seção **Dados pessoais e personalidades** foi atualizada com um cenário de caso de uso para ilustrar como as diferentes personalidades estão interagindo com relação à privacidade. [Leia mais](../../start/using/privacy.md#use-case-scenario)

Adição de uma nova seção listando Perguntas frequentes sobre privacidade. [Leia mais](../../start/using/privacy-faq.md)

A seção **Privacidade** foi movida e enriquecida com duas novas páginas: [Gerenciamento de privacidade](../../start/using/privacy-management.md) e [Solicitações de gerenciamento de privacidade](../../start/using/privacy-requests.md).

A seção **Mensagens transacionais** foi reorganizada e reunida em um único local para navegação aprimorada. [Leia mais](../../channels/using/getting-started-with-transactional-msg.md)

Na seção Adobe Experience Platform Data Connector, foram adicionadas informações sobre o erro de validação de mapeamento de dados relacionado ao gerenciamento de privacidade e como solucioná-lo. [Leia mais](../../integrating/using/aep-mapping-activation.md)

## Versão 20.4 - Outubro de 2020 {#release-20-4---october-2020}

**Novos recursos incluídos na versão**

Grupos de controle – [Saiba mais](../../sending/using/control-group.md)

API externa (suporte a OAuth) – [Leia mais](../../automating/using/external-api.md)

Integração com o Journey AI – [Leia mais](../../sending/using/predictive.md)

**Outras atualizações de documentação incluídas na versão**

A seção sobre como chamar um workflow com parâmetros externos foi aprimorada com novas funções disponíveis no Editor de expressão. [Leia mais](../../automating/using/customizing-workflow-external-parameters.md)

Uma recomendação foi adicionada às práticas recomendadas de workflows no número de atividades a serem usadas por workflow. [Leia mais](../../automating/using/best-practices-workflows.md#number-activities)

Adição de uma nova seção sobre práticas recomendadas de delivery. [Leia mais](../../sending/using/delivery-best-practices.md)

Adição de uma seção para descrever os novos filtros que permitem pesquisar as configurações do evento de acordo com seu status e a última vez que um evento foi recebido. [Leia mais](../../channels/using/configuring-transactional-event.md#searching-transactional-events)

## Setembro de 2020 {#doc-updates-september-2020}

A seção **Mensagens transacionais do evento** foi reorganizada e explicada. [Leia mais](../../channels/using/editing-transactional-message.md)

Uma nota de advertência foi adicionada para avisar os usuários sobre a limitação de permissões relacionada ao acesso ao log. [Leia mais](../../administration/using/users-management.md)

Uma nova seção foi adicionada para detalhar o processo de criação de uma nova marca. [Leia mais](../../administration/using/branding.md#creating-a-brand)

Está disponível a nova integração entre o Campaign Standard e o Microsoft Dynamics 365. [Leia mais](../../integrating/using/d365-acs-get-started.md)

Foram adicionadas informações sobre fontes anônimas no relatório perfis ativos. [Leia mais](../../audiences/using/active-profiles.md)

## Agosto de 2020 {#doc-updates-august-2020}

Está disponível uma nova seção atualizada sobre como começar a usar mensagens transacionais. [Leia mais](../../channels/using/getting-started-with-transactional-msg.md)

A seção de **limitações de mensagens transacionais** foi movida [para cá](../../channels/using/transactional-messaging-limitations.md).

A seção **Preparação do envio** foi movida [para cá](../../sending/using/preparing-the-send.md).

## Julho de 2020 {#doc-updates-july-2020}

Uma nova seção foi adicionada com diretrizes relacionadas ao monitoramento do Campaign Standard. [Leia mais](../../administration/using/monitoring-guidelines.md)

As medidas de proteção e limitações da API externa foram atualizadas. [Leia mais](../../automating/using/external-api.md#guardrails)

A página Visão geral do gerenciamento de privacidade foi atualizada para incluir informações sobre a Lei de Proteção de Dados Pessoais (PDPA) da Tailândia e sobre a Lei Geral de Dados (LGPD) do Brasil. [Leia mais](https://helpx.adobe.com/br/campaign/kb/campaign-privacy-overview.html#whatisgdpr)

O guia Canal para dispositivos móveis foi reorganizado e melhorado. Um novo guia Configuração de canais móveis foi adicionado com documentação técnica sobre configuração móvel. [Leia mais](../../administration/using/push-tracking.md)

A página Gerenciamento de privacidade no Campaign Standard foi atualizada, incluindo esclarecimentos sobre como gerenciar solicitações de privacidade por meio da integração do Privacy Core Service. [Leia mais](https://helpx.adobe.com/br/campaign/kb/acs-privacy.html#ManagingPrivacyRequests)

Novos recursos de email alimentado por IA: envio de otimização de tempo e pontuação de perfis. [Leia mais](../../sending/using/predictive.md)

## Junho de 2020 {#doc-updates-june-2020}

Os casos de uso do workflow foram atualizados e reorganizados em seções temáticas. [Leia mais](../../automating/using/about-workflow-use-cases.md)

Casos de uso foram adicionados em como [criptografar](../../automating/using/managing-encrypted-data.md#use-case-gpg-encrypt) e [descriptografar](../../automating/using/managing-encrypted-data.md#use-case-gpg-decrypt) dados usando o Painel de controle do Campaign e workflows do Campaign.

As referências ao site de suporte herdado foram substituídas pelo novo URL. [Saiba mais](../../support.md)

A configuração personalizada da conta Litmus foi removida do recurso de renderização da caixa de entrada. [Leia mais](../../sending/using/email-rendering.md)

Campaign Standard – a integração do Microsoft Dynamics 365 está indisponível no momento. Um novo conector está sendo desenvolvido e estará disponível no futuro. As páginas de ajuda relacionadas foram removidas. [Leia mais](../../integrating/using/d365-acs-get-started.md)

## Maio de 2020 {#doc-updates-may-2020}

A página de visão geral do Campaign Standard foi enriquecida e reorganizada por temas. [Leia mais](../../start/using/about-campaign-standard.md)

A seção Parâmetros do canal de emails foi esclarecida com informações adicionais sobre os campos de máscaras autorizadas e a ID de relatórios do delivery. [Leia mais](../../administration/using/configuring-email-channel.md)

A Configuração de um aplicativo móvel usando SDKs da Adobe Experience Platform está agora disponível na documentação principal, com maiores informações sobre o aplicativo móvel de sincronização AEPSDK, do fluxo de trabalho técnico do Launch. [Leia mais](../../administration/using/configuring-a-mobile-application.md)

## Versão 20.3 - Maio de 2020 {#release-20-3---may-2020}

**Novos recursos incluídos na versão**

Lei de Proteção de Dados Pessoais da Tailândia (PDPA) - [Leia mais](https://helpx.adobe.com/content/help/br/campaign/kb/acs-privacy.html)

Atividade de API externa (GA) - [Saiba mais](../../automating/using/external-api.md)

**Outras atualizações de documentação incluídas na versão**

Foram adicionadas informações no campo **[!UICONTROL History in days]**, nas propriedades dos fluxos de trabalho, que agora incluem arquivos baixados pela atividade **[!UICONTROL Transfer file]**. [Leia mais](../../automating/using/managing-execution-options.md)

Foram adicionadas informações na seção de substituição de perfis relativas ao limite de 500 caracteres do prefixo da linha de assunto. [Leia mais](../../sending/using/testing-messages-using-target.md)

Uma nova seção dedicada à Privacidade e Consentimento foi adicionada à documentação principal. [Leia mais](../../start/using/privacy.md)

Inclusão de um caso de uso para permitir a conversão de emails do editor herdado para o Designer de email. [Leia mais](../../designing/using/converting-emails-from-legacy-editor.md)

Uma seção de perguntas frequentes sobre o Designer de email foi adicionada. [Leia mais](../../designing/using/faq-email-designer.md)

## Abril de 2020 {#doc-updates-april-2020}

A documentação da integração do Microsoft Dynamics 365 com o Adobe Campaign Standard está agora disponível na documentação principal. [Leia mais](../../integrating/using/d365-acs-get-started.md)

Recursos adicionais foram adicionados à página inicial de documentação. [Leia mais](../../campaign-standard-home.md)

Informações sobre o Experience Cloud ID Service (ECID) foram adicionadas à documentação do Conector de dados da Adobe Experience Platform. [Leia mais](../../integrating/using/aep-about-data-connector.md#key-concepts)

A seção de mensagem transacional foi aprimorada com informações sobre como acessar os eventos transacionais mais recentes e capturas de tela atualizadas. [Leia mais](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)

A documentação Tipologias e regras de tipologia foi aprimorada e atualizada com informações adicionais sobre regras de tipologia incorporadas. [Leia mais](../../sending/using/about-typology-rules.md)

Foram adicionadas informações sobre a ação da atividade **[!UICONTROL Transfer file]**, a ação **[!UICONTROL File listing]**. [Leia mais](../../automating/using/transfer-file.md)

A documentação sobre tentativas após uma falha temporária de delivery foi atualizada com mais detalhes sobre como as tentativas são gerenciadas depois de atualizadas para o MTA aprimorado. [Leia mais](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure)

A seção Exclusão de uma mensagem transacional foi aprimorada e esclarecida. [Leia mais](../../channels/using/publishing-transactional-message.md#deleting-a-transactional-message)

A seção **Visualização de deliveries** foi atualizada com exemplos de deliveries de publicação de conteúdo para dispositivos móveis. [Leia mais](../../sending/using/previewing-messages.md)

Foram adicionadas práticas recomendadas em relação a mensagens transacionais e à exclusão de eventos em tempo real não utilizados. [Leia mais](../../channels/using/configuring-transactional-event.md#creating-an-event)

A seção Configuração do canal de emails foi atualizada com esclarecimentos sobre todas as configurações de email que agora são gerenciadas pelo MTA aprimorado do Adobe Campaign. [Leia mais](../../administration/using/configuring-email-channel.md)

A seção de mensagem transacional foi atualizada com informações adicionais sobre os direitos necessários para editar configurações de eventos e sobre como enriquecer coleções em mensagens transacionais. [Leia mais](../../channels/using/configuring-transactional-event.md).

## Versão 20.2 - Abril de 2020 {#release-20-2---april-2020}

**Novos recursos incluídos na versão**

Integração do Blob do Azure - [Leia mais](../../administration/using/external-accounts.md#microsoft-azure-external-account)

Teste de email usando perfis segmentados - [Leia mais](../../sending/using/testing-messages-using-target.md)

**Outras atualizações de documentação incluídas na versão**

Foi adicionada uma limitação à renderização de Mensagens no aplicativo. [Leia mais](../../channels/using/customizing-an-in-app-message.md)

Foram adicionadas informações sobre como usar agregados em uma atividade **[!UICONTROL Query]**. [Leia mais](../../automating/using/query.md#adding-an-aggregate)

Foi adicionada uma limitação com MCPNS ao configurar um aplicativo para dispositivos móveis. [Leia mais](https://helpx.adobe.com/br/campaign/kb/configuring-app-sdk.html)

Uma nova seção de diretrizes de configuração foi adicionada ao Guia de administração. A seção sobre navegadores e sistemas operacionais compatíveis que estava no guia de Introdução foi movida para esta seção. A nota técnica sobre os pontos de extremidade de rede do Campaign Standard também foi adicionada a esta seção. [Leia mais](../../administration/using/about-configuration-guidelines.md)

Uma nova seção que descreve como excluir uma configuração de evento está agora disponível. [Leia mais](../../channels/using/publishing-transactional-event.md#deleting-an-event)

As seções de mensagens transacionais foram atualizadas para refletir as pequenas atualizações e aprimoramentos da interface de vários usuários. [Leia mais](../../channels/using/getting-started-with-transactional-msg.md)

As informações relacionadas aos painéis de atividade da API externa foram atualizadas. [Leia mais](../../automating/using/external-api.md)

## Março de 2020 {#doc-updates-march-2020}

Informações mais detalhadas sobre o MTA aprimorado foram adicionadas à documentação principal, especialmente no que se refere às regras de processamento de email e à qualificação de emails rejeitados. [Leia mais](../../administration/using/configuring-email-channel.md#email-processing-rules)

A seção dedicada ao arquivamento com Cco de email foi movida e atualizada. [Leia mais](../../sending/using/archiving.md)

A documentação Configuração de um aplicativo para dispositivo móvel e páginas relacionadas foi atualizada com o objetivo de refletir a depreciação do SDK V4. [Leia mais](https://aep-sdks.gitbook.io/docs/version-4-sdk-end-of-support-faq)

A documentação de integração do Adobe Campaign Standard/Adobe Experience Manager foi atualizada e aprimorada. [Leia mais](../../integrating/using/configure-experience-manager.md)

A documentação do Campaign Email Designer e de páginas relacionadas foi atualizada para refletir a desativação do [!DNL Adobe Creative SDK]. [Leia mais](../../rn/using/deprecated-features.md)

Uma nova seção dedicada às práticas recomendadas do modelo de dados do Campaign Standard está disponível. [Leia mais](../../developing/using/data-model-best-practices.md)

Foram adicionadas informações sobre o direito incorporado do **[!UICONTROL Workflow]**. [Leia mais](../../administration/using/list-of-roles.md)

Informações foram adicionadas sobre o **[!UICONTROL History in days field]**, disponíveis nas propriedades dos fluxos de trabalho. [Leia mais](../../automating/using/about-workflow-execution.md)

## Versão 20.1 - Fevereiro de 2020 {#release-20-1---february-2020}

**Novos recursos incluídos na versão**

Conector de dados da Adobe Experience Platform (beta) - [Leia mais](../../integrating/using/aep-about-data-connector.md)

Destinos do público (beta) - [Leia mais](../../integrating/using/aep-about-audience-destinations-service.md)

**Outras atualizações de documentação incluídas na versão**

A documentação Gerenciamento de privacidade foi atualizada com informações sobre como criar o campo de recuso CCPA para recursos de perfis personalizados. [Leia mais](https://helpx.adobe.com/content/help/en/campaign/kb/acs-privacy.html)

As Notas de versão foram reorganizadas e aprimoradas. [Leia mais](../../rn/using/release-notes.md)

Informações relacionadas ao grupo de segurança Administradores foram atualizadas, especificando que a unidade organizacional **[!UICONTROL All (all)]** está atribuída a ela e não pode ser modificada. [Leia mais](../../administration/using/managing-groups-and-users.md)

Foram adicionadas informações sobre como definir um fuso horário específico para ser usado como padrão em um workflow. [Leia mais](../../automating/using/building-a-workflow.md)

Foram adicionadas informações no guia Working with APIs sobre o novo parâmetro **_forcePagination=true**, permitindo a execução de paginação em tabelas grandes. [Leia mais](../../api/using/pagination.md)

Uma nova seção que descreve os avisos que podem ser exibidos em um painel de mensagem está disponível. [Leia mais](../../channels/using/message-dashboard.md#warnings)

A documentação do MTA aprimorado do Adobe Campaign, que descreve a infraestrutura de envio atualizada, permitindo avaliação aprimorada do delivery, produtividade e manipulação de rejeição, está disponível. [Leia mais](https://helpx.adobe.com/br/campaign/kb/campaign-enhanced-mta.html)

Foram adicionadas observações sobre os URLs do servidor de aplicativos e do servidor de mirror pages. Eles devem estar protegidos para que as pré-visualizações de páginas de aterrissagem e mirror pages sejam exibidas na interface do usuário do Campaign. [Leia mais](../../administration/using/branding.md#configuring-and-using-brands)

A seção Exportar logs foi atualizada para refletir a disponibilidade da ID de log de delivery nos recursos Logs do delivery e Logs de rastreamento. A ID permite exportar um identificador exclusivo para cada log. [Leia mais](../../automating/using/exporting-logs.md)

## Janeiro de 2020 {#doc-updates-january-2020}

A documentação de Capacidade de delivery foi atualizada com uma nova seção sobre Certificação de IP.<!--[Read more](../../sending/using/ip-certification.md)-->

Uma nova seção que descreve como criar um workflow de delivery entre canais está disponível. [Leia mais](../../automating/using/workflow-cross-channel-delivery.md)

A seção Cálculo de indicadores para relatórios dinâmicos foi atualizada. [Leia mais](../../reporting/using/indicator-calculation.md)

Foi adicionada uma nova página sobre diretrizes gerais para entregas de publicação de conteúdo para dispositivos móveis no Adobe Campaign Classic. [Leia mais](https://helpx.adobe.com/br/campaign/kb/acs-mobile.html)

A documentação Trabalho com o Campaign e o Experience Manager foi atualizada, trazendo a nova seção **Dicas sobre como usar a integração Campaign-Experience Manager**. [Leia mais](../../integrating/using/integrating-with-experience-manager.md#tips-aem)

A página inicial da documentação das APIs foi aprimorada com redirecionamentos para os diferentes tópicos. [Leia mais](../../api/using/get-started-apis.md)

## Nov - Dez de 2019 {#doc-updates-december-2019}

A documentação Configuração da conta externa S3 foi atualizada. [Leia mais](../../administration/using/external-accounts.md#amazon-s3-external-account)

A seção Design de conteúdo de email foi reorganizada. [Leia mais](../../designing/using/designing-content-in-adobe-campaign.md)

O guia de introdução à Avaliação do delivery foi integrado à documentação principal e atualizado. [Leia mais](../../sending/using/about-deliverability.md)

O guia de introdução sobre como exportar/importar recursos personalizados foi integrado à documentação principal. [Leia mais](../../automating/using/exporting-importing-custom-resources.md)

Um novo caso de uso que descreve como criar um grupo de controle usando um workflow no Campaign Standard foi adicionado.

Informações relacionadas às propriedades das páginas de aterrissagem foram movidas para uma seção dedicada. [Leia mais](../../channels/using/configuring-landing-page.md)

A documentação do Painel de controle do Campaign foi integrada ao novo conjunto de documentação colaborativa. [Leia mais](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=pt-BR)

A tabela de **Cálculo de indicadores** foi atualizada. [Leia mais](../../reporting/using/indicator-calculation.md)

O conjunto de documentações das APIs foi integrado à documentação do Campaign Standard.[Leia mais](../../api/using/get-started-apis.md)

O guia de introdução à Criação de um email personalizado foi alterado e atualizado. [Leia mais](https://helpx.adobe.com/br/campaign/kb/acs-get-started-with-emails.html)

O guia de introdução às práticas recomendadas de delivery foi atualizado. [Leia mais](../../sending/using/delivery-best-practices.md)

O modelo de dados foi integrado à documentação do Campaign Standard. [Leia mais](../../developing/using/datamodel-audience.md)

O novo ponto de extremidade de API **/customResources** foi adicionado à documentação da API.[Leia mais](../../api/using/interacting-with-custom-resources.md)

## Versão 19.4 - Outubro de 2019 {#release-19-4---october-2019}

**Novos recursos incluídos na versão**

Lei de Privacidade do Consumidor da Califórnia (CCPA) - [Leia mais](https://helpx.adobe.com/content/help/br/campaign/kb/acs-privacy.html#ccpa)

Integração do Microsoft Dynamics 365 (GA) - [Leia mais](../../integrating/using/d365-acs-get-started.md)

**Outras atualizações de documentação incluídas na versão**

A lista de mensagens de erro para o Adobe Campaign foi atualizada. [Leia mais](https://docs.campaign.adobe.com/doc/AC/en/technicalResources/error_messages/error_codes.html)

O guia de introdução ao GDPR foi melhorado e aprimorado. Agora se trata uma documentação de gerenciamento de privacidade, incluindo o GDPR e o CCPA. [Leia mais](https://helpx.adobe.com/content/help/br/campaign/kb/campaign-privacy.html)

Um novo gráfico que apresenta o processo de publicação de mensagens transacionais foi adicionado. [Leia mais](../../channels/using/publishing-transactional-message.md#transactional-messaging-pub-process)

O guia de introdução às práticas recomendadas de delivery foi movido e atualizado. [Leia mais](../../sending/using/delivery-best-practices.md)

Uma nova seção foi adicionada. Ela fornece uma visão geral dos diferentes métodos com os quais você pode enriquecer o banco de dados do Campaign Standard. [Leia mais](../../audiences/using/enriching-campaign-database.md)

Uma nova seção foi adicionada descrevendo como criar um estilo de links com o Designer de email. [Leia mais](../../designing/using/styles.md#about-styling-links)

Informações relacionadas à privacidade foram adicionadas à documentação das APIs [Clique aqui](../../api/using/creating-a-privacy-request.md)

## Set - Out de 2019 {#doc-updates-october-2019}

Uma nova seção relacionada às configurações do Campaign Standard foi adicionada. [Leia mais](../../administration/using/about-campaign-standard-settings.md)

Uma nova seção que descreve como enviar um email automático de confirmação personalizado para perfis que assinam um serviço específico foi adicionada. [Leia mais](../../audiences/using/confirming-subscription-to-a-service.md)

A seção Mensagens transacionais foi modificada com as atualizações mais recentes da interface, incluindo edição de conteúdo com o Designer de email. [Leia mais](../../channels/using/editing-transactional-message.md)

O capítulo Páginas de aterrissagem foi reorganizado. Ele também foi enriquecido com uma nova seção que detalha as etapas para configurar uma página de aterrissagem. [Leia mais](../../channels/using/getting-started-with-landing-pages.md)

Uma nova seção foi adicionada na seção Notificações por push sobre como criar e atualizar informações de perfil com base nos dados de assinatura de um aplicativo para dispositivos móveis. [Leia mais](../../channels/using/updating-profile-with-mobile-app-data.md)

Um novo exemplo que mostra como enviar um email contendo dados adicionais recuperados de uma atividade de carregamento de arquivo foi adicionado. [Leia mais](../../automating/using/sending-email-enriched-fields.md)

Uma nova seção sobre com usar coberturas foi adicionada. [Leia mais](../../sending/using/using-traps.md).

Uma observação sobre a opção **Launch_URL_Campaign** foi adicionada na página sobre como configurar um aplicativo para dispositivos móveis usando os SDKs da Adobe Experience Platform. [Leia mais](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html)

O guia do Designer de email foi reorganizado. [Leia mais](../../designing/using/designing-content-in-adobe-campaign.md)

## Agosto de 2019 {#doc-updates-august-2019}

Uma nova seção com casos de uso sobre fluxos de trabalho focados em consultas foi adicionada. [Leia mais](../../automating/using/workflow-created-query-with-complement.md)

Um procedimento foi adicionado na seção Solução de problemas do workflow, sobre como exibir consultas SQL na guia Log. [Leia mais](../../automating/using/best-practices-workflows.md#troubleshooting-data-management-activities)

Um novo artigo de ajuda foi adicionado, com informações relacionadas a gerenciamento de subdomínios e gerenciamento de certificados no Painel de controle do Campaign. [Leia mais](https://experienceleague.adobe.com/docs/control-panel/using/subdomains-and-certificates/subdomains-branding.html?lang=pt-BR)

A seção que descreve os modelos e fragmentos de conteúdo foi atualizada. [Leia mais](../../designing/using/using-reusable-content.md#content-templates)

Uma nova seção sobre como salvar conteúdo de email como modelo no Designer de email foi adicionada. [Leia mais](../../designing/using/using-reusable-content.md#saving-content-as-template)

## Versão 19.3 - Julho de 2019 {#release-19-3---july-2019}

**Novos recursos incluídos na versão**

Atividade de API externa (Beta público) - [Leia mais](../../automating/using/external-api.md)

Relatório no segmento do workflow – [Leia mais](../../reporting/using/creating-a-report-workflow-segment.md)

**Outras atualizações de documentação incluídas na versão**

O Guia de implementação do Campaign Standard agora está ativo.[Leia mais](https://helpx.adobe.com/br/campaign/kb/campaign-standard-implementation-guide.html)

Um conjunto de novos artigos de ajuda foi criado sobre a implementação e o uso do conector do Microsoft Dynamics 365. Observe que esse recurso está atualmente com a Disponibilidade limitada.[Leia mais](../../integrating/using/d365-acs-get-started.md)

Uma observação foi adicionada na seção [Chamado de workflow com parâmetros](../../automating/using/calling-a-workflow-with-external-parameters.md) sobre a preparação do delivery e o período de agregação.

Foram adicionadas informações sobre como personalizar um rótulo de delivery com variáveis de evento declaradas na atividade de sinal externo do workflow. [Leia mais](../../automating/using/external-signal.md)

Uma nova seção foi adicionada detalhando como criar um usuário no Adobe Campaign Standard. [Leia mais](../../administration/using/users-management.md)

Um novo artigo está agora disponível com dicas para simplificar campanhas de marketing, incluindo links para a documentação do produto e vídeos de tutoriais.[Leia mais](https://helpx.adobe.com/br/campaign/kb/simplify-campaign-management.html)

Uma solução de problemas para Relatórios dinâmicos foi adicionada. [Leia mais](../../reporting/using/troubleshooting.md)

Um diagrama foi adicionado explicando como os diferentes modelos no aplicativo lidam com as informações pessoais. [Leia mais](../../channels/using/preparing-and-sending-an-in-app-message.md)

A seção sobre como salvar conteúdo de email como um fragmento no Designer de email foi atualizada. [Leia mais](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment)

Um aviso foi adicionado sobre como espaços em branco adicionais podem afetar o layout de um conteúdo de email. [Leia mais](../../designing/using/personalization.md#creating-custom-content-blocks)

Uma nova seção sobre atualizações recomendadas do Email Designer foi adicionada. [Leia mais](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-updates)

<!-- A new section on how to send proofs using real customer data has been added. [Read more](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs-using-additional-data) -->

Uma nova seção sobre práticas recomendadas do workflow foi adicionada. [Leia mais](../../automating/using/best-practices-workflows.md)

A lista de mensagens de erro do Campaign Standard e do Campaign Classic foi atualizada. [Leia mais](https://docs.campaign.adobe.com/doc/AC/en/technicalResources/error_messages/error_codes.html)

Um aviso na documentação de recursos personalizados foi adicionado. Recomendamos o uso de no máximo 30 caracteres para IDs de recursos personalizados. Isso também se aplica a campos de recursos personalizados, chaves, índices e links. [Leia mais](../../developing/using/creating-or-extending-the-resource.md)

## Jun - Jul de 2019 {#doc-updates-2019}

Uma nova página sobre limitações de Páginas de aterrissagem foi adicionada. [Leia mais](../../channels/using/getting-started-with-landing-pages.md#landing-page-limitations)

Um caso de uso sobre como chamar um perfil usando uma chave de identificação composta foi adicionado. [Leia mais](../../developing/using/uc-calling-resource-id-key.md)

Uma recomendação foi adicionada sobre o uso de deliveries recorrentes sem período de agregação ao chamar um workflow com parâmetros. [Leia mais](../../automating/using/calling-a-workflow-with-external-parameters.md)

A lista de mensagens de erro do Campaign Standard e do Campaign Classic foi atualizada. [Leia mais](https://docs.campaign.adobe.com/doc/AC/en/technicalResources/error_messages/error_codes.html)

Um aviso na documentação de recursos personalizados foi adicionado. Recomendamos o uso de no máximo 30 caracteres para IDs de recursos personalizados. Isso também se aplica a campos de recursos personalizados, chaves, índices e links. [Leia mais](../../developing/using/creating-or-extending-the-resource.md)

## Versão 19.2 - Maio de 2019 {#release-19-2---may-2019}

**Novos recursos incluídos na versão**

Painel de controle do Campaign - [Leia mais](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html)

Notificações locais - [Leia mais](../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type)

Aprimoramento do workflow – Adicione um payload à atividade de sinal externo - [Leia mais](../../automating/using/calling-a-workflow-with-external-parameters.md)

Aprimoramento das Páginas de aterrissagem - Google reCAPTCHA - [Leia mais](../../channels/using/configuring-landing-page.md#setting-google-recaptcha)

**Outras atualizações de documentação incluídas na versão**

O artigo Delegação de nome de domínio foi atualizado. [Leia mais](https://helpx.adobe.com/br/campaign/kb/domain-name-delegation.html)

Um novo artigo de Planejamento de versão foi publicado para compartilhar datas de lançamento futuras. [Leia mais](https://helpx.adobe.com/br/campaign/kb/acs-release-planning.html)

Os links de ajuda contextual disponíveis diretamente do Adobe Campaign foram atualizados.

Esta [página](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/overview.html?lang=pt-BR) é agora a página oficial de Vídeos do Adobe Campaign Standard.

Uma seção foi adicionada sobre retenção de dados que inclui os valores de retenção padrão para tabelas padrão. [Leia mais](../../administration/using/data-retention.md)

Uma seção foi adicionada sobre atualizações e operações de manutenção. [Leia mais](../../administration/using/updates-and-maintenance-operations.md)

Foram adicionadas informações sobre a nova opção de classificação na atividade **Transferência de arquivo**. [Leia mais](../../automating/using/transfer-file.md)

A [documentação das APIs REST](../../api/using/get-started-apis.md) foi atualizada:

* Uma nova seção foi adicionada com informações genéricas sobre por que usar as APIs REST do Campaign Standard.
* Uma coleção de solicitações de API pré-projetadas foi disponibilizada, representando casos de uso comuns.
* Uma nova seção foi adicionada sobre como gerenciar Unidades organizacionais.
* Foram adicionadas informações sobre como criar um serviço.
* Foram adicionadas informações sobre como chamar um workflow com parâmetros.

Foram adicionadas informações sobre a nova atividade **Test**. [Leia mais](../../automating/using/test.md)

O guia de Automatização foi atualizado com links para atividades de workflow relacionadas. [Leia mais](../../automating/using/workflow-interface.md#palette)

A seção Cálculo de indicadores para relatórios dinâmicos foi atualizada. [Leia mais](../../reporting/using/indicator-calculation.md)

A tabela de compatibilidade de relatórios dinâmicos foi adicionada para um melhor entendimento da compatibilidade entre dimensões e métricas. [Leia mais](https://experienceleague.adobe.com/docs/campaign-standard/assets/dynamic_report_compatibility.pdf?lang=en)

A lista de funções para fluxos de trabalho foi atualizada. [Leia mais](../../automating/using/list-of-functions.md)

O capítulo Design de conteúdo foi reorganizado e aprimorado. Ele traz uma nova seção que descreve claramente os diferentes métodos para criar um email com o Designer de email usando conteúdos existentes. [Leia mais](../../designing/using/using-existing-content.md)

Uma nova seção sobre como salvar conteúdo de email como um fragmento no Designer de email foi adicionada. [Leia mais](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment)

A seção Gerenciar links foi atualizada com informações adicionais sobre como gerenciar URLs rastreados no Designer de email. [Leia mais](../../designing/using/links.md#inserting-a-link)

Uma nova seção foi adicionada para descrever o processo específico de repetição de mensagens transacionais. [Leia mais](../../channels/using/transactional-message-execution.md#transactional-message-retry-process)

A seção Publicação de um recurso com extensão da API foi esclarecida e atualizada com as alterações mais recentes da interface. [Leia mais](../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension)

A seção Arquivamento de emails foi renomeada e reorganizada. [Leia mais](../../sending/using/archiving.md)

A seção Criação de um email foi atualizada para refletir as alterações mais recentes na interface. [Leia mais](../../channels/using/creating-an-email.md)

O artigo Base de conhecimento de [configurações e protocolo do conector SMS](https://helpx.adobe.com/br/campaign/kb/sms-connector-protocol-and-settings.html) foi atualizado. Ele apresenta a nova opção adicionada à conta externa de SMS para limitar o número de instâncias de MTA permitidas para conexão com o provedor SMPP.

O Guia de Introdução foi enriquecido e reorganizado. [Leia mais](../../start/using/about-campaign-standard.md)

A página de Recursos obsoletos e removidos foi atualizada. [Leia mais](../../rn/using/deprecated-features.md)

A seção de integração do Dreamweaver foi atualizada e aprimorada. [Leia mais](../../designing/using/using-integrations.md#editing-content-in-dreamweaver)

## Versão 19.1 - Fevereiro de 2019 {#release-19-1---february-2019}

**Novos recursos incluídos na versão**

Melhorias nos Relatórios do canal de push - [Leia mais](../../reporting/using/push-notification-report.md)

Integração do Launch para aplicativos de dispositivos móveis - [Leia mais](../../administration/using/configuring-a-mobile-application.md#using-adobe-experience-platform-sdk)

Mensagens no aplicativo móvel - [Leia mais](../../channels/using/about-in-app-messaging.md)

Melhorias no workflow – Leia mais [aqui](../../automating/using/workflow-interface.md#duplicating-workflow-activities) e [aqui](../../automating/using/load-file.md#configuration)

**Outras atualizações de documentação incluídas na versão**

A nova experiência de integração para criar conteúdos de email e outras melhorias no Designer de email foram adicionadas ao capítulo Edição de conteúdo de email. [Leia mais](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-home-page)

Uma nova seção sobre limitações de Mensagens transacionais foi adicionada. [Leia mais](../../channels/using/transactional-messaging-limitations.md)

Uma nova seção que compara as diferentes opções de criação de email no Adobe Campaign foi adicionada. [Leia mais](../../designing/using/using-integrations.md#email-design-options-comparison)

A seção Criação de blocos de conteúdo personalizados foi aprimorada com detalhes sobre targeting dimensions. [Leia mais](../../designing/using/personalization.md#creating-custom-content-blocks)

Um aviso foi adicionado indicando que o Designer de email não é compatível com o Internet Explorer 11. [Leia mais](../../administration/using/about-configuration-guidelines.md)

Avisos sobre o impacto da reformulação foram adicionados à seção Exclusão de recurso. [Leia mais](../../developing/using/deleting-a-resource.md)

O capítulo sobre como adicionar ou estender um recurso foi atualizado. [Leia mais](../../developing/using/creating-or-extending-the-resource.md)

Um caso de uso foi adicionado sobre como estender o recurso personalizado de perfis. [Leia mais](../../developing/using/extending-the-profile-resource-with-a-new-field.md)

Foram adicionadas informações sobre como vincular recursos personalizados. [Leia mais](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources)

Uma nova nota técnica foi adicionada sobre como exibir uma imagem de uma notificação por push do Adobe Campaign Standard. [Leia mais](../../administration/using/image-push-notification.md)

Uma nova nota técnica sobre implementação do rastreamento de notificação por push foi adicionada. [Leia mais](../../administration/using/push-tracking.md)

A lista de mensagens de erro do Campaign Standard e do Campaign Classic foi atualizada. [Leia mais](https://docs.campaign.adobe.com/doc/AC/en/technicalResources/error_messages/error_codes.html)

A documentação de integração dos Acionadores e do Campaign foi atualizada. [Leia mais](../../integrating/using/about-adobe-experience-cloud-triggers.md)

Atualização dos links de ajuda contextual disponíveis diretamente do Adobe Campaign.

Uma observação foi adicionada sobre a adição de data e hora no nome do arquivo que contém as rejeições. [Leia mais](../../automating/using/load-file.md#configuration)

Foram adicionadas informações ao importar campos compostos por colunas com comprimento corrigido. [Leia mais](../../automating/using/load-file.md#configuration)

Foram adicionadas informações sobre a opção que permite manter as rejeições em um arquivo. Essa opção agora permite aplicar uma etapa de pós-processamento ao arquivo que contém as rejeições. [Leia mais](../../automating/using/load-file.md#configuration)

Adição de uma nova seção sobre como duplicar atividades de workflow por meio de operações de copiar e colar. [Leia mais](../../automating/using/workflow-interface.md#duplicating-workflow-activities)

Foram adicionadas informações sobre a nova opção das atividades de Query ( [Leia mais](../../automating/using/query-samples.md)) e Segmentação ( [Leia mais](../../automating/using/segmentation.md)), que permitem adicionar uma transição de saída após a atividade, caso a atividade não recupere dados.

Foram adicionadas informações na seção Atualização de atividade de dados no novo campo Batch size, que permite definir o tamanho máximo do lote para upload de dados. [Leia mais](../../automating/using/update-data.md#configuration)

Foram adicionadas informações na seção da atividade Extrair arquivo sobre a nova opção que permite desativar o processo de geração de arquivos, se a transição de saída estiver vazia. [Leia mais](../../automating/using/extract-file.md#configuration)

## Versão 19.0 – Janeiro de 2019 {#release-19-0---january-2019}

**Novos recursos incluídos na versão**

Disponibilidade geral do Designer de email - [Leia mais](../../designing/using/designing-content-in-adobe-campaign.md)

Listas de produtos em Emails transacionais - [Leia mais](../../designing/using/using-product-listings.md)

Visualização de publicação de conteúdo para dispositivos móveis no Designer de email - [Leia mais](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view)

Melhorias beta nas Mensagens no aplicativo - [Leia mais](../../channels/using/about-in-app-messaging.md)

**Outras atualizações de documentação incluídas na versão**

O guia Design de conteúdo foi atualizado para refletir a disponibilidade geral do Designer de email e a descontinuação do editor herdador de conteúdo de email. [Leia mais](../../designing/using/designing-content-in-adobe-campaign.md)

Atualização da documentação de [Mensagens no aplicativo](../../channels/using/about-in-app-messaging.md) e [Notificações de push](../../channels/using/about-push-notifications.md).

Foram adicionadas mais informações sobre os diferentes tipos de públicos no Adobe Campaign. [Leia mais](../../audiences/using/about-audiences.md)

Atualização do capítulo Usuários e Segurança para refletir a depreciação das unidades geográficas. [Leia mais](../../administration/using/organizational-units.md)

Foram adicionadas informações sobre a nova opção na atividade Carregar dados, que permite aplicar uma etapa de pós-processamento ao arquivo que contenha os registros rejeitados (por exemplo, compactação no formato Zip). [Leia mais](../../automating/using/load-file.md)

Foram adicionadas informações sobre o novo campo na atividade Update data, que permitem configurar o tamanho máximo do lote para upload dos dados. [Leia mais](../../automating/using/update-data.md)

Atualização da documentação [Importação de conteúdo de URL](../../designing/using/using-existing-content.md#importing-content-from-a-url) com informações relacionadas ao Designer de email.

O Microsoft Edge (versão mais recente) foi adicionado à lista de navegadores compatíveis para computadores. [Leia mais](../../administration/using/about-configuration-guidelines.md)

Foram adicionadas informações sobre a nova opção na atividade Extract file, que impede a geração de um arquivo, caso a transição de entrada estiver vazia. [Leia mais](../../automating/using/extract-file.md)

A seção Configuração de um aplicativo para dispositivos móveis usando o SDK V4 foi movida e agora encontra-se [aqui](https://helpx.adobe.com/br/campaign/kb/configuring-app-sdkv4.html).

A seção Configuração de um aplicativo para dispositivos móveis usando SDKs da Adobe Experience Platform foi movida e agora encontra-se [aqui](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

Os vídeos foram atualizados e movidos, e agora encontram-se [aqui](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/overview.html).

A seção Tipo de usuários foi atualizada. [Leia mais](../../administration/using/users-management.md)

## Versão 18.9 - Setembro de 2018 {#release-18-9---september-2018}

**Novos recursos incluídos na versão**

Mensagens no aplicativo (beta) - [Leia mais](../../channels/using/about-in-app-messaging.md)

Integração do Adobe Launch para aplicativos de dispositivos móveis (beta) - [Leia mais](../../sending/using/managing-typologies.md)

**Outras atualizações de documentação incluídas na versão**

Atualização do guia Notificação por push, com alterações na interface. [Leia mais](../../channels/using/about-push-notifications.md)

Foram adicionadas informações sobre como excluir um público. [Leia mais](../../audiences/using/creating-audiences.md#deleting-audiences)

Atualização da seção Relatório integrado de notificação por push. [Leia mais](../../reporting/using/push-notification-report.md)

## Versão 18.7 - Julho de 2018 {#release-18-7---july-2018}

**Novos recursos incluídos na versão**

[Sinalizador de alta prioridade](../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-android) e [filtro de tipologia](../../sending/using/managing-typologies.md) para assinantes de aplicativos para dispositivos móveis.

Importação de conteúdo automatizada de um URL no momento da preparação. [Leia mais](../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time)

**Outras atualizações de documentação incluídas na versão**

Uma nova nota técnica foi adicionada sobre o protocolo e as configurações do conector SMS. [Leia mais](https://helpx.adobe.com/campaign/kb/sms-connector-protocol-and-settings.html)

Atualização da documentação de Integração do Experience Manager com o Adobe Campaign. [Leia mais](../../reporting/using/creating-a-custom-profile-dimension.md)

O guia Design de conteúdo foi totalmente reorganizado, especialmente para apresentar os dois editores com os quais se pode projetar conteúdo para emails. [Leia mais](../../designing/using/designing-content-in-adobe-campaign.md)

Saiba como tornar o conteúdo externo totalmente editável com o Creative SDK, criando fragmentos de seus emails existentes. [Leia mais](../../designing/using/designing-from-scratch.md)

A lista de atributos HTML para conformidade total com o Creative Designer agora está disponível nesta [seção](../../designing/using/using-existing-content.md#editing-existing-contents-with-the-email-designer).

Foram adicionadas informações sobre o idioma padrão para o modelo multilíngue. [Leia mais](../../channels/using/multilingual-messages-template.md)

O guia Usuários e Segurança foi atualizado para refletir a depreciação do recurso de unidade geográfica para novas instâncias do Campaign Standard, bem como instâncias existentes sem unidades geográficas criadas, a partir da versão 18.7. [Leia mais](../../rn/using/deprecated-features.md)

## Versão 18.6 - Junho de 2018 {#release-18-6---june-2018}

**Novos recursos incluídos na versão**

A documentação da API foi atualizada com informações sobre a API do **Histórico**. Um caso de uso foi adicionado sobre como recuperar a mirror page de um delivery enviado a um perfil. [Leia mais](../../api/using/interacting-with-marketing-history.md)

**Outras atualizações de documentação incluídas na versão**

A documentação de integração dos Acionadores e do Campaign foi atualizada e reorganizada. [Leia mais](../../integrating/using/about-adobe-experience-cloud-triggers.md)

Um caso de uso foi adicionado sobre como criar passo a passo uma dimensão de perfil personalizada. [Leia mais](../../reporting/using/creating-a-custom-profile-dimension.md)

A documentação Trabalho com o Campaign e o Audience Manager ou o serviço principal Pessoas. [Leia mais](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md)

Atualização da definição da função Preparar deliveries. [Leia mais](../../administration/using/list-of-roles.md)

Adição de um exemplo na seção da atividade de query sobre como segmentar perfis que clicaram em um link específico em um delivery. [Leia mais](../../automating/using/query-samples.md#targeting-profiles-who-clicked-a-specific-link-)

Adicionada uma seção na documentação da API relacionada aos **filtros personalizados**. [Leia mais](../../api/using/filtering.md)

## Versão 18.5 - Maio de 2018 {#release-18-5---may-2018}

**Novos recursos incluídos na versão**

GDPR: Integração de serviço principal - [Leia mais](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-management.html?lang=pt-BR)

Aprimoramentos de Notificações por push - feedback detalhado do delivery - [Leia mais](../../channels/using/preparing-and-sending-a-push-notification.md#sending-the-notification)

Extensão Logs do delivery - [Leia mais](../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension)

Relatórios dinâmicos com Dados de perfil personalizados - [Leia mais](../../channels/using/creating-a-multilingual-push-notification.md)

**Outras atualizações de documentação incluídas na versão**

Adicionada a lista de métricas do Campaign encontradas no Analytics. [Leia mais](../../integrating/using/campaign-dimensions-and-metrics-in-analytics.md)

Foram adicionadas informações sobre a opção Licenças no menu Administração [Leia mais](../../administration/using/licenses.md)

Foram adicionadas informações sobre como usar campos personalizados em uma notificação por push. [Leia mais](../../channels/using/customizing-a-push-notification.md#add-custom-fields)

Atualização do guia passo a passo de práticas recomendadas do delivery. [Leia mais](../../sending/using/delivery-best-practices.md)

Foram adicionadas informações sobre tipos de logs de rastreamento. [Leia mais](../../sending/using/tracking-messages.md#tracking-logs)

A seção da atividade de consulta foi atualizada com amostras de consultas. [Leia mais](../../automating/using/query.md#query-samples)

A seção dedicada à inclusão na lista de bloqueios foi renomeada para “Conhecimento sobre os processos de aceitação e recusa”. Essa seção foi atualizada com informações sobre como gerenciar aceitações para canais específicos e como configurar páginas de aterrissagem para gerenciar aceitações e recusas. [Leia mais](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

Conheças as práticas recomendadas para usar os servidores SFTP hospedados pela Adobe. [Leia mais](../../administration/using/external-accounts.md#sftp-external-account)

A lista de SKUs do Analytics compatíveis para integração com os Acionadores foi atualizada. [Leia mais](../../integrating/using/configuring-triggers-in-experience-cloud.md#configuring-solutions-and-services)

Algumas páginas da documentação do editor de conteúdo foram mescladas para oferecer uma visualização mais abrangente das diferentes ações disponíveis. [Leia mais](../../designing/using/designing-content-in-adobe-campaign.md)

## Versão 18.3 — março de 2018 {#release-18-3---march-2018}

**Novos recursos incluídos na versão**

Regulamento Geral sobre a Proteção de Dados da União Europeia (GDPR) - [Leia mais](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GDPR.html)

Creative Designer para Email - [Leia mais](../../designing/using/designing-content-in-adobe-campaign.md)

Deliveries de push multilíngues - [Leia mais](../../channels/using/creating-a-multilingual-push-notification.md)

Uso de recursos personalizados em mensagens transacionais - [Leia mais](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)

**Outras atualizações de documentação incluídas na versão**

A API do GDPR reagrupa recursos que permitem o processamento automático de solicitações do GDPR. [Leia mais](../../api/using/creating-a-privacy-request.md)

Foram adicionadas informações sobre como configurar landing pages para que seus recipients possam ser incluídos na lista de bloqueios. [Leia mais](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md)

A seção [Configuração de mensagens transacionais](../../channels/using/configuring-transactional-event.md) foi reorganizada e um [caso de uso passo a passo](../../channels/using/transactional-messaging-use-case.md) foi adicionado.

Uma nota técnica foi adicionada sobre como gerar um arquivo CSV multilíngue para usar nas notificações por push. [Leia mais](https://helpx.adobe.com/br/campaign/kb/acs-generate-csv-multilingual-push.html).

Foram adicionadas informações sobre o template de importação **Atualização de quarentenas de correspondência direta e logs do delivery**. [Leia mais](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates)

A lista do fluxos de trabalho técnicos foi atualizada. [Leia mais](../../administration/using/technical-workflows.md)

A seção da atividade de Scheduler foi atualizada. [Leia mais](../../automating/using/scheduler.md)

A lista de materiais de ajuda sobre a integração do Campaign e das soluções Adobe foi atualizada. [Leia mais](../../integrating/using/get-started-campaign-integrations.md).

A ajuda contextual do Campaign Standard no produto foi atualizada.

## Versão 18.2 - Fevereiro de 2018 {#release-18-2---february-2018}

**Novos recursos incluídos na versão**

Assinatura - assine ou cancele a assinatura de uma lista de perfis para vários serviços - [Leia mais](../../automating/using/subscription-services.md)

Atividade de Enriquecimento - enriqueça os dados com base em transições anteriores - [Leia mais](../../automating/using/enrichment.md)

**Outras atualizações de documentação incluídas na versão**

A maioria dos URLs para integrações do Campaign e das soluções Adobe foi alterada! Verifique os marcadores. [Leia mais](../../integrating/using/get-started-campaign-integrations.md)

O datamodel v1 agora está disponível com a estrutura SQL para recursos incorporados - [Leia mais](https://docs.adobe.com/content/help/pt-BR/campaign-standard/using/developing/datamodel/datamodel-audience.html)

Foram adicionadas informações sobre como preparar uma mensagem em um delivery [Leia mais](../../sending/using/preparing-the-send.md)

As notas de versão foram reorganizadas em várias páginas para que você obtenha uma visualização mais global de todas as diferentes versões.

A seção **[!UICONTROL Working with typologies]** foi atualizada para melhorar a visibilidade. [Leia mais](../../sending/using/about-typology-rules.md)

Uma nova opção que permite obter desempenho ao definir muitos dados adicionais em um **[!UICONTROL Query]** está agora disponível. [Leia mais](../../automating/using/query-samples.md)

O exemplo de importação de perfil foi atualizado com algumas dicas para que seus perfis estejam prontos para receber malas diretas. [Leia mais](../../automating/using/about-data-import-and-export.md)

Uma nova atividade está disponível nos fluxos de trabalho: a atividade **[!UICONTROL Enrichment]**. [Leia mais](../../automating/using/enrichment.md)

A atividade **[!UICONTROL Subscription Services]** foi atualizada para ser compatível com mais casos de uso, incluindo o uso de um único arquivo para atualizar assinaturas para vários serviços. [Leia mais](../../automating/using/subscription-services.md)

Adicionado um caso de uso passo a passo sobre como preparar um delivery. [Leia mais](../../sending/using/preparing-the-send.md)

A seção que inclui a lista de autorizações foi retirada. [Leia mais](https://experienceleague.adobe.com/docs/campaign-standard/assets/acs_rights.pdf?lang=en) (PDF).

Um caso de uso passo a passo foi adicionado sobre como usar a resposta automática do SMS. [Leia mais](../../channels/using/managing-incoming-sms.md#managing-stop-sms)

Foram adicionadas informações sobre como enviar um delivery dependendo dos fusos horários dos usuários em um workflow recorrente. [Leia mais](../../automating/using/recurring-push-notifications.md)

A seção **[!UICONTROL Customizing a push notification]** foi reorganizada com casos de uso passo a passo. [Leia mais](../../channels/using/customizing-a-push-notification.md)

Nova seção dedicada ao gerenciamento de lista de bloqueios. [Leia mais](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

Informações sobre falhas de delivery e quarentenas foram atualizadas. [Leia mais](../../sending/using/monitoring-a-delivery.md)

Novas seções dedicadas a [mapeamentos de público-alvo](../../administration/using/target-mappings-in-campaign.md) e [targeting dimensions e recursos](../../automating/using/query.md#targeting-dimensions-and-resources).

## Versão 18.1 – Janeiro de 2018 {#release-18-1---january-2018}

**Novos recursos incluídos na versão**

Relatórios para gerenciamento de fadiga - [Leia mais](../../sending/using/fatigue-rules.md#viewing-the-fatigue-rule-summary-report)

Compartilhamento de relatórios - [Leia mais](../../reporting/using/reporting-interface.md#share-tab)

Melhorias nas notificações por push - Leia mais [aqui](../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification) e [aqui](../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-ios)

Deliveries otimizados para fuso horários - [Leia mais](../../automating/using/scheduler.md)

Acionamento da atividade de Sinal da API - [Leia mais](../../api/using/triggering-a-signal-activity.md)

**Outras atualizações de documentação incluídas na versão**

Atualização da seção de criação do serviço. [Leia mais](../../audiences/using/creating-a-service.md)

Casos de uso foram adicionados para melhor compreensão de grupos e unidades de segurança. [Leia mais](../../administration/using/organizational-units.md)

Definições e cálculos de dimensões, métricas e segmentos em relatórios dinâmicos foram aprimorados. [Leia mais](../../reporting/using/list-of-components-.md)

Foram adicionadas informações sobre como recuperar mensagens SMS recebidas com um workflow. [Leia mais](../../administration/using/configuring-sms-channel.md)

Foram adicionadas informações sobre Configurações de historização, da atividade Transfer file. [Leia mais](../../automating/using/transfer-file.md)

Instruções para configurar a integração com o Audience Manager ou com o serviço principal Pessoas foram atualizadas. [Leia mais](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md)

## Versão 17.10 - Outubro de 2017 {#release-17-10---october-2017}

**Novos recursos incluídos na versão**

Gerenciamento de fadiga - [Leia mais](../../sending/using/fatigue-rules.md)

Criação de conteúdo: Importar de um URL - [Leia mais](../../designing/using/using-existing-content.md#importing-content-from-a-url)

**Outras atualizações de documentação incluídas na versão**

A amostra de teste A/B foi atualizada. [Leia mais](../../channels/using/designing-an-a-b-test-email.md)

Nova nota técnica sobre como criar ou atualizar dados de perfil quando um aplicativo móvel envia dados de &quot;Coletar PII&quot;. [Leia mais](https://helpx.adobe.com/br/campaign/kb/acs-updating-profile-based-on-subscription.html)

Uma seção foi adicionada sobre novos recursos de rastreamento de exportação. [Leia mais](../../administration/using/auditing-export-logs.md)

Foram adicionadas precisões sobre a exportação de pacotes incorporados. [Leia mais](../../automating/using/managing-packages.md)

Definição de conta externa e amostras foram atualizadas. [Leia mais](../../administration/using/external-accounts.md)

Várias capturas de tela foram atualizadas para refletir as alterações nas categorias do Editor de consultas.

A seção de [Alertas de delivery](../../sending/using/receiving-alerts-when-failures-happen.md) foi movida e reorganizada.

A seção Recursos personalizados foi esclarecida com um procedimento mais detalhado sobre como [definir filtros](../../developing/using/configuring-filter-definition.md).

A [nota técnica](https://helpx.adobe.com/br/campaign/kb/integrate-mobile-sdk.html) sobre como integrar o SDK móvel da Adobe Marketing Cloud com um aplicativo para dispositivos móveis foi atualizada e esclarecida. A integração permite receber notificações por push do Adobe Campaign Standard.

Uma nota técnica foi adicionada explicando a estrutura do payload recebido em um aplicativo móvel. [Leia mais.](../../administration/using/push-payload.md)

A [seção](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html) Configuração do canal de push foi atualizada com novos dados de payload na versão do OS a serem adicionados ao definir postbacks na interface do Adobe Mobile Services.

A documentação do SMS foi atualizada com alguns esclarecimentos adicionados à seção [Respostas automáticas de SMS](../../channels/using/managing-incoming-sms.md#managing-stop-sms).

Nova seção dedicada ao gerenciamento de workflow por meio da API. [Leia mais](../../api/using/controlling-a-workflow.md)

Nova seção dedicada às chaves primárias e ao uso de uma ID empresarial como chave na API. [Leia mais](../../api/using/get-started-apis.md)

Informações foram adicionadas sobre filtragens simples e múltiplas na API. [Leia mais](../../api/using/filtering.md)

## Versão 17.9 - Setembro de 2017 {#release-17-9---september-2017}

**Novos recursos incluídos na versão**

Biblioteca de modelos de email - [Leia mais](../../designing/using/using-reusable-content.md#content-templates)

Relatórios dinâmicos com dados de perfil - [Leia mais](../../reporting/using/about-dynamic-reports.md)

Aprimoramento nas assinaturas em massa - [Leia mais](../../automating/using/subscription-services.md)

**Outras atualizações de documentação incluídas na versão**

Lista detalhada de todos os componentes disponíveis nos Relatórios dinâmicos e algumas alterações em fórmulas. [Leia mais](../../reporting/using/list-of-components-.md)

Lista detalhada de KPIs compartilhados com o Adobe Analytics. [Leia mais](../../integrating/using/campaign-dimensions-and-metrics-in-analytics.md)

Novo vídeo sobre Relatórios dinâmicos.

Recomendações de conta S3 foram adicionadas. [Leia mais](../../administration/using/external-accounts.md#amazon-s3-account-recommendations)

A seção sobre os diferentes tipos de usuários foi atualizada. [Leia mais](../../administration/using/users-management.md)

A seção sobre a personalização da fonte de imagem foi atualizada. [Leia mais](../../designing/using/personalization.md#personalizing-an-image-source)

Foi adicionada uma documentação no relatório de perfis ativos. [Leia mais](../../audiences/using/active-profiles.md)

A documentação [Alerta de deliveries](../../sending/using/receiving-alerts-when-failures-happen.md#delivery-alerting-reasons) foi atualizada com uma seção de solução de problemas que apresenta dicas sobre as ações que você pode tomar ao receber alertas.

Um novo guia de introdução está disponível: ele apresenta algumas práticas recomendadas que podem ser usadas para fazer entregas com o Adobe Campaign, desde a criação e o direcionamento até o envio e o monitoramento. [Leia mais](https://helpx.adobe.com/br/campaign/kb/delivery-best-practices.html)

A documentação das mensagens de acompanhamento foi atualizada com um caso de uso aprimorado. [Leia mais](../../channels/using/follow-up-messages.md#sending-a-follow-up-message)

Documentação adicionada à ID ACS. [Leia mais](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources)

Novas funções de criptografia e hash forma adicionadas com exemplos. [Leia mais](../../automating/using/list-of-functions.md)

A seção sobre a atividade do workflow Transferir arquivo foi atualizada. [Leia mais](../../automating/using/transfer-file.md)

Informações foram adicionadas na opção “Solicitar confirmação antes de enviar mensagens”, na atividade do workflow Delivery de email. [Leia mais](../../automating/using/email-delivery.md)

## Versão 17.7 - Julho de 2017 {#release-17-7---july-2017}

**Novos recursos incluídos na versão**

Deliveries multilíngues (Email e SMS) - [Leia mais](../../channels/using/creating-a-multilingual-email.md)

Notificações do Adobe Campaign - [Leia mais](../../administration/using/sending-internal-notifications.md)

Alertas de deliveries - [Leia mais](../../sending/using/receiving-alerts-when-failures-happen.md)

ID declarada criptografada em fontes de dados - [Leia mais](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md)

Compartilhamento de KPI do Campaign para o Analytics - [Leia mais](../../integrating/using/about-campaign-analytics-integration.md)

Canal de correspondência direta - Retorno ao remetente, [Leia mais](../../channels/using/return-to-sender.md)

**Outras atualizações de documentação incluídas na versão**

Os guias de introdução e os vídeos de instruções foram reagrupados em uma seção dedicada.

A documentação de renderização de Emails foi atualizada. [Leia mais](../../sending/using/email-rendering.md)

A tabela de cálculo de indicadores de relatórios foi atualizada. [Leia mais](../../reporting/using/indicator-calculation.md)

A documentação dos relatórios foi atualizada com quatro novas métricas. [Leia mais](../../reporting/using/list-of-components-.md)

Documentação adicionada sobre a geração de IDs exclusivas para perfis. [Leia mais](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources)

O mecanismo de dupla aceitação agora está documentado por meio de um procedimento passo a passo. [Leia mais](../../channels/using/setting-up-a-double-opt-in-process.md)

A seção Lista de funções foi atualizada. [Leia mais](../../administration/using/list-of-roles.md)

## Versão 17.5 - Maio de 2017 {#release-17-5---may-2017}

**Novos recursos incluídos na versão**

Correspondência direta - [Leia mais](../../channels/using/about-direct-mail.md)

Cco de emails - [Leia mais](../../sending/using/archiving.md)

**Outras atualizações de documentação incluídas na versão**

O guia &quot;Deliveries&quot; foi reorganizado e renomeado para &quot;Channels&quot;. [Leia mais](../../channels/using/get-started-communication-channels.md)

Várias capturas de tela foram atualizadas para refletir as alterações na interface.

Uma nova nota técnica agora está disponível: &quot;Integração do SDK móvel da Adobe com seu aplicativo para dispositivos móveis&quot;. [Leia mais](https://helpx.adobe.com/campaign/kb/integrate-mobile-sdk.html)

Foram adicionadas instruções para configurar a integração do serviço principal do People ou Audience Manager com o Adobe Campaign. [Leia mais](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md)

A tabela de autorizações foi revisada para esclarecer melhor certas funções. [Leia mais](https://experienceleague.adobe.com/docs/campaign-standard/assets/acs_rights.pdf?lang=en)

Atualização dos links de ajuda contextual disponíveis diretamente do Adobe Campaign.

## Versão 17.4 - Abril de 2017 {#release-17-4---april-2017}

**Novos recursos incluídos na versão**

Recursos de edição de imagens formas aprimorados com o SDK do Creative - [Leia mais](../../designing/using/images.md#modifying-images-with-the-adobe-creative-sdk)

Notificações por push transacionais - [Leia mais](../../channels/using/transactional-push-notifications.md)

Notificações por push recorrentes - [Leia mais](../../automating/using/push-notification-delivery.md)

Conector S3 (Simple Storage Service) da Amazon - [Leia mais](../../administration/using/external-accounts.md)

Integração do Dreamweaver ativa - [Leia mais](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html?lang=pt-BR)

**Outras atualizações de documentação incluídas na versão**

Seção adicionada sobre os diferentes tipos de usuários do Adobe Campaign. [Leia mais](../../administration/using/users-management.md)

O guia Workflow foi reorganizado e estendido. Descubra facilmente como [criar](../../automating/using/building-a-workflow.md) e [executar](../../automating/using/about-workflow-execution.md) um fluxo de trabalho, como [segmentar](../../automating/using/about-targeting-activities.md) e [gerenciar](../../automating/using/about-targeting-activities.md#enriching-data) os dados, como [importar e exportar](../../automating/using/about-data-import-and-export.md) dados e como usar os dados do workflow para atualizar o banco de dados ou enviar deliveries.

O cálculo do indicador de relatórios agora está disponível para relatórios dinâmicos, incluindo descrição completa e fórmula de cálculo. [Leia mais](../../reporting/using/indicator-calculation.md)

Nova seção dedicada sobre a configuração do Adobe Mobile Services para usar notificações por push e dados de Pontos de interesse no Adobe Campaign. [Leia mais](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)

As seções de configuração e implementação do aplicativo para dispositivos móveis foram atualizadas, incluindo etapas mais detalhadas para configurar e enviar notificações por push. [Leia mais](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)

A seção sobre como trabalhar com imagens no Campaign foi atualizada. [Leia mais](../../designing/using/images.md#setting-up-image-properties)

A integração com o Adobe Analytics para dispositivos móveis (Pontos de interesse) foi atualizada, incluindo etapas de configuração e caso de uso. [Leia mais](../../integrating/using/about-campaign-points-of-interest-data-integration.md)

## Versão 17.2 - Março de 2017 {#release-17-2---march-2017}

**Novos recursos incluídos na versão**

Relatórios dinâmicos - [Leia mais](../../reporting/using/about-dynamic-reports.md)

Integração do Dreamweaver (Labs) - [Leia mais](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html)

Otimização manual do tempo de envio - [Leia mais](../../sending/using/optimizing-the-sending-time.md)

Notificações por push: melhorias - [Leia mais](../../channels/using/about-push-notifications.md)

Fluxos de trabalho: nova atividade de sinal - [Leia mais](../../automating/using/external-signal.md)

Fluxos de trabalho: nova atividade de leitura de público - [Leia mais](../../automating/using/read-audience.md)

Dados de pontos de interesse - [Leia mais](../../integrating/using/about-campaign-points-of-interest-data-integration.md)

Recursos vinculados em APIs REST - [Leia mais](../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension)

**Outras atualizações de documentação incluídas na versão**

Integração de acionadores: foram adicionados dois casos de usos. [Leia mais](../../integrating/using/abandonment-triggers-use-cases.md)

Reprojetamos a documentação da API do desenvolvedor com novas informações e trechos de código para uma melhor experiência do usuário. [Leia mais](../../api/using/get-started-apis.md)

Descubra exemplos das novas atividades de workflow [Ler público](../../automating/using/read-audience.md) e [Sinal externo](../../automating/using/external-signal.md).

## Versão 17.1 – Janeiro de 2017 {#release-17-1---january-2017}

**Novos recursos incluídos na versão**

Exportação de logs para relatórios externos – [Leia mais](../../automating/using/exporting-logs.md)

API de mensagens transacionais – [Leia mais](../../api/using/get-started-apis.md)

Recursos de marketing para mensagens transacionais – [Leia mais](../../channels/using/editing-transactional-message.md#profile-transactional-message-specificities)

**Outras atualizações de documentação incluídas na versão**

Atividade do workflow Query incremental: novo modo incremental – [Leia mais](../../automating/using/incremental-query.md)

Atualização da atividade do workflow Scheduler – [Leia mais](../../automating/using/scheduler.md)

Alteração de URL: Serviço principal do Assets – [Leia mais](../../integrating/using/working-with-campaign-and-assets-core-service.md)

Alteração de URL: Serviço principal do People – [Leia mais](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md)

O guia de Perfis e Públicos foi reorganizado. [Leia mais](../../audiences/using/get-started-profiles-and-audiences.md)
