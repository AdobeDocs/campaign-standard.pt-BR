---
title: Perguntas frequentes sobre privacidade
description: Saiba mais sobre privacidade, dados pessoais e gerenciamento de consentimento no Adobe Campaign Standard
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
ht-degree: 100%

---


# Perguntas frequentes sobre privacidade {#privacy-faq}

Estas são algumas das perguntas frequentes sobre privacidade e consentimento ao usar o Adobe Campaign.

## Termos principais {#key-terms}

**Quais são os termos principais sobre Privacidade?**

Os itens listados abaixo vinculam-se aos principais termos e conceitos relacionados à Privacidade e Consentimento no Adobe Campaign:

* [Regras sobre a gestão da privacidade](../../start/using/privacy-management.md#privacy-management-regulations)
* [Dados pessoais e Personalidades](../../start/using/privacy.md#personal-data)
* [Direito de acesso e Direito ao esquecimento](../../start/using/privacy-management.md#right-access-forgotten)
* [Consentimento, retenção e funções](../../start/using/privacy-management.md#consent-retention-roles)

## Preparo para as regras de privacidade {#privacy-regulations-readiness}

**Qual é a sugestão do Adobe Campaign para o cumprimento das mais recentes regras de privacidade?**

A Adobe não presta aconselhamento jurídico. Você deve trabalhar com seu próprio serviço jurídico para garantir que sejam tomadas todas as medidas necessárias para o GDPR, CCPA, PDPA, LGPD ou qualquer outra regulamentação aplicável.

**Preparo para solicitações de acesso e exclusão de dados**

* Identifique um processo para receber/responder às solicitações do titular dos dados, incluindo a nomeação de um ponto de contato de privacidade.

* Revise os vários dados do cliente armazenados no Adobe Campaign e determine identificadores exclusivos (provavelmente haverá mais de um).

* Determine uma política e um processo de validação/autenticação para confirmação da identidade do titular dos dados.

* Verifique se a resposta do titular dos dados é facilmente compreensível.

**Considere o consentimento**

* Liste e atualize, conforme a necessidade, todos os pontos de contato para captura de dados para GDPR (ou seja, considere o idioma, o mecanismo de consentimento e os logs de consentimento).

* Verifique se todos os emails de marketing incluem os links para cancelamento de inscrição.

* Avalie a estratégia global de marketing por email para determinar implementações específicas da localidade geográfica.

**Entenda seus dados**

* Revise todas as fontes de importação e captura de dados nas quais os dados fluem para o Adobe Campaign e registre quais campos estão sendo usados para suas iniciativas de marketing.

* Remova do banco de dados do Adobe Campaign todos os atributos de dados não utilizados.

* Use os dados disponíveis no Adobe Campaign para a finalidade à qual foram coletados e ofereça a seus recipients experiências melhores e personalizadas.

* Revise e atualize as permissões de acesso aos dados para ajudar a garantir que os usuários do Adobe Campaign possam aproveitar totalmente apenas os dados necessários para executar suas campanhas, mas não acessem dados extras.

* Verifique se cada usuário do Adobe Campaign tem os direitos de acesso apropriados para executar suas tarefas necessárias, mas não tem direitos à execução de tarefas adicionais.

## Preservar o engajamento do usuário {#preserve-user-engagement}

**Como os controladores de dados podem obter consentimento com impacto mínimo no engajamento do usuário?**

Nos casos em que é necessário o consentimento para determinadas atividades de marketing, o consentimento do consumidor terá de estar ativo (ou seja, não silenciado na caixa de aprovação ou pré-seleção), desagregado e poderá não estar sujeito à oferta dos serviços.

Pode até haver instâncias em que certos consentimentos precisem ser atualizados para que possam continuar usando os dados a partir de agora.

Em vez de considerar esses requisitos de consentimento aprimorados como um risco para o universo mercadológico, os profissionais de marketing poderiam adotá-los como um verdadeiro indicador de engajamento e lealdade da marca, assim como da satisfação e confiança do cliente.

## Gerenciar o consentimento {#manage-consent}

**Como os controladores de dados podem gerenciar o consentimento no Adobe Campaign?**

O Adobe Campaign já oferece recursos para gerenciar o consentimento em mais níveis do que a maioria dos profissionais de marketing aproveita por meio de campos de dados personalizados ou por meio de um ou mais serviços.

Os profissionais de marketing devem consultar seu serviço jurídico para obter orientação sobre como proceder e, em seguida, aproveitar os recursos já incorporados ao Adobe Campaign.

Por exemplo, estender o modelo de dados no Adobe Campaign para rastrear não apenas se as pessoas aceitaram, mas também o registro de data e hora da aceitação, e algum tipo de indicador que capture o escopo preciso do consentimento.

## Exclusão de dados {#data-deletion}

**Quais dados os controladores de dados podem excluir no Adobe Campaign em resposta a uma solicitação do cliente por um titular dos dados?**

Todos os dados associados ao titular dos dados serão excluídos, incluindo tabelas predefinidas e personalizadas.

Tecnicamente, todos os dados vinculados ao titular dos dados com `integrity="own"` serão excluídos.

Como controlador de dados, você tem a opção de personalizar este processo alterando a integridade dos links definidos nos esquemas de dados (por exemplo, caso tenha uma justificativa comercial para não excluir determinados dados).

**O que acontece com os relatórios quando os logs de delivery e de rastreamento são excluídos?**

Os relatórios do Adobe Campaign são baseados em indicadores computados em dados agregados de delivery e logs de rastreamento. Como resultado, a remoção de logs individuais não deve afetar as métricas exibidas nos relatórios.

## Reimportar dados {#re-import-data}

**No Adobe Campaign, muitas vezes o registro é carregado a partir de uma fonte de dados externa. É necessário estar atento a uma possível reimportação de dados em uma data posterior?**

Ao receber uma solicitação de exclusão, o controlador de dados precisará garantir que todos os dados necessários sobre o titular dos dados sejam excluídos de todos os sistemas.

## Nova inclusão {#opt-in-again}

**Um titular de dados, cujos dados tenham sido apagados do Adobe Campaign, pode ser reinserido?**

É possível que um titular de dados seja novamente aceito ou seja adicionado como um novo recipient depois que seus dados forem apagados do Adobe Campaign.

Você pode usar a trilha de auditoria que detalha quando a exclusão anterior foi executada e quando o novo recipient foi criado.