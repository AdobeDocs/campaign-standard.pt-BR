---
title: Sobre os relatórios dinâmicos
description: Com relatórios dinâmicos, arraste e solte variáveis e dimensões em seu ambiente de forma livre e analise o sucesso de suas campanhas.
page-status-flag: never-activated
uuid: a84a18bd-4e33-466e-a6ce-d7008fe12746
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: reporting
content-type: reference
topic-tags: about-reporting
discoiquuid: bbb41c38-12c1-4625-85d5-69627e2f4b39
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a1bc9d23163d12517c4501a572fc92aac6aacbc6

---


# Sobre os relatórios dinâmicos{#about-dynamic-reports}

>[!NOTE]
>
>Somente os usuários com direitos administrativos ou com unidades organizacionais definidas como **Todos** podem criar ou salvar um novo relatório. Para obter mais informações, consulte esta [seção](../../administration/using/users-management.md).

![](assets/dynamic_report_intro.png)

O Relatórios dinâmico fornece relatórios totalmente personalizáveis e em tempo real. Ele adiciona acesso aos dados do perfil, permitindo a análise demográfica por dimensões de perfil, como gênero, cidade e idade, além de dados funcionais de campanha de email, como abrir e clicar. Com a interface de arrastar e soltar, você pode explorar dados, determinar como suas campanhas de e-mail tiveram desempenho em relação aos segmentos de clientes mais importantes e medir seu impacto nos recipient.

Graças ao menu arrastar e soltar e às visualizações personalizáveis, o recurso de relatórios dinâmicos permite combinar dimensões, métricas e intervalo de tempo em qualquer combinação, com detalhamentos e comparações ilimitados.


**Tópicos relacionados:**

* [lista do relatório](../../reporting/using/defining-the-report-period.md)
* [Unidades organizacionais](../../administration/using/organizational-units.md)
* [Vídeo de relatórios](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/reporting/creating-a-dynamic-report.html) dinâmicos

## Acesso a relatórios dinâmicos {#accessing-dynamic-reports}

Os relatórios podem ser acessados:

* No home page, selecionando a **[!UICONTROL Reports]** guia na barra superior ou no **[!UICONTROL Reports]** cartão para acessar os relatórios de todos os delivery.

   ![](assets/campaign_reports_access.png)

* Em cada programa, campanha e mensagem, no botão **Relatórios** , clicando em Relatórios **** dinâmicos para apenas visualização os relatórios específicos do delivery.

   ![](assets/campaign_reports_description.png)

Determinados relatórios não podem estar disponíveis imediatamente após um delivery, dependendo do tempo necessário para coletar e processar informações.

Os relatórios dinâmicos são divididos em duas categorias:

* **Modelos**, que podem ser modificados copiando-os usando a opção **Salvar como** (**Projeto > Salvar como...**) no modelo.
* **Relatórios** personalizados (identificados em azul), que podem ser criados diretamente clicando no botão **Criar novo projeto** no home page **Relatórios** .

>[!NOTE]
>
>Os dados são filtrados dependendo de suas unidades organizacionais.

![](assets/dynamic_report_overview.png)

## Contrato de uso do relatórios dinâmico {#dynamic-reporting-usage-agreement}

O objetivo do contrato de uso do relatórios dinâmico é funcionar como um consentimento pop-up para o processamento de dados. Por padrão, o contrato só é visível e só pode ser aceito ou recusado por usuários atribuídos com direitos administrativos.

Três opções estão disponíveis:

* **[!UICONTROL Ask me later]**: Ao clicar em **Perguntar mais tarde**, a janela parará de ser exibida por 24 horas. Até que você aceite ou recuse o contrato, as dimensões do perfil não aparecerão em seus relatórios e as informações de identificação pessoal de seus clientes não serão coletadas ou enviadas.
* **[!UICONTROL Accept]**: Ao aceitar este contrato, você autoriza a Adobe Campaign a coletar as informações de identificação pessoal dos clientes e a transferi-las para o relatórios ou data center.
* **[!UICONTROL Decline]**: Ao recusar o contrato, as dimensões do perfil não aparecerão em seus relatórios e as informações de identificação pessoal de seus clientes não serão coletadas ou enviadas. Observe que, nesse caso, a externalID ainda será coletada e usada para identificar os usuários finais.

