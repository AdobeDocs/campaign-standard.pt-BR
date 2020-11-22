---
solution: Campaign Standard
product: campaign
title: Garantia de integração do Microsoft Dynamics 365
description: Garantia do Microsoft Dynamics 365 com integração de Campaign Standard
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '585'
ht-degree: 0%

---


# Garantias de integração e limites

## Garantias de integração

Ao planejar utilizar essa integração, devem ser tidos em conta os seguintes aspectos: Consulte o seu representante técnico de Adobe, caso acredite que você excede esses guardadores.

* Você precisará licenciar o pacote de Campanha adequado para suportar o volume de chamada do mecanismo ACS gerado pela integração. Exceder o volume de chamada do motor licenciado pode causar uma degradação do desempenho da Campanha.

   Use o seguinte para ajudar a estimar o volume de chamada do mecanismo da integração:

   * Inserções de registros (ou seja, novo registro): 1 chamada de motor
   * Exclusão de registro: 1 chamada de motor
   * Registrar atualizações: 2 chamadas do mecanismo (apenas 1 chamada se o registro de destino for idêntico ao registro de origem - ou seja, se não houver alteração no registro ACS)

   Ao estimar o volume geral de chamadas do mecanismo ACS, é importante ter em conta outras fontes de chamadas do mecanismo, incluindo landing page, WebApps, JSSP, APIs, registros de aplicativos móveis etc.

   Informações do pacote de Campanha de visualização aqui: https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html

* A integração suporta um máximo de 30 milhões de contatos.

* A oferta de integração padrão inclui suporte para até cinco entidades personalizadas

* Entidades personalizadas com mais de 500 mil registros exigirão horas de consulta extras para executar uma importação inicial baseada em arquivos única (por entidade personalizada) por meio do fluxo de trabalho de Campanha (que incorre em um custo adicional)

* A oferta de integração padrão inclui suporte para entidades personalizadas de até 50 colunas.

* Você precisará criar e publicar seus recursos personalizados antes de implementar a integração.

* A profundidade máxima da tabela ao vincular tabelas é de dois (ou seja, tabela1->tabela2->tabela3)

* Há suporte limitado para tipos de dados dinâmicos 365. Se o modelo de dados contiver um tipo de dados diferente dos tipos simples de dados (por exemplo, sequências, números inteiros, decimais etc.), talvez seja necessário atualizar o modelo de dados antes de usar a integração.

* A preservação de dados existentes em entidades personalizadas Campanhas pode acarretar custos adicionais de consultoria para preparar os dados para a integração.

* Pode ser necessário estabelecer janelas de manutenção onboard entre o Adobe e o cliente, uma vez que a assimilação inicial pode causar lentidão na Campanha.

* É recomendável que você comunique instâncias conhecidas de aumento significativo ou &quot;picos&quot; no uso da integração (por exemplo, aumento acentuado em registros novos ou atualizados), pois isso pode causar lentidão na sincronização de dados.

* Como parte da integração, espera-se que você conclua as etapas de configuração de pré-integração no Microsoft Azure e no Dynamics 365. Consulte as etapas de configuração [nesta página](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)

* Espera-se que você incorpore seus modelos de dados do Dynamics 365 e Campanha à integração e os mantenha.

## Limites de integração

A integração foi projetada para resolver o caso de uso geral da movimentação comum de dados entre o Dynamics 365 e a Campanha, mas não se destina a abordar todos os casos de uso específicos a cada cliente:

* A integração não emite privacidade (por exemplo, RGPD) para exclusão. A responsabilidade de satisfazer os pedidos de privacidade dos utilizadores finais incumbe ao cliente; essas solicitações devem ser feitas tanto na Campanha (via Adobe Experience Platform Privacy Service) quanto no Dynamics 365 independentemente. A integração pode emitir exclusões regulares para ajudar na sincronização de dados, se desejado.

* Nenhum dado de entidade personalizada ou perfil será sincronizado da Campanha para o Dynamics 365, com exceção das informações de opção de não participação (se configuradas pelo cliente).

* O gerenciamento de subscrições de campanha (ou seja, assina/cancela a assinatura) não é suportado nativamente.

* Não há suporte para a composição e o acionamento de campanhas de e-mail de Campanha no Dynamics 365.

* A integração não oferecerá suporte à remodelagem de dados entre o Dynamics 365 e os modelos de dados de Campanha. Espera-se que a integração sincronize uma tabela do Dynamics 365 em uma tabela de Campanha.

* Não há interface de usuário de autoatendimento com a versão atual da integração.
