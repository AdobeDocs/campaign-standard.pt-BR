---
title: Retenção de dados
description: Saiba mais sobre os valores de retenção padrão para tabelas padrão
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 01cfa2a0-4ff5-4520-a515-11676de82528
source-git-commit: 99c092bc40c9176a25a6ec2a164ee1d3f85d5cbe
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 4%

---

# Retenção de dados{#data-retention}

>[!NOTE]
>
>O reporte de dados está disponível apenas para os últimos três anos. Para obter mais informações sobre os períodos de retenção de dados, entre em contato com os consultores da Adobe ou com os administradores técnicos.

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

## Período de retenção para entregas {#deliveries}

Por padrão, o período de retenção para deliveries é ilimitado.

No entanto, se houver um alto volume de entregas em sua instância, você poderá atualizar a opção **NmsCleanup_DeliveryPurgeDelay**, disponível no menu **[!UICONTROL Administration]** > **[!UICONTROL Application settings]**.

Toda vez que o fluxo de trabalho **[!UICONTROL Database cleanup]** é executado, os deliveries que atendem às condições definidas para esta opção são excluídos.

Esta ação pode ajudar a acelerar processos como o fluxo de trabalho **[!UICONTROL Copy headers from delivery templates]**.

>[!NOTE]
>
>Saiba mais sobre fluxos de trabalho técnicos em [esta seção](technical-workflows.md).


O valor padrão da opção **NmsCleanup_DeliveryPurgeDelay** é `-1`. Nesse caso, nenhum delivery é excluído.

Por exemplo, se você o definir como `180`, qualquer entrega que não seja de modelo e não tenha sido atualizada nos últimos 180 dias será excluída quando o fluxo de trabalho **[!UICONTROL Database cleanup]** for executado.

>[!NOTE]
>
>* Os templates de delivery transacional ou de marketing não serão excluídos.
>
>* Para deliveries recorrentes, os deliveries secundários com período de agregação definido como mês ou ano não serão excluídos.

Ao atualizar a opção **NmsCleanup_DeliveryPurgeDelay**, é recomendável prosseguir gradualmente com várias iterações. Por exemplo, você pode começar definindo o valor como 300 dias, depois 180 dias, depois 120 dias e assim por diante - certificando-se de que as iterações estejam pelo menos com 2 dias de diferença. Caso contrário, o fluxo de trabalho **[!UICONTROL Database cleanup]** pode demorar muito mais devido a um grande número de entregas a serem excluídas.

