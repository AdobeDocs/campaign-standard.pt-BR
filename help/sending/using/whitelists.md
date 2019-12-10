---
title: Listas de permissões no Adobe Campaign Standard
description: Saiba como otimizar listas de permissões com o Adobe Campaign Standard.
page-status-flag: never-activated
uuid: 286fceee-65a9-4cb9-b205-9ce5d024675c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sheduling-messages
discoiquuid: 9c7fd670-bba9-4f3c-8cb1-87397a1acd27
context-tags: delivery,schedule,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 44049443f8028ed26089ee0d49944ebac6a62111

---


# Lista de permissões{#whitelists}

Os principais provedores de serviços de Internet (ISPs) e provedores de email da Web gerenciam as listas de permissões dos remetentes de mensagens de email reconhecidos. O Adobe Campaign ajuda você no processo de obter certificação das melhores listas de permissões.

Uma lista de permissões de email é uma lista de endereços de email ou nomes de domínio a partir dos quais um programa de bloqueio de email permitirá o recebimento de mensagens.

Há dois tipos de listas brancas:
* Listas brancas não comerciais
* Listas brancas comerciais

## Listas brancas não comerciais {#non-commercial-whitelists}

Para ser aceito por essas listas brancas, o remetente deve passar por uma série de testes baseados em uma verificação técnica (seu servidor de email não deve ser um relé aberto, mas deve ter um IP estático) da infraestrutura ou de sua atividade (frequência de entrega, volume, número de reclamações).

Se o remetente não seguir uma dessas regras, ele poderá ser excluído da lista de permissões. Em seu pacote de Disponibilidade **de Email do** Adobe Campaign, o Adobe Campaign oferece um serviço de consultoria especializada para o processo de certificação para listas brancas não comerciais.

## Listas brancas comerciais {#commercial-whitelists}

As listas de permissões comerciais são baseadas em um sistema que permite ao remetente ignorar completamente os filtros antisspam ou receber pontos incrementais à medida que ele entra no sistema. Essas listas brancas pagantes (CPT ou anualmente) são oferecidas por sistemas como a Pontuação do remetente do caminho de devolução.

Os ISPs podem usar livremente esses serviços e o número de ISPs pode variar dependendo da lista de permissões. Um remetente pode, por conseguinte, estar mais confiante ao enviar as suas mensagens através de uma garantia de entrega. Algumas listas brancas também oferecem a abertura de imagens e ativação de links.

Aparecer em uma lista de permissões é um ativo inegável para qualquer campanha por email. Em seu pacote de Disponibilidade **de Email do** Adobe Campaign, o Adobe Campaign oferece um serviço de certificação de lista de permissões comercial, como CSA e Pontuação de Remetente de Caminho de Devolução.