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
source-git-commit: 887396a0871a8ed93642c55a49c8737f5c98bfc2
workflow-type: ht
source-wordcount: '990'
ht-degree: 100%

---


# Versão mais recente{#latest-release}

## Versão 21.2 - Junho de 2021 {#release-21-2---june-2021}

Os novos recursos, melhorias e correções incluídos na próxima versão do Campaign Standard estão listados abaixo. Os novos recursos, as melhorias e as correções incluídos nesta versão do Campaign Standard estão listados abaixo.

**Melhorias**

* Ao criar uma página de aterrissagem, agora é possível adicionar uma caixa de seleção obrigatória que os perfis precisam marcar antes de enviar o formulário. Para obter mais informações consulte a [documentação detalhada](../../channels/using/managing-landing-page-form-data.md#agreement-checkbox).

* Para a integração dos acionadores, a mensagem de erro exibida quando não há dados de reconciliação chegando na carga do acionador foi aprimorada: &quot;Dados de alias ausentes na carga&quot;.

* O desempenho para recuperar notificações por push da fila foi aprimorado.

**Outras alterações**

* O mecanismo de assinatura do URL para links de rastreamento foi desabilitado para evitar um problema que fazia com que alguns links de rastreamento válidos e assinados fossem bloqueados incorretamente após serem modificados por ferramentas de segurança de terceiros.

* Em entregas com muitas variantes, os usuários não poderão mais criar cópias de idioma se a variante padrão tiver sido excluída. Uma mensagem agora é exibida durante a criação da cópia de idioma. (CAMP-48235)

* O processo de exclusão de perfil de duas etapas (descontinuado a partir da versão 19.4 do Campaign) agora está desativado por padrão. Anteriormente, era necessário desativá-lo manualmente na interface do Campaign antes de usar o Serviço principal de privacidade. Não fazer isso levava as solicitações de exclusão a permanecerem no estado pendente sem conclusão.

* Em Relatórios dinâmicos, o segmento **Excluir prova** foi removido. (CAMP-46161)

* Uma nova mensagem de aviso foi adicionada para informar ao usuário quando um certificado iOS é carregado sem o valor platformPrincipal no aplicativo Campaign.

* O tamanho máximo de um email agora é definido como 100 MB por padrão. Esse limite permite evitar qualquer erro que possa aumentar indefinidamente o tamanho de um email, o que pode causar uma falha do sistema. (CAMP-47445) [Saiba mais](../../sending/using/design-and-personalize.md#email-size)

* A integração do Serviço principal de ativos com o Designer de email agora pode ser usada por usuários padrão.

* Uma nova mensagem foi adicionada para confirmar uma migração bem-sucedida de um aplicativo de push v4 para um aplicativo de push v5.

* Durante a criação de tokens JSONWeb para autenticar na API do Campaign Standard, os perfis de produto agora são **considerados**. Isso significa que as unidades organizacionais e as funções alocadas ao grupo de segurança (que corresponde ao perfil do produto no AdobeIO) serão aplicadas à conta técnica IMS necessária para chamadas de API Rest do Campaign Standard. (CAMP-47479)

**Correções**

* Correção de um problema que impedia que a opção de expiração da tabela de log do processo em lote (**xtkjoblog**) fosse aplicada. Isso impedia que a tabela fosse removida corretamente.

* Correção de um problema que impedia a alteração da ordem dos filtros em uma atividade de fluxo de trabalho de **Segmentação**. (CAMP-48357)

* Correção de uma regressão de 20.4 que podia resultar em falha de entregas com um erro de valor nulo. (CAMP-48591)

* Correção de um problema que impedia o envio de um relatório por meio do menu **Compartilhar** > **Enviar relatório agora** ou **Enviar relatório na programação**. (CAMP-47798)

* Correção de uma regressão introduzida no Campaign que podia gerar taxas de abertura incorretas para o Gmail devido à filtragem de eventos de rastreamento recebidos das contas do Gmail. (CAMP-46504)

* Correção de vários problemas que causavam discrepância de dados entre relatórios no Adobe Campaign Standard e relatórios no Adobe Analytics. (CAMP-47671, CAMP-47296)

* Correção de um problema que impedia o acesso aos logs do delivery após a falha da preparação. (CAMP-48296)

* Correção de um problema que podia exibir uma mensagem de erro ao ser feita uma tentativa de editar, excluir ou enviar um relatório personalizado. (CAMP-47789, CAMP-47798)

* Correção de um problema que resultava em falha nas chamadas de APIs ao criar um novo recurso personalizado e ativar a opção **Não sincronizar**. (CAMP-48014)

* Correção de um problema em que os recursos personalizados com a opção **Não sincronizar** ativada podiam fazer referência a um esquema que tinha sido reformulado ou excluído. Esse problema causava um erro durante a publicação dos recursos personalizados.

* Correção de um problema de recusa de SMS ao serem usados vários códigos curtos na mesma conta externa.

* Correção de um problema que impedia o acesso a um novo critério de alerta de entrega (&quot;o recurso que você está tentando acessar está inacessível&quot;) após a publicação do banco de dados. (CAMP-48221)

* Correção de um problema em que os logs de rastreamento estavam ausentes em algumas instâncias do Campaign com relatórios dinâmicos. Um novo [fluxo de trabalho técnico](../../administration/using/technical-workflows.md) foi adicionado para restaurar esses logs de rastreamento. (CAMP-47885)

* Correção de um problema em que nenhum dado da entrega era exibido em Relatórios dinâmicos. Os relatórios eram definidos como 0. (CAMP-47480)

* Correção de um problema que impedia o Cliente HTTP JavaScript do servidor de se conectar ao URL externo.

* Correção de um problema que redefinia uma atividade **Query incremental** após a alteração do nome interno do fluxo de trabalho. Isso ocorria quando um campo de data era usado como modo incremental. (CAMP-47674)

* Correção de um problema que impedia a pré-visualização da miniatura no resumo da entrega ao ser criado um email multilíngue com a integração do Adobe Experience Manager. Esse problema ocorria ao ser usado o botão **Criação de cópia de idioma** para criar as variantes de email. (CAMP-47810)

* Correção de um problema que impedia os usuários de acessar a entrega principal por meio da entrega secundária de email ou SMS. (CAMP-47986)

* Correção de um problema que podia causar consumo excessivo de CPU e memória ao serem enviadas mensagens transacionais por meio da API REST com um evento personalizado ausente. (CAMP-47147)

* Correção de um erro na API de mensagens transacionais que, ocasionalmente, impedia o envio de mensagens em tempo real.

* Correção de um problema em que os relatórios não eram recebidos após o uso da opção **Enviar relatório na programação**. (CAMP-48583, CAMP-47786)

* Correção de um problema em que os relatórios recebidos após o uso da opção **Enviar relatório agora** estavam incompletos e com dados faltando. (CAMP-48583)

* Correção de um problema no Designer de email, em que as dimensões de uma imagem eram reduzidas ao ser carregada uma imagem. (CAMP-47017)

* Correção de um problema que impedia que cada modelo do Experience Manager disponível fosse exibido ao ser criada uma entrega. (CAMP-48132)

* Correção de um erro que impedia que o link Campanha na página Resumo de uma entrega enviada de redirecionar os usuários para a campanha relacionada. (CAMP-48012)

* Correção de um problema no Designer de email em que a integração do Serviço principal de ativos continuava falhando ao ser feita a tentativa de selecionar um ativo. (CAMP-47446)

* Correção de um problema que bloqueava algumas entregas do Journey Orchestration porque o Campaign não aceitava carimbos de data e hora com um valor exato (ou seja, terminando em 00) enviados por eventos do Journey Orchestration.
