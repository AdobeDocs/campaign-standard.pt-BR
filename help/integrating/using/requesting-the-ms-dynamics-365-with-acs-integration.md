---
title: Solicitar e configurar a integração com o Microsoft Dynamics 365
description: Saiba como solicitar e configurar o Microsoft Dynamics 365 com integração com o Campaign Standard
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e90f878814e65a9a61ee4013d94fd0bf3b1f7875
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 3%

---


# Solicitar e configurar a integração com o Microsoft Dynamics 365

Para provisionar essa integração, é necessário seguir as etapas abaixo.

Siga os detalhes do fluxograma e do fluxograma abaixo para solicitar e configurar a integração.

![](assets/provisioning-wf.png)

Detalhes do fluxograma (mapeia para as etapas acima):

* **Etapa 1** - Pressupõe-se que você já tenha ou esteja em processo de adquirir uma licença para o Microsoft Dynamics 365 para Vendas e para Adobe Campaign Standard.

* **Etapa 2** - A oferta de integração padrão é gratuita para todos os clientes. no entanto, podem ser aplicados custos adicionais, dependendo de seus requisitos (consulte [Proteção de integração e limites](../../integrating/using/ms-dynamics-365-integration-guardrails.md). Será necessário assinar uma nova ordem de venda para aproveitar a integração.

* **Etapa 3** - Complete as etapas de pré-integração para o Dynamics 365 e a Campanha. Consulte [Configurar esta integração](#configure-this-integration).

* **Etapas 4 a 7** - A equipe de onboard do Adobe trabalhará com você durante o processo de onboard.

## Configurar esta integração {#configure-this-integration}

Três sistemas precisam ser provisionados e configurados para essa integração: Adobe Campaign Standard, Microsoft Dynamics 365 para Vendas e a ferramenta de integração. Os artigos de configuração são vinculados abaixo.

>[!CAUTION]
>
>Para cada sistema, essas etapas precisam ser executadas por um administrador.
>
>As etapas nos artigos abaixo o guiarão pela criação de integrações/registros que envolvam a atribuição de permissões e/ou acesso administrativo.  É sua responsabilidade garantir que essas etapas estejam em conformidade com suas políticas de empresa antes de serem executadas e executá-las cuidadosamente.

No ADOBE CAMPAIGN, é necessário configurar o acesso à API e uma nova integração para a ferramenta de integração. Para fazer isso, consulte [este artigo](../../integrating/using/configure-adobe-io-for-ms-dynamic.md).

No MICROSOFT DYNAMICS 365, é necessário criar um novo registro de aplicativo e permitir que o usuário do aplicativo use a integração.  Para configurar o Microsoft Dynamics 365 para essa integração, consulte [este artigo](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md).

Você precisará trabalhar com a equipe de onboard do Adobe para configurar os fluxos de dados de entrada, saída e recusa.


## Solicitar suporte

Os tíquetes de suporte podem ser registrados com o Adobe Custom Care, como de costume; O Atendimento ao cliente fornecerá pessoal de suporte, conforme necessário.

Para quaisquer problemas com fluxos de dados de integração, certifique-se de incluir o conjunto de relatórios como parte da descrição da edição, bem como as seguintes informações:

* Proprietário do processo: Arquitetos de engenharia

* ID do Processo ES: [Fornecido durante o processo de integração]

* Título do processo: Integração do Dynamics 365 / Adobe Campaign Standard

* Descrição do problema: [Descrição do problema]

A cobertura de suporte de integração está disponível 24 horas por dia, 5 dias por semana (disponível de segunda a sexta-feira, exceto feriados de Adobe e períodos de pausa).