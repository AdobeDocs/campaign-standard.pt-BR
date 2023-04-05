---
title: Notas de versão anteriores
description: Notas de versão anteriores
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: 25e842d2b012a07b3f1ef1ff5490a6b4afa0e887
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 27%

---


# Notas de versão anteriores {#e-new-release}

Esta página descreve as melhorias e correções incluídas na próxima versão do Campaign Standard.
>[!CAUTION]
>
> Esse conteúdo está sujeito a alterações sem aviso prévio até a data de atualização dos ambientes de estágio. Saiba mais na [página de planejamento de versão](../../rn/using/release-planning.md).

## Versão 23.1 - Versão de primavera/verão de 2023 {#apr-23}

### Aprimoramentos {#e-rn-improvements}

* O serviço de mensagens de push foi modernizado para otimizar a manutenção. (CAMP-47959)
* O serviço de mensagens SMS foi modernizado para proporcionar uma estabilidade aprimorada. (CAMP-52217)
* O pronto para uso **Fluxo de trabalho de criação do enriquecimento de relatórios** foi adicionada. Após importar um target mapping de uma instância para outra, basta executar o workflow para importar as entradas de enriquecimento de relatório correspondentes. (CAMP-52452)

### Correções{#e-rn-patches}

* Correção de um problema que poderia resultar em erro de tempo limite ao exibir o **Hot click** relatório. (CAMP-51582)
* Correção de um problema que poderia impedir o uso da integração com o **Places** serviço. (CAMP-51923)
* Correção de um problema que impedia que o agendador do workflow funcionasse corretamente. (CAMP-52003)
* Correção de um problema que impedia a exibição dos detalhes de detalhamento ao visualizar a versão PDF de um relatório dinâmico personalizado com um grande volume de dados. (CAMP-52178)
* Correção de um problema que poderia exibir um erro ao acessar relatórios. (CAMP-52500)
* Correção de um problema que aplicou incorretamente a variável **Limitar instâncias de MTA para esta conta** Parâmetro do conector SMS para todos os canais em vez de aplicar somente ao SMS. (CAMP-52640)
