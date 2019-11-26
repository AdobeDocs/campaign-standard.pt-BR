---
title: Segmentação e direcionamento
description: '"Saiba mais sobre perfis, definição de metas e criação de público-alvo no Campaign: crie públicos-alvo, importe contatos para compartilhar públicos-alvo com as soluções da Experience Cloud e evite a fadiga de marketing."'
page-status-flag: never-activated
uuid: 71f53808-0309-49f6-a4ee-3446eac9758a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: about-adobe-campaign
discoiquuid: d8c8a318-9433-4aec-b378-fd0beb50e9fb
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 13430243e8f2840ca85e557798168f6380a7b0fa

---


# Segmentação e direcionamento{#segmentation-and-targeting}

## Profiles {#profiles}

Use o modelo de dados flexível do Adobe Campaign para aprimorar os dados do perfil do cliente e adicionar novos atributos ou tabelas. Em seguida, use esses perfis do cliente para obter segmentação, personalização e relatórios mais precisos.

Os perfis do Adobe Campaign representam todos os contatos armazenados no banco de dados. Cada perfil corresponde a uma entrada no banco de dados que contém as informações necessárias para que esse perfil seja direcionado, qualificado e rastreado individualmente. Isso significa que um perfil pode ser: um cliente, um cliente potencial, um indivíduo inscrito em um boletim informativo, um destinatário, um usuário ou qualquer outra denominação dependendo da organização.

O recurso de perfis do cliente integra todos os dados do cliente em um único lugar:

![](assets/mkt_hist_view.png)

O Adobe Campaign propõe vários mecanismos para aquisição de perfil: coleta de dados online por meio de páginas [de](../../channels/using/getting-started-with-landing-pages.md)aterrissagem, mecanismos [de importação manuais ou](../../automating/using/about-data-import-and-export.md)automatizados, entrada [](../../audiences/using/creating-profiles.md) direta na interface do Adobe Campaign, criação em massa por meio de APIs [do](../../api/using/about-campaign-standard-apis.md)Campaign.

**Tópicos relacionados:**

* Saiba mais sobre os diferentes tipos de perfis na seção [Perfis](../../audiences/using/about-profiles.md) .
* Acesse o número de Perfis **** ativos em sua organização [nesta seção](../../audiences/using/active-profiles.md).
* Saiba como personalizar seus dados, lidar com tarefas complexas de gerenciamento de dados, como cálculos, agregados, deduplicações e mesclagens, usando recursos de direcionamento de [fluxo de trabalho](../../automating/using/about-targeting-activities.md)

## Audiences {#audiences}

Para permitir que você entregue mensagens relevantes e eficazes e envolva seus clientes com eficácia, o Adobe Campaign integra funcionalidades avançadas de análise e direcionamento. Graças aos fluxos de trabalho e ao editor de consultas, você pode criar públicos-alvo que serão direcionados por suas diferentes campanhas, dependendo das informações que você tiver sobre elas, suas atividades, seu idioma, suas preferências ou seu histórico de marketing. Isso permite filtrar perfis inscritos, por exemplo, ou criar públicos-alvo em um número ilimitado de critérios.

Os públicos-alvo são apresentados [nesta página](../../audiences/using/about-audiences.md) e detalhados na seção [Públicos-alvo](../../audiences/using/creating-audiences.md) .

**Tópicos relacionados:**

* Saiba como atingir públicos multilíngues em várias regiões enviando notificações [por push](../../channels/using/creating-a-multilingual-push-notification.md) multilíngues ou emails [multilíngues](../../channels/using/creating-a-multilingual-email.md)
* Saiba como [criar consultas](../../audiences/using/creating-audiences.md#creating-query-audiences) para criar públicos-alvo
* Saiba como [criar públicos](../../audiences/using/creating-audiences.md#creating-list-audiences) de lista em um fluxo de trabalho
* Saiba como [importar um público-alvo de um arquivo](../../audiences/using/creating-audiences.md#creating-file-audiences) em um fluxo de trabalho
* Saiba como [compartilhar públicos-alvo](../../audiences/using/creating-audiences.md#creating-experience-cloud-audiences) com as soluções da Experience Cloud

## General Data Protection Regulation {#general-data-protection-regulation}

O GDPR é a nova lei de privacidade da União Europeia que concilia e moderniza os requisitos de proteção de dados. O GDPR aplica-se aos clientes do Adobe Campaign que coletam dados de residentes da UE. Além dos recursos de privacidade já disponíveis no Adobe Campaign (incluindo gerenciamento de consentimento, configurações de retenção de dados e funções de usuário), estamos aproveitando essa oportunidade em nossa função de Processador de dados para incluir recursos adicionais, para ajudar a facilitar sua preparação como Controlador de dados para determinadas solicitações do RGPD.

Consulte este [guia](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GDPR.html) para saber mais sobre as ferramentas e funcionalidades fornecidas pelo Adobe Campaign para ajudá-lo a se tornar compatível com o RGPD.

## Gerenciamento de fadiga {#fatigue-management}

As regras de fadiga permitem que os comerciantes definam regras comerciais globais entre canais que excluirão automaticamente perfis solicitados em excesso das campanhas.

Para implementar regras de fadiga, defina um número máximo de mensagens por perfil e selecione um período no qual a regra será aplicada. Durante a preparação da entrega, os perfis são excluídos da entrega, se aplicável, dependendo do número de mensagens já enviadas a eles.

**Tópicos relacionados:**

* Saiba como [projetar regras](../../administration/using/fatigue-rules.md#examples) de fadiga por meio de um conjunto de amostras
* Saiba como criar regras [de tipologia](../../administration/using/about-typology-rules.md)
* Usar regras [de](../../administration/using/filtering-rules.md) filtro para refinar o público-alvo das mensagens
