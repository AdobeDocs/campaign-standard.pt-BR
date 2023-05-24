---
title: Retenção de dados
description: Saiba mais sobre os valores de retenção padrão para tabelas padrão
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 01cfa2a0-4ff5-4520-a515-11676de82528
source-git-commit: 4d67d1d0239c7439cc1f4b8e1fd7fb2f7a99adec
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 13%

---

# Retenção de dados{#data-retention}

As tabelas de log padrão no Campaign têm períodos de retenção predefinidos que limitam a duração do armazenamento de dados, para evitar sobrecarga no sistema.

A configuração da retenção de dados é definida pelos administradores técnicos do Adobe durante a implementação e os valores podem variar, com base nos requisitos do cliente.

Entre em contato com os consultores de Adobe ou administradores técnicos para saber mais sobre os períodos de retenção que se aplicam ao seu ambiente ou para definir períodos de retenção personalizados.

Observe que, usando a funcionalidade padrão do workflow, é possível configurar períodos de retenção para qualquer tabela personalizada.

Abaixo estão os períodos de retenção padrão para tabelas padrão. Sempre que possível e dependendo do uso de seus dados, o Adobe sugere mover para os períodos de retenção recomendados para melhorar o desempenho da instância do Campaign.

* **Rastreamento consolidado**: 6 meses (recomendado: 1 mês)
* **Logs de entrega**: 6 meses (recomendado: 1 mês)
* **Logs de rastreamento**: 6 meses (recomendado: 1 mês)
* **Eventos**: 1 mês
* **Estatísticas de processamento de evento**: 6 meses (recomendado: 1 mês)
* **Eventos arquivados**: 6 meses (recomendado: 1 mês)
* **Entidades temporárias**: 7 dias
* **Eventos de pipeline ignorados**: 1 mês
* **Alertas de entrega**: 1 mês
* **Auditoria de exportação**: 6 meses (recomendado: 1 mês)