A tabela abaixo exibe o que acontece depois de aceitar este contrato, dependendo da sua região.

|  | relatórios dinâmico | Conector do Microsoft Dynamics 365 |
|---|---|---|
| Américas e APAC (Pacífico Asiático) | **Recurso disponível**. <br>Todas as informações prontas para uso (ou seja, cidade, país/região, estado, gênero e segmentos com base na idade) e perfis personalizados encaminhados para o centro de relatórios dos EUA. For more information on profile dimensions, refer to this [page](../../reporting/using/list-of-components-.md) | **Recurso disponível**. <br>Todos os campos de perfis prontos para uso e personalizados e campos de evento padrão são processados no data center dos EUA. |
| EMEA (Europa, Oriente Médio e África) | **Recurso disponível**. <br>Todas as informações prontas para uso (ou seja, cidade, país/região, estado, gênero e segmentos com base na idade) e perfis personalizados encaminhados para o centro de relatórios da EMEA. For more information on profile dimensions, refer to this [page](../../reporting/using/list-of-components-.md) | **Recurso disponível.** Campos <br>predefinidos e personalizados de perfis e campos de evento padrão processados no data center da EMEA. <br>**[!UICONTROL Control data]** que contém dados de registro de E/S da Adobe e IDs de eventos de usuários finais do cliente enviados e armazenados no data center dos EUA. |

A tabela abaixo mostra o que acontece depois de recusar este contrato, dependendo da sua região. Observe que mesmo se você recusar este contrato, o relatórios sobre delivery e a integração com o Microsoft Dynamics 365 ainda estarão disponíveis.

| Região | relatórios dinâmico | Conector do Microsoft Dynamics 365 |
|---|---|---|
| Américas e APAC (Pacífico Asiático) | **Recurso disponível**. <br> Nenhuma informação predefinida e personalizada sobre perfis enviada para o centro de relatórios dos EUA, com exceção da ExternalID. | **Recurso disponível**. <br>Nenhum campo de perfil personalizado ou predefinido enviado para o data center dos EUA, com exceção da ID externa e da ID do Recipient. <br>Todos os campos de evento padrão do Adobe Campaign processados no data center dos EUA, com exceção da ID do mirror page. <br>Para obter mais informações sobre a integração do Microsoft Dynamics 365, consulte esta [página](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md). |
| EMEA (Europa, Oriente Médio e África) | **Recurso disponível**. <br>Nenhuma informação predefinida e personalizada sobre perfis enviada para o centro de relatórios da EMEA, com exceção da ExternalID. | **Recurso disponível.** <br>Nenhum campo de perfil personalizado ou predefinido enviado para o centro de dados da EMEA, com exceção da ID externa e da ID do Recipient. <br>Todos os campos de evento padrão do Adobe Campaign processados no data center da EMEA, com exceção da ID do mirror page.  <br>**[!UICONTROL Control data]** que contém dados de registro de E/S da Adobe e IDs de eventos de usuários finais do cliente enviados e armazenados no data center dos EUA.<br>Para obter mais informações sobre a integração do Microsoft Dynamics 365, consulte esta [página](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md). |

Essa opção não é final, você sempre pode alterá-la selecionando **[!UICONTROL Enable PII data to be transferred to US region to use reporting on Profile data]** > **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Options]**.

O valor pode ser alterado a qualquer momento. O valor 1 corresponde a **[!UICONTROL Ask me later]**, 2 **[!UICONTROL Decline]** e 3 **[!UICONTROL Accept]**.

![](assets/pii_window_2.png)
