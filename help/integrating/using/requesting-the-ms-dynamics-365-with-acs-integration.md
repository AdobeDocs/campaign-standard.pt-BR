---
title: Solicitação e configuração do Microsoft Dynamics 365 com integração com Campaign Standard
description: Saiba como solicitar e configurar o Microsoft Dynamics 365 com integração com o Campaign Standard
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a1bc9d23163d12517c4501a572fc92aac6aacbc6

---


# Solicitação do Microsoft Dynamics 365 com integração com Campaign Standard

Para provisionar essa integração, é necessário seguir as etapas abaixo.

Observe que essa integração usa um provedor de terceiros, Unifi.  Em conexão com suas solicitações de assistência de suporte, a Adobe pode ser obrigada a compartilhar suas informações de instância do Adobe Campaign com o Unifi.

Siga os detalhes do fluxograma e do fluxograma abaixo para solicitar e configurar a integração.

![](assets/provisioning-wf.png)

Detalhes do fluxograma (mapeia para as etapas acima):

1. Você já deve ter o Campaign Standard e o Microsoft Dynamics 365 provisionados, com acesso de administrador ao start implementando essa integração.

1. Leia este artigo, verifique os avisos e as etapas de configuração.

1. Envie uma solicitação de conta para adobe-support@unifisoftware.com; O Unifi exigirá as seguintes informações quando você solicitar uma conta:
* Nome do usuário
* Sobrenome do usuário
* Email do usuário
* Nome da Empresa
* Região (América do Norte, EMEA ou APAC)
* Tipo de uso:  Tipo de cliente (usuários do cliente que usarão seus dados de produção nesta integração) ou Tipo de parceiro (consultores parceiros que estão testando a integração para obter um melhor entendimento para que possam ajudar seus clientes de Campanha) ou Tipo interno (usuários internos da Adobe que estão testando a integração para obter uma melhor compreensão da solução)
* status dos dados do Campaign Standard (começando com o banco de dados limpo ou trazendo os dados existentes para a integração)
* ID do locatário da Campanha (consulte Configurar a seção de integração da Campanha etapa 3 para obter sua ID do locatário)
* URL da instância de Campanha

Tempo de resposta Unifi esperado: 1 hora durante o horário comercial regular dos EUA (das 9h às 17h, horário do Pacífico, Seg - Sex, excluindo feriados).

1. Complete as etapas pós-provisionamento para o Microsoft Dynamics 365 e para o Campaign Standard.
Além disso, envie um ticket para o Atendimento ao cliente da Adobe (diretamente ou por meio de seu contato da Adobe) para que o sinalizador de recurso de logon único esteja habilitado na instância da Campanha. Os parceiros devem entrar em contato com o representante da caixa de proteção do parceiro da Adobe, em vez de entrar em contato com o Atendimento ao cliente da Adobe para ativar o sinalizador de recursos.
Se você tiver dados existentes na Campanha que planeja incorporar à integração, siga as orientações em &quot;Dados de Campanha existentes&quot; e consulte atentamente seu contato técnico da Adobe antes de continuar.

1. Complete as etapas iniciais de integração no Unifi, navegando até o Unifi, clicando em telas de onboard, preenchendo as credenciais de conta do Dynamics 365 e do Campaign Standard e notificando o Unifi quando concluído.

1. O Unifi solicitará ao cliente a configuração de não participação desejada e o mapeamento do atributo de não participação.

1. O cliente indicará a configuração de não participação selecionada e o mapeamento do atributo de não participação.
Tempo de resposta Unifi esperado: 1 dia útil (seg - sex, exceto feriados)

1. A configuração do Unifi envolve a revisão de mapeamentos OTB, filtros, trabalhos etc. e fazendo modificações, se necessário.  Consulte o Guia do usuário Unifi para obter detalhes.
Esta etapa envolve a definição da frequência de execução dos horários Unifi
* Definir a frequência de execução dos horários no ecrã de horários em Unifi; no entanto, para programações de &quot;ingresso&quot; e &quot;saída&quot;, execute-as manualmente uma vez antes de definir a frequência de programação
* Recomendam-se as seguintes frequências de programação: Entrada (15 minutos), Saída (15 minutos), Exclusões (Uma vez por dia), Recusar (uma vez por dia)

**É recomendável trabalhar com consultoria Unifi e/ou Adobe (entre em contato com a equipe de conta da Adobe) ao configurar o Unifi.**

Para habilitar a integração entre o Adobe Campaign Standard e o Microsoft Dynamics 365, os clientes devem criar uma conta de usuário com o Unifi, um provedor de terceiros, conforme descrito neste documento.   Como usuário final do sistema Unifi, para qualquer pesquisa relacionada a solicitações de dados iniciadas pelo cliente no sistema Unifi, o cliente deve entrar em contato com a Unifi.

## Configurar esta integração

Três sistemas precisam ser provisionados e configurados para essa integração: Adobe Campaign Standard, Microsoft Dynamics 365 para vendas e Unifi. Os artigos de configuração são vinculados abaixo.

>[!CAUTION]
>
>Para cada sistema, essas etapas precisam ser executadas por um administrador.
>
>As etapas nos artigos abaixo o guiarão pela criação de integrações/registros que envolvam a atribuição de permissões e/ou acesso administrativo.  É sua responsabilidade garantir que essas etapas estejam em conformidade com suas políticas de empresa antes de serem executadas e executá-las cuidadosamente.

No ADOBE CAMPAIGN, é necessário configurar o acesso à API e configurar uma nova integração para Unifi. Para fazer isso, consulte [este artigo](../../integrating/using/configure-adobe-io-for-ms-dynamic.md).

No MICROSOFT DYNAMICS 365, é necessário criar um novo registro de aplicativo e permitir que o usuário do aplicativo use a integração.  Para configurar o Microsoft Dynamics 365 para essa integração, consulte [este artigo](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md).

Na UNIFI, é necessário configurar a integração e o mapeamento ou adicionar atributos personalizados. Para configurar o Unifi para essa integração, consulte [este artigo](../../integrating/using/configure-unifi-for-microsoft-dynamics-365-integration.md).

## Solicitação de suporte

Em caso de problemas, entre em contato com o suporte ao cliente Unifi: [support@unifisoftware.atlassian.net](mailto:support@unifisoftware.atlassian.net).

Tempo de resposta Unifi esperado: 4 horas durante o horário comercial regular dos EUA (das 9h às 17h, horário do Pacífico, Seg - Sex, excluindo feriados).

>[!CAUTION]
>
>Em conexão com sua solicitação de assistência de suporte, a Adobe pode ser obrigada a compartilhar suas informações de instância do Adobe Campaign com o Unifi.