---
title: Perguntas frequentes sobre privacidade
description: Saiba mais sobre privacidade, dados pessoais e gerenciamento de consentimento na Adobe Campaign Standard
page-status-flag: never-activated
uuid: ed9e631c-5ad1-49f1-be1e-b710bc64dc91
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: discovering-the-interface
discoiquuid: 5227ca05-3856-4e54-aec6-14444d6534e3
translation-type: tm+mt
source-git-commit: 500a9575157a0652eac2504d2360f7a1cbd6189e
workflow-type: tm+mt
source-wordcount: '813'
ht-degree: 0%

---


# Perguntas frequentes sobre privacidade {#privacy-faq}

Estas são algumas das Perguntas frequentes sobre privacidade e consentimento ao usar o Adobe Campaign.

## Termos principais {#key-terms}

**Quais são os termos chave sobre Privacidade?**

Os itens listados abaixo vinculam-se aos principais termos e conceitos relacionados à Privacidade e Consentimento no Adobe Campaign:

* [Regulamentos relativos à gestão da privacidade](../../start/using/privacy-management.md#privacy-management-regulations)
* [Dados pessoais e Personalidades](../../start/using/privacy.md#personal-data)
* [Direito de acesso e direito de ser esquecido](../../start/using/privacy-management.md#right-access-forgotten)
* [Consentimento, retenção e funções](../../start/using/privacy-management.md#consent-retention-roles)

## Prontidão das regras de privacidade {#privacy-regulations-readiness}

**Qual é a sugestão da Adobe Campaign para cumprir com as mais recentes regulamentações de privacidade?**

O Adobe não presta aconselhamento jurídico. Você deve trabalhar com seu próprio conselho legal para garantir que eles estejam tomando todas as medidas necessárias para o RGPD, CCPA, PDPA, LGPD ou qualquer outra preparação de regulamentação aplicável.

**Preparar para solicitações de acesso e exclusão de dados**

* Identifique um processo para receber/responder às solicitações da pessoa de dados, incluindo a nomeação de um ponto de contato de privacidade.

* Revise os vários dados do cliente armazenados no Adobe Campaign e determine identificadores exclusivos (provavelmente haverá mais de um).

* Determine uma política e um processo de validação/autenticação para confirmação de identidade da pessoa de dados.

* Certifique-se de que a resposta da pessoa de dados seja fácil de entender.

**Considere o Consentimento**

* Lista e atualização, conforme necessário, de todos os pontos de contato para captura de dados para RGPD (ou seja, considere a linguagem, o mecanismo de consentimento e os registros de consentimento).

* Certifique-se de que todos os emails de marketing incluam os links para cancelar a inscrição.

* Avalie a estratégia global de marketing por email para determinar implementações específicas da localidade geográfica.

**Entenda seus dados**

* Revise todas as fontes de importação e captura de dados nas quais os dados fluem para o Adobe Campaign e documento quais campos estão sendo usados para seus esforços de marketing.

* Remova todos os atributos de dados não utilizados do banco de dados Adobe Campaign.

* Use os dados disponíveis no Adobe Campaign para a intenção de capturá-los e dar a seus recipient experiências melhor personalizadas.

* Revise e atualize as permissões de acesso aos dados para ajudar a garantir que os usuários do Adobe Campaign possam aproveitar totalmente apenas os dados necessários para executar suas campanhas, mas não acessem quaisquer dados além disso.

* Certifique-se de que cada usuário da Adobe Campaign tenha os direitos de acesso apropriados para executar suas tarefas necessárias, mas não tenha outros direitos para executar tarefas adicionais.

## Preservar envolvimento do usuário {#preserve-user-engagement}

**Como os controladores de dados podem obter consentimento com impacto mínimo no envolvimento do usuário?**

Nos casos em que o consentimento será necessário para determinadas atividades de marketing, o consentimento do consumidor terá de estar ativo (ou seja, sem silêncio como caixa de aprovação ou pré-seleção), desagregado e poderá não estar sujeito à oferta dos serviços.

Pode até haver casos em que certos consentimentos precisam ser atualizados para que possam continuar usando os dados a partir de agora.

Em vez de pensar nesses requisitos de consentimento aprimorados como um risco para o universo comercializável, os profissionais de marketing poderiam abraçá-los como um verdadeiro indicador de envolvimento e lealdade da marca, assim como satisfação e confiança do cliente.

## Gerenciar consentimento {#manage-consent}

**Como os controladores de dados podem gerenciar o consentimento no Adobe Campaign?**

A Adobe Campaign já oferece recursos para gerenciar o consentimento em mais níveis do que a maioria dos comerciantes aproveita por meio de campos de dados personalizados ou por meio de um ou mais serviços.

Os profissionais de marketing devem consultar seu conselho legal para obter orientação sobre como proceder e, em seguida, aproveitar os recursos já incorporados à Adobe Campaign.

Por exemplo, estender o modelo de dados no Adobe Campaign para rastrear não apenas se as pessoas aceitaram, mas também o carimbo de data e hora da aceitação, e algum tipo de indicador que captura o escopo preciso do consentimento.

## Exclusão de dados {#data-deletion}

**Quais dados os controladores de dados podem excluir no Adobe Campaign em resposta a uma solicitação do cliente por uma pessoa de dados?**

Todos os dados associados à pessoa de dados serão excluídos, incluindo tabelas predefinidas e personalizadas.

Tecnicamente, todos os dados vinculados à pessoa de dados com `integrity="own"` serão excluídos.

Como o Controlador de dados, você tem a opção de personalizar isso alterando a integridade dos links definidos nos schemas de dados (por exemplo, caso tenha uma justificação comercial para não excluir determinados dados).

**Como os relatórios são afetados quando delivery e logs de rastreamento são excluídos?**

Os relatórios no Adobe Campaign são baseados em indicadores computados em dados agregados de delivery e logs de rastreamento. Como resultado, a remoção de registros individuais não deve afetar as métricas exibidas nos relatórios.

## Reimportar dados {#re-import-data}

**Muitas vezes no Adobe Campaign, o registro é carregado de uma fonte externa de dados. Preciso ter cuidado com a possibilidade de reimportar dados posteriormente?**

Como o Controlador de dados, você precisará garantir que, ao receber uma solicitação de exclusão, você exclua todos os dados necessários sobre a pessoa de dados de todos os seus sistemas.

## Opt in novamente {#opt-in-again}

**Uma pessoa de dados pode, cujos dados foram apagados da Adobe Campaign, aceitar novamente mais tarde?**

É possível que uma pessoa de dados faça a aceitação novamente ou seja adicionada como um novo recipient depois que seus dados forem apagados da Adobe Campaign.

Você pode usar a trilha de auditoria que detalha quando a exclusão anterior foi executada e quando o novo recipient foi criado.