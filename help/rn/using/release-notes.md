---
solution: Campaign Standard
product: campaign
title: Versão mais recente
description: Esta página detalha o conteúdo da versão mais recente do Campaign Standard
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
feature: Visão geral
role: Business Practitioner
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: e4d5be678b49af649bd4d4dabd83bff04c675d9f
workflow-type: tm+mt
source-wordcount: '1000'
ht-degree: 6%

---

# Versão mais recente{#latest-release}

## Versão 21.2 - Junho de 2021 {#release-21-2---june-2021}

Novos recursos, melhorias e correções incluídos na próxima versão do Campaign Standard estão listados nas [Notas de versão antecipadas](e-release-notes.md).

**Aprimoramentos**

* Ao criar uma landing page, agora é possível adicionar uma caixa de seleção obrigatória que os perfis precisam marcar antes de enviar o formulário. Para obter mais informações consulte a [documentação detalhada](../../channels/using/managing-landing-page-form-data.md#agreement-checkbox).

* Para a integração dos acionadores, a mensagem de erro exibida quando não há dados de reconciliação chegando na carga do acionador foi aprimorada: &quot;Dados de alias ausentes da carga&quot;.

* O desempenho para recuperar notificações por push da fila foi aprimorado.

**Outras alterações**

* O mecanismo de assinatura do URL para links de rastreamento foi desabilitado para evitar que um problema que fazia com que alguns links de rastreamento válidos e assinados fossem bloqueados incorretamente após serem modificados por ferramentas de segurança de terceiros.

* Em deliveries com várias variantes, os usuários não poderão mais criar cópias de idioma se a variante padrão tiver sido excluída. Uma mensagem agora é exibida durante a criação da cópia de idioma. (CAMP-48235)

* O processo de exclusão de perfil de duas etapas (obsoleto a partir da versão 19.4 do Campaign) agora está desativado por padrão. Anteriormente, era necessário desativá-lo manualmente na interface do Campaign antes de usar o Privacy Core Service. Não fazer isso faria com que as solicitações de exclusão permanecessem no estado pendente sem concluir.

* Uma nova função de agregação &quot;StringAgg&quot; foi introduzida para concatenar os valores de uma coluna do tipo string. (CAMP-47077) [Saiba mais](../../automating/using/list-of-functions.md#aggregates)

* Nos Relatórios dinâmicos, o segmento **Excluir prova** foi removido. (CAMP-46161)

* Uma nova mensagem de aviso foi adicionada para informar ao usuário quando um certificado iOS é carregado sem o valor platformPrincipal no aplicativo Campaign.

* O tamanho máximo de um email agora é definido como 100 MB por padrão. Esse limite permite evitar qualquer erro que possa aumentar indefinidamente o tamanho de um email, o que pode levar a uma falha do sistema. (CAMP-47445) [Saiba mais](../../sending/using/design-and-personalize.md#email-size)

* A integração do Asset Core Service com o Designer de email agora pode ser usada por usuários padrão.

* Uma nova mensagem foi adicionada para confirmar uma migração bem-sucedida de um aplicativo de push v4 para um aplicativo de push v5.

* Durante a criação de tokens JSONWeb para autenticar na API do Campaign Standard, os perfis de produto agora são **considerados**. Isso significa que as unidades organizacionais e as funções alocadas ao grupo de segurança (que corresponde ao perfil do produto no AdobeIO) serão aplicadas à conta técnica IMS necessária para chamadas de API Campaign Standard Rest. (CAMP-47479)

**Correções**

* Correção de um problema que impedia que a opção de expiração da tabela de log do processo em lote (**xtkjoblog**) fosse aplicada. Isso impedia que a tabela fosse removida corretamente.

* Correção de um problema que impedia a alteração da ordem dos filtros em uma atividade de workflow de **Segmentação** . (CAMP-48357)

* Correção de uma regressão de 20.4 que poderia resultar em falha de deliveries com um erro de valor nulo. (CAMP-48591)

* Correção de um problema que impedia o envio de um relatório por meio do menu **Compartilhar** > **Enviar relatório agora** ou **Enviar relatório na programação**. (CAMP-47798)

* Correção de uma regressão que poderia resultar em taxas de abertura incorretas para o Gmail devido à filtragem de eventos de rastreamento recebidos das contas do Gmail. (CAMP-46504)

* Correção de vários problemas que causavam discrepância de dados entre relatórios no Adobe Campaign Standard e relatórios no Adobe Analytics. (CAMP-47671, CAMP-47296)

* Correção de um problema que impedia o acesso aos logs de delivery após a falha da preparação. (CAMP-48296)

* Correção de um problema que poderia exibir uma mensagem de erro ao tentar editar, excluir ou enviar um relatório personalizado. (CAMP-47789, CAMP-47798)

* Correção de um problema que resultava em falha nas chamadas de APIs ao criar um novo recurso personalizado e ativar a opção **Do not synchronize**. (CAMP-48014)

* Correção de um problema em que os recursos personalizados com a opção **Do not synchronize** ativada podiam fazer referência a um esquema que tinha sido redesenhado ou excluído. Esse problema causava um erro ao publicar os recursos personalizados.

* Correção de um problema de recusa de SMS ao usar vários códigos curtos na mesma conta externa.

* Correção de um problema que impedia o acesso a um novo critério de alerta de delivery (&quot;o recurso que você está tentando acessar está inacessível&quot;) após a publicação do banco de dados. (CAMP-48221)

* Correção de um problema em que os logs de rastreamento estavam ausentes em algumas instâncias do Campaign com relatórios dinâmicos. Um novo [technical workflow](../../administration/using/technical-workflows.md) foi adicionado para restaurar esses logs de rastreamento. (CAMP-47885)

* Correção de um problema em que nenhum dado de delivery era exibido em Relatórios dinâmicos. Os relatórios foram definidos como 0. (CAMP-47480)

* Correção de um problema que impedia o Cliente HTTP JavaScript do servidor de se conectar ao URL externo.

* Correção de um problema que redefinia uma atividade **Incremental query** após alterar o nome interno do workflow. Isso ocorria quando um campo de data era usado como modo incremental. (CAMP-47674)

* Correção de um problema que impedia a exibição da miniatura de visualização no resumo do delivery ao criar um email multilíngue com a integração do Adobe Experience Manager. Esse problema ocorria ao usar o botão **Language copy creation** para criar as variantes de email. (CAMP-47810)

* Correção de um problema que impedia os usuários de acessar o delivery pai a partir do delivery filho de email ou SMS. (CAMP-47986)

* Correção de um problema que poderia causar consumo excessivo de CPU e memória ao enviar mensagens transacionais por meio da API REST com um evento personalizado ausente. (CAMP-47147)

* Correção de um erro com a API de mensagens transacionais que, ocasionalmente, impedia o envio de mensagens em tempo real.

* Correção de um problema em que os relatórios não eram recebidos após o uso da opção **Enviar relatório no agendamento** . (CAMP-48583, CAMP-47786)

* Correção de um problema em que os relatórios recebidos após o uso da opção **Enviar relatório agora** estavam incompletos e faltavam dados. (CAMP-48583)

* Correção de um problema com o Designer de email, em que as dimensões de uma imagem eram reduzidas ao carregar uma imagem. (CAMP-47017)

* Correção de um problema que impedia que cada template Experience Manager disponível fosse exibido ao criar um delivery. (CAMP-48132)

* Correção de um erro que impedia o link Campaign na página Summary de um delivery enviado de redirecionar os usuários para a campanha relacionada. (CAMP-48012)

* Correção de um problema no Designer de email em que a integração do Asset Core Service continuava falhando ao tentar selecionar um ativo. (CAMP-47446)

* Correção de um problema que bloqueava alguns deliveries de Journey Orchestration devido ao Campaign não suportar carimbos de data e hora com um valor exato (ou seja, terminar com 00) enviado por eventos do Journey Orchestration.
