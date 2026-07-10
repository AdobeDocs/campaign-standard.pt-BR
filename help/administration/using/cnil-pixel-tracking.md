---
title: Orientação da CNIL sobre pixels de rastreamento de email
description: Saiba mais sobre as orientações atualizadas da CNIL sobre pixels de rastreamento de email e os controles do Adobe Campaign Standard que podem apoiar seus esforços de conformidade.
audience: administration
role: Admin
level: Experienced
hide: true
source-git-commit: 75f1f4ad8f7173f4601c9cff1ea93bf4092f274d
workflow-type: tm+mt
source-wordcount: '1081'
ht-degree: 0%

---


# Noções básicas sobre a orientação atualizada da CNIL sobre pixels de rastreamento de email {#cnil-pixel-tracking}

>[!BEGINSHADEBOX]

**Nesta página:** saiba mais sobre a recomendação da CNIL de abril de 2026 sobre pixels de rastreamento de email e descubra os controles do Adobe Campaign Standard — ativação de rastreamento, rastreamento em nível de link, modelo de dados de consentimento, mecanismos de recusa e relatórios — que podem apoiar seus esforços de conformidade.

>[!ENDSHADEBOX]

Esta publicação é apenas para fins informativos. Não é um aconselhamento jurídico e não garante a sua conformidade com a legislação aplicável. Os recursos do produto Adobe Campaign Standard descritos abaixo são componentes básicos que, configurados e operados adequadamente, podem oferecer suporte a uma implementação em conformidade. Cada cliente é responsável por determinar e cumprir suas obrigações conforme a legislação aplicável.

## Visão geral {#overview}

Em 14 de abril de 2026, a *Commission nationale de l&#39;informatique et des libertés* (CNIL), autoridade de proteção de dados da França, publicou uma [recomendação sobre o uso de pixels de rastreamento em emails](https://www.cnil.fr/sites/default/files/2026-04/recommandation-pixels_de_suivi.pdf). As orientações esclarecem quando o consentimento é necessário e destacam a importância de práticas de consentimento adequadas para o rastreamento de pixels de email. Essa política pode afetar as práticas de envio para qualquer entidade que entregue emails a assinantes com sede na França.

A CNIL forneceu um período de três meses a partir da data da recomendação para que as empresas informassem seus destinatários de email (&quot;usuários&quot;) sobre a presença dos pixels de rastreamento, sua finalidade e o direito dos usuários de recusarem. Durante esse período de transição, espera-se que os clientes notifiquem os usuários sobre o rastreamento de pixels e forneçam uma opção de não participação, se necessário. A CNIL deve iniciar as atividades de fiscalização após 14 de julho de 2026.

À medida que a CNIL e outros reguladores esclarecem as orientações sobre rastreamento de pixels e questões relacionadas, a Adobe continuará a monitorar atualizações e informar os clientes sobre os recursos técnicos dos produtos da Adobe que oferecem suporte ao marketing por email, incluindo o Adobe Campaign Standard.

Os aplicativos de execução de marketing por email do Adobe, incluindo Adobe Journey Optimizer, Journey Optimizer B2B, Adobe Campaign e Marketo Engage, fornecem controles que podem ajudar os clientes a gerenciar o rastreamento aberto no nível do delivery ou do email. Os clientes são responsáveis por determinar suas próprias obrigações de conformidade de acordo com as orientações da CNIL e outras leis aplicáveis, mas esses recursos podem apoiar os esforços de conformidade do cliente.

### O que é um pixel de rastreamento de email {#tracking-pixel}

Um pixel de rastreamento de email é uma imagem transparente 1x1 inserida na HTML de um email. Quando o cliente de email do recipient carrega essa imagem, o pixel faz o ping em um servidor que registra dados, como carimbo de data e hora, tipo de dispositivo, cliente de email e, às vezes, um endereço IP para localização aproximada. Esse log é vinculado ao registro de um recipient, permitindo que os profissionais de marketing vejam se um email está aberto.

### Suporte ao cliente {#support}

Os clientes que buscam assistência para implementar as alterações descritas acima podem interagir com o ecossistema existente do Adobe. Para perguntas técnicas sobre os recursos da Adobe mencionados, entre em contato com o Gerente de sucesso do cliente ou gerente de conta técnica.

## Funcionalidade do Adobe Campaign Standard relacionada ao rastreamento de email {#acs-functionality}

Os clientes podem usar o rastreamento nativo, o esquema e os mecanismos de personalização do Adobe Campaign Standard para lidar com determinados elementos ao configurar a arquitetura.

### Classificação de email {#email-classification}

Estenda o template do delivery com um campo personalizado indicando o tipo do email (autenticação, somente delivery, transacional, marketing com consentimento, prospecção B2B). No Campaign Standard, os modelos de entrega podem transportar campos personalizados que fluem para a lógica de relatórios e fluxo de trabalho. Essa classificação direciona qual rastreamento é apropriado para cada envio.

