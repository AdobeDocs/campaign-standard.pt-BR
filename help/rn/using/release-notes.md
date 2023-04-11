---
title: Versão mais recente
description: Esta página detalha o conteúdo da versão mais recente do Campaign Standard
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: 362f1f6605bc9667a80cddf2bd1bef4338cda31a
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 16%

---


# Versão mais recente{#latest-release}

![Painel de controle](assets/do-not-localize/cp-icon.png) **Nova versão do Painel de controle**. [Saiba mais](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html?lang=pt-BR){target="_blank"}.

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
