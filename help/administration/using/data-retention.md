---
title: Retenção de dados
description: Saiba mais sobre os valores de retenção padrão para tabelas padrão
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 01cfa2a0-4ff5-4520-a515-11676de82528
TQID: 'https://experienceleague.adobe.com/MKbmxOV4o1R-x8HwnWdd1ewflrckuahOmO36Fu1lhfQ'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: 7f0a1ee5-eeb8-5478-a9cd-b1896f033118
    internal-label: Instance Settings
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 5%
---
# Retenção de dados{#data-retention}

>[!NOTE]
>
>O reporte de dados está disponível somente para os últimos dois anos. Para obter mais informações sobre os períodos de retenção de dados, entre em contato com os consultores da Adobe ou com os administradores técnicos.

As tabelas de log padrão no Campaign têm períodos de retenção predefinidos que limitam a duração do armazenamento de dados, para evitar sobrecarga no sistema.

A configuração de retenção de dados é definida pelos administradores técnicos da Adobe durante a implementação e os valores podem variar, com base nos requisitos do cliente.

Entre em contato com os consultores da Adobe ou administradores técnicos para saber mais sobre os períodos de retenção que se aplicam ao seu ambiente ou para definir períodos de retenção personalizados.

Observe que, usando a funcionalidade padrão do workflow, é possível configurar períodos de retenção para qualquer tabela personalizada.

Abaixo estão os períodos de retenção padrão para tabelas padrão. Sempre que possível, e dependendo do uso de seus dados, a Adobe sugere mudar para os períodos de retenção recomendados para melhorar o desempenho da instância do Campaign.

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
* **Entregas**: 2 anos

## Período de retenção para entregas {#deliveries}

<!-- By default, the retention period for deliveries is unlimited.-->

A partir de 1º de junho de 2025, somente os deliveries dos últimos dois anos permanecerão disponíveis no sistema. Você encontrará mais detalhes abaixo:

* Quaisquer deliveries com mais de dois anos serão removidos permanentemente e não estarão mais acessíveis.
* Essa limpeza inclui somente deliveries enviados e com falha; deliveries recorrentes, deliveries de rascunho e templates não serão afetados.
* Depois que um delivery é removido, qualquer informação de rastreamento ou envio vinculada também será excluída permanentemente.
* Os templates de delivery transacional ou de marketing não serão excluídos.
* Para deliveries recorrentes, os deliveries secundários com período de agregação definido como mês ou ano não serão excluídos.

Caso deseje acelerar processos como o fluxo de trabalho **[!UICONTROL Copy headers from delivery templates]**, o período de retenção de entrega pode ser reduzido. Para fazer isso, entre em contato com o representante da Adobe.

<!--

However, if there is a high volume of deliveries on your instance, you can update the **NmsCleanup_DeliveryPurgeDelay** option available from the **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** menu.

Each time the **[!UICONTROL Database cleanup]** workflow is run, the deliveries meeting the conditions set for this option will be deleted.

-->

<!--

When updating the **NmsCleanup_DeliveryPurgeDelay** option, it is recommended to proceed gradually with multiple iterations. For example, you can start by setting the value to 300 days, then 180 days, then 120 days, and so on - making sure iterations are at least 2 days apart. Otherwise, the **[!UICONTROL Database cleanup]** workflow may take much longer because of a large number of deliveries to delete.

This action can help speeding up processes such as the **[!UICONTROL Copy headers from delivery templates]** workflow. Learn more on technical workflows in [this section](technical-workflows.md).

The default value for the **NmsCleanup_DeliveryPurgeDelay** option is `-1`. In this case, no delivery is deleted.

For example, if you set it to `180`, any non-template deliveries that have not been updated in the last 180 days will be deleted when the **[!UICONTROL Database cleanup]** workflow is run.

-->


