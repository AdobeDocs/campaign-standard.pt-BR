---
title: Sobre relatórios dinâmicos
seo-title: Sobre relatórios dinâmicos
description: Sobre relatórios dinâmicos
seo-description: Com relatórios dinâmicos, arraste e solte variáveis e dimensões em seu ambiente de forma livre e analise o sucesso de suas campanhas.
page-status-flag: nunca ativado
uuid: a 84 a 18 bd -4 e 33-466 e-a 6 ce-d 7008 fe 12746
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: relatórios
content-type: reference
topic-tags: about-reporting
discoiquuid: bbb 41 c 38-12 c 1-4625-85 d 5-69627 e 2 f 4 b 39
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 08b2363076adcc101b741ab66b85285e7a510baa

---


# About dynamic reports{#about-dynamic-reports}

>[!NOTE]
>
>Only users with administration rights or with organizational units set to **All** can create or save a new report. For more on this, refer to this [section](../../administration/using/types-of-users.md).

![](assets/dynamic_report_intro.png)

Os Relatórios dinâmicos fornecem relatórios totalmente personalizáveis e em tempo real. Ele adiciona acesso a dados de perfil, permitindo a análise demográfica por dimensões de perfil, como gênero, cidade e idade, além de dados funcionais da campanha por email, como abrir e clicar. Com a interface de arrastar e soltar, você pode explorar os dados, determinar como suas campanhas de email foram executadas em relação aos segmentos de clientes mais importantes e medir seu impacto nos destinatários.

Graças ao menu arrastar e soltar e visualizações personalizáveis, o recurso de relatórios dinâmicos permite combinar dimensões, métricas e intervalos de tempo em qualquer combinação, com detalhamentos e comparações ilimitadas.


**Tópicos relacionados:**

* [Lista de relatórios](../../reporting/using/defining-the-report-period.md)
* [Unidades organizacionais](../../administration/using/organizational-units.md)
* [Vídeo de relatórios](https://helpx.adobe.com/campaign/kt/acs/using/acs-creating-a-dynamic-report-feature-video-use.html) dinâmicos

## Accessing dynamic reports {#accessing-dynamic-reports}

Os relatórios podem ser acessados:

* From the home page by selecting **[!UICONTROL Reports]** tab in the top bar or the **[!UICONTROL Reports]** card to access reports for all deliveries.

   ![](assets/campaign_reports_access.png)

* In each program, campaign, and message, from the **Reports** button by clicking **Dynamic Reports** to only view the reports specific to the delivery.

   ![](assets/campaign_reports_description.png)

Alguns relatórios não podem estar disponíveis imediatamente após uma entrega, dependendo do tempo necessário para coletar e processar as informações.

Os relatórios dinâmicos são divididos em duas categorias:

* **Modelos**, que podem ser modificados copiando-os usando a opção **Salvar como** (**Projeto &gt; Salvar como.**) no modelo.
* **Relatórios** personalizados (identificados em azul), que podem ser criados diretamente clicando no **botão Criar novo projeto** na página inicial **dos Relatórios** .

>[!NOTE]
>
>Os dados são filtrados dependendo das unidades organizacionais.

![](assets/dynamic_report_overview.png)


## Dynamic reporting usage agreement {#dynamic-reporting-usage-agreement}

Os relatórios dinâmicos permitem filtrar seu relatório com base nos dados de perfil com as dimensões do perfil.

As dimensões do perfil só podem ser exibidas e usadas em seus relatórios após aceitarem o contrato de uso de relatório dinâmico. Por padrão, o contrato só pode ser visto e pode ser aceito ou recusado por usuários atribuídos com direitos de administração.

Este contrato permite a transferência e o armazenamento nos Estados Unidos dos seguintes dados de perfil: cidade, país/região, estado, gênero e segmentos da idade.

Ao aceitar esse contrato, todos os dados europeus e não europeus serão transferidos para os Estados Unidos.

![](assets/pii_window.png)

Três opções estão disponíveis:

* **[!UICONTROL Ask me later]**: Ao clicar em Perguntar mais tarde, a janela parará de ser exibida por 24 horas.
* **[!UICONTROL Accept]**: Ao aceitar este contrato, você autoriza o Adobe Campaign a coletar as informações de identificação pessoal dos clientes e a transferi-las para os Estados Unidos.
* **[!UICONTROL Decline]**: Ao recusar o contrato, as dimensões do perfil não aparecerão em seus relatórios e as informações de identificação pessoal dos clientes não serão coletadas ou enviadas.

This choice is not final, you can always change it by selecting **[!UICONTROL Enable PII data to be transferred to US region to use reporting on Profile data]** in **[!UICONTROL Administration]** &gt; **[!UICONTROL Application Settings]** &gt; **[!UICONTROL Options]**.

O valor pode ser alterado a qualquer momento. The value -1 corresponds to **[!UICONTROL Ask me later]**, 1 **[!UICONTROL Accept]** and 0 **[!UICONTROL Decline]**.

![](assets/pii_window_2.png)

