---
title: Notas de versão anteriores
description: Notas de versão anteriores
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: 485927b217fb68064897dd877c2f4a6dd208d443
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 21%

---


# Notas de versão anteriores {#e-new-release}

Esta página descreve as melhorias e correções incluídas na próxima versão do Campaign Standard.
>[!CAUTION]
>
> Esse conteúdo está sujeito a alterações sem aviso prévio até a data de atualização dos ambientes de estágio. Saiba mais na [página de planejamento de versão](../../rn/using/release-planning.md).

## Versão 23.1 - Versão de primavera/verão de 2023 {#apr-23}

### Aprimoramentos {#e-rn-improvements}

* O serviço de mensagens de push foi modernizado para melhorar o suporte. (CAMP-47959)
* O serviço de mensagens SMS foi aprimorado para oferecer uma melhor estabilidade. (CAMP-52217)
* O Adobe fez muitas correções de acessibilidade para melhorar a facilidade geral de uso do aplicativo. Estes são alguns exemplos de melhorias de acessibilidade:
   * A acessibilidade do teclado da interface foi otimizada em várias telas.
   * O aplicativo foi aprimorado para usuários de tela sensível ao toque.
   * A cor de vários itens na interface foi alterada para melhorar a visibilidade.

### Outras alterações {#e-rn-changes}

* O pronto para uso **Fluxo de trabalho de criação do enriquecimento de relatórios** foi adicionada. Após importar um target mapping de uma instância para outra, basta executar o workflow para importar as entradas de enriquecimento de relatório correspondentes. (CAMP-52452)

### Problemas corrigidos{#e-rn-patches}

* Correção de um problema que poderia resultar em erro de tempo limite ao exibir o **Hot click** relatório. (CAMP-51582)
* Correção de um problema que poderia impedir o uso da integração com o **Places** serviço. (CAMP-51923)
* Correção de um problema que impedia que o agendador do workflow funcionasse corretamente. (CAMP-52003)
* Correção de um problema que impedia a exibição dos detalhes de detalhamento ao visualizar a versão PDF de um relatório dinâmico personalizado com um grande volume de dados. (CAMP-52178)
* Correção de um problema que poderia exibir um erro ao acessar relatórios. (CAMP-52500)
* Correção de um problema que aplicou incorretamente a variável **Limitar instâncias de MTA para esta conta** Parâmetro do conector SMS para todos os canais em vez de aplicar somente ao SMS. (CAMP-52640)
