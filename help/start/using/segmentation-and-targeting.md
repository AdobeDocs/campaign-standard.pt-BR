---
title: Segmentação e direcionamento
description: '"Saiba mais sobre perfis, definição de metas e criação de audiências na Campanha: crie audiências, importe contatos para compartilhar audiências com as soluções da Experience Cloud e evite a fadiga de marketing."'
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
source-git-commit: 3b40a9bba79d04f1635b7522cfc99f9e7566c3c0

---


# Segmentação e direcionamento{#segmentation-and-targeting}

## Profiles {#profiles}

Use o modelo de dados flexível do Adobe Campaign para aprimorar os dados do perfil do cliente e adicionar novos atributos ou tabelas. Em seguida, use esses perfis do cliente para obter segmentação, personalização e relatórios mais precisos.

perfis Adobe Campaign representam todos os contatos armazenados no banco de dados. Cada perfil corresponde a uma entrada no banco de dados que contém as informações necessárias para que o perfil seja direcionado, qualificado e rastreado individualmente. Isso significa que um perfil pode ser: um cliente, um prospecto, um indivíduo inscrito em um boletim informativo, um recipient, um usuário ou qualquer outra denominação dependendo da organização.

O recurso perfis do cliente integra todos os dados do cliente em um único lugar:

![](assets/mkt_hist_view.png)

A Adobe Campaign propõe vários mecanismos para a aquisição de perfis: coleta de dados online via [landing page](../../channels/using/getting-started-with-landing-pages.md), mecanismos [de importação manuais ou](../../automating/using/about-data-import-and-export.md)automatizados, entrada [](../../audiences/using/creating-profiles.md) direta na interface do Adobe Campaign, criação em massa por meio de APIs [de](../../api/using/about-campaign-standard-apis.md)Campanha.

**Tópicos relacionados:**

* Saiba mais sobre os diferentes tipos de perfis na seção [Perfis](../../audiences/using/about-profiles.md) .
* Acesse o número de Perfis **** ativos em sua organização [nesta seção](../../audiences/using/active-profiles.md).
* Saiba como personalizar seus dados, lidar com tarefas de gestão de dados complexas, como cálculos, agregações, deduplicações e mesclagens, usando recursos de direcionamento de [fluxo de trabalho](../../automating/using/about-targeting-activities.md)

## Públicos {#audiences}

Para permitir que você forneça mensagens relevantes e eficazes e envolva seus clientes com eficiência, o Adobe Campaign integra funcionalidades avançadas de análise e segmentação. Graças aos workflows e ao editor de query, você pode criar audiências que serão direcionadas pelas suas diferentes campanhas, dependendo das informações que você tiver sobre elas, suas atividades, seus idiomas, suas preferências ou seus históricos de marketing. Isso permite que você filtre perfis inscritos, por exemplo, ou crie audiências de públicos alvos em um número ilimitado de critérios.

As Audiências são apresentadas [nesta página](../../audiences/using/about-audiences.md) e detalhadas na seção [Audiência](../../audiences/using/creating-audiences.md) .

**Tópicos relacionados:**

* Saiba como acessar audiências multilíngues em várias regiões enviando notificações [por push](../../channels/using/creating-a-multilingual-push-notification.md) multilíngues ou emails [multilíngues](../../channels/using/creating-a-multilingual-email.md)
* Saiba como [criar query](../../audiences/using/creating-audiences.md#creating-query-audiences) para criar audiências
* Saiba como [criar audiências](../../audiences/using/creating-audiences.md#creating-list-audiences) de lista em um fluxo de trabalho
* Saiba como [importar uma audiência de um arquivo](../../audiences/using/creating-audiences.md#creating-file-audiences) em um fluxo de trabalho
* Saiba como [compartilhar audiências](../../audiences/using/creating-audiences.md#creating-experience-cloud-audiences) com as soluções da Experience Cloud

## Regulamento Geral sobre a Proteção de Dados {#general-data-protection-regulation}

O GDPR é a nova lei de privacidade da União Europeia que concilia e moderniza os requisitos de proteção de dados. O GDPR aplica-se aos clientes do Adobe Campaign que coletam dados de residentes da UE. Além dos recursos de privacidade já disponíveis no Adobe Campaign (incluindo gerenciamento de consentimento, configurações de retenção de dados e funções de usuário), estamos aproveitando essa oportunidade em nossa função de Processador de dados para incluir recursos adicionais, para ajudar a facilitar sua preparação como Controlador de dados para determinadas solicitações do RGPD.

Consulte este [guia](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GDPR.html) para saber mais sobre as ferramentas e funcionalidades fornecidas pelo Adobe Campaign para ajudá-lo a se tornar compatível com o RGPD.

## Gerenciamento de fadiga {#fatigue-management}

As regras de fadiga permitem que os comerciantes definam regras comerciais globais entre canais que excluirão automaticamente perfis excessivamente solicitados do campanha.

Para implementar regras de fadiga, defina um número máximo de mensagens por perfil e selecione um período no qual a regra será aplicada. Durante a preparação do delivery, os perfis são excluídos do delivery, se aplicável, dependendo do número de mensagens já enviadas a eles.

**Tópicos relacionados:**

* Saiba como [projetar regras](../../sending/using/fatigue-rules.md#examples) de fadiga por meio de um conjunto de amostras
* Saiba como criar [regra de tipologia](../../sending/using/about-typology-rules.md)
* Use as regras [de](../../sending/using/filtering-rules.md) filtro para refinar a audiência de suas mensagens