[Saiba como criar e usar modelos de entrega](../../channels/using/creating-an-email.md)

### Modelo de dados de consentimento {#consent-data-model}

Estenda o recurso de Perfil por meio do mecanismo de recurso personalizado do Campaign Standard (**Administration > Development > Custom Resources**) para transportar sinalizadores de consentimento por finalidade, carimbos de data e hora de consentimento e a data de abertura mais recente (somente data — sem componente de hora). Um recurso personalizado separado e vinculado ao Perfil captura o log de eventos de consentimento somente anexação, que oferece suporte à prova de consentimento individual. Como as páginas de aterrissagem do Campaign Standard podem gravar diretamente nos campos de Perfil, o estado de consentimento atual é gerenciável nativamente; o log de consentimento é gravado por meio da API REST do Adobe Campaign Standard (`/profileAndServicesExt`) depois que uma preferência é enviada.

[Saiba como criar ou estender um recurso](../../developing/using/creating-or-extending-the-resource.md)

[Saiba como interagir com recursos personalizados por meio da API](../../api/using/interacting-with-custom-resources.md)

### Emissão de pixels {#pixel-emission}

O Adobe Campaign Standard controla o rastreamento no nível de entrega por meio da opção **[!UICONTROL Activate tracking]** nas propriedades de entrega ou de modelo. Para deliveries em que o rastreamento aberto não é legal (somente autenticação, emails de solicitação novamente), essa alternância é desativada. Para entregas em que a emissão de pixels por finalidade é apropriada, uma abordagem é desativar o pixel padrão inserido automaticamente e usar blocos de conteúdo que contenham elementos condicionais de imagem rastreada 1×1 — um por finalidade — em que cada imagem recebe uma categoria de URL (`PIX_DELIV`, `PIX_PERF`, `PIX_PROFILE`, `PIX_FRAUD`) e é exibida somente quando o sinalizador de consentimento correspondente do destinatário é verdadeiro.

[Saiba como configurar parâmetros de rastreamento de email](configuring-email-channel.md#tracking-parameters)

[Saiba como gerenciar URLs rastreados no Designer de email](../../designing/using/links.md#about-tracked-urls)

[Saiba como adicionar blocos de conteúdo](../../designing/using/personalization.md#adding-a-content-block)

### Retirada {#withdrawal}

Adicione um link **Gerenciar preferências do rastreador** a cada rodapé de email, diferente do link de cancelamento de inscrição. O link aponta para uma página de aterrissagem do Campaign Standard autenticada por meio do mecanismo `recipientId` ou `urlSubscription`; o destinatário alterna seus sinalizadores de consentimento por finalidade e os envia. Na confirmação, uma pequena chamada para a API REST do Campaign Standard grava o evento de retirada no log de consentimento. A recomendação indica que esse link está isento de segurança do requisito de rastreamento.

[Saiba como configurar páginas de aterrissagem de aceitação e recusa](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#setting-up-opt-in-and-opt-out-landing-pages)

[Saiba como começar a usar landing pages](../../channels/using/getting-started-with-landing-pages.md)

### Prova de consentimento {#consent-proof}

Cada alteração de consentimento — capturar na inscrição, atualizar da página de preferências, expiração — cria uma linha no recurso personalizado de log de consentimento, carregando o código da versão do texto, carimbo de data e hora de captura, fonte de captura e escopo. Esse log pode ser consultado por meio do explorador do Campaign Standard, pode ser exposto por meio da API REST e pode ser exportado para revisão do DPO por meio de um fluxo de trabalho programado.

[Saiba como interagir com recursos personalizados por meio da API](../../api/using/interacting-with-custom-resources.md)

### Governança de solicitação novamente {#re-solicitation}

Um campo `cusLastPixelRefusalDate` personalizado no Perfil, combinado com uma regra de filtragem de tipologia que exclui perfis em que esse campo está dentro de um período escolhido, impede a solicitação novamente de destinatários que recusaram nesse período. Um fluxo de trabalho programado gerencia os prazos de expiração de consentimento dos clientes sinalizando registros obsoletos e gravando eventos de expiração no log de consentimento.

[Saiba como trabalhar com regras de tipologia](../../sending/using/about-typology-rules.md)

[Saiba como gerenciar regras de tipologia](../../sending/using/managing-typology-rules.md)

### Relatórios {#reporting}

Os Relatórios dinâmicos do Campaign Standard são criados em categorias de URL e dimensões de perfil. As categorias de URL por finalidade introduzidas acima aparecem nos Relatórios dinâmicos como novas dimensões, permitindo que os operadores dividam os dados abertos e clicados por finalidade. A distinção entre rastreamento consentido e não consentido é visível nativamente assim que as categorias de URL estiverem em vigor.

[Saiba como começar a usar os Relatórios dinâmicos](../../reporting/using/about-dynamic-reports.md)

[Saiba mais sobre indicadores de rastreamento](../../reporting/using/tracking-indicators.md)
