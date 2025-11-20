---
title: Notas de versão mais recentes
description: Esta página detalha o conteúdo da versão mais recente do Campaign Standard
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: c1f64589578c144a9b8eb879684f27834efaf8d8
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 100%

---


# Notas de versão mais recentes {#latest-release}

<!--
## Release notes {#e-new-release}


This section lists improvements and changes included in the next Campaign Standard release.

>[!CAUTION]
>
>This content is subject to changes without prior notice until the stage environments upgrade date. Learn more in the [Release planning page](../../rn/using/release-planning.md).

-->

## Versão 25.2 - Versão do verão de 2025 {#summer-25}

### Correções de segurança {#summer-25-security}

* Esta versão inclui correções de segurança.
* Esta versão inclui a seguinte atualização de segurança: PostgreSQL 14.18, migração do CentOS para o Rocky em instâncias do Azure.

### Outras correções {#summer-25-fixes}

* Tratamento aprimorado da exaustão de sequências para aumentar a confiabilidade do sistema. (CAMP-57281)
* Atualizações gerais para estabilização do produto. (CAMP-57339)
* Geração de relatórios dinâmica aprimorada para aumentar a robustez e reduzir as divergências de dados. (CAMP-58157)
* Correção de um problema no qual os menus suspensos não quebravam o texto automaticamente. (CAMP-57360)
* Atualização da funcionalidade de geração de relatórios para impedir que os usuários consultem dados de mais de dois anos atrás. (CAMP-59262)

## Versão 25.1.2 {#25.1.2}

### Correções de segurança {#25.1.2-security}

* Esta versão inclui correções de segurança.
* Esta versão inclui a seguinte atualização de segurança: o Apache Tomcat foi atualizado para a v10.1.36.

### Outras correções {#25.1.2-fixes}

* Correção de um problema de análise de token que podia impedir os usuários de fazer logon pelo IMS. (CAMP-57337)
* O mecanismo de geração de ID de sequência automática foi aprimorado para aumentar a confiabilidade do sistema. (CAMP-57281)

## Versão 25.1 – Versão do inverno de 2025 {#winter-25}

### Correções de segurança {#winter-25-security}

* Esta versão inclui correções de segurança.
* Esta versão inclui a seguinte atualização de segurança: o Apache Tomcat foi atualizado para a v10.1.33.

### Outras correções {#winter-25-fixes}


* Correção do URL do “Esquema de dados” na tela de resumo da assinatura (CAMP-56168, CAMP-56296)
* Correção de um problema para contornar as regras de fadiga quando a opção **Mensagem a ser enviada imediatamente** for usada (CAMP-56866, CAMP-57033)
* Correção de um problema duplicado em modelos (CAMP-56340)
* Correção de uma regressão de rastreamento quando URLs dinâmicos eram usados em modelos do Adobe Experience Manager (CAMP-51932)
* Correção de um problema de desempenho no processo de faturamento (CAMP-56796)
* Correção de um problema de codificação de HTML com o caractere `>` em páginas da web JSSP (CAMP-56497)
* Correção de um problema nos relatórios dinâmicos ao usar a opção **Exibir nas linhas selecionadas** (CAMP-55895)

