---
solution: Campaign Standard
product: campaign
title: Introdução a relatórios dinâmicos
description: Com relatórios dinâmicos, arraste e solte variáveis e dimensões em seu ambiente de forma livre e analise o sucesso de suas campanhas.
audience: reporting
content-type: reference
topic-tags: about-reporting
translation-type: tm+mt
source-git-commit: b471fddd49037770e33a113374afd60c2e79e69b
workflow-type: tm+mt
source-wordcount: '791'
ht-degree: 6%

---


# Introdução a relatórios dinâmicos {#about-dynamic-reports}

O Relatórios dinâmico fornece relatórios totalmente personalizáveis e em tempo real. Ele adiciona acesso aos dados do perfil, permitindo a análise demográfica por dimensões de perfil, como gênero, cidade e idade, além de dados funcionais de campanha de email, como abrir e clicar. Com a interface de arrastar e soltar, você pode explorar dados, determinar o desempenho de suas campanhas de email em relação aos segmentos de clientes mais importantes e medir seu impacto nos recipients.

>[!NOTE]
>
>Somente usuários com direitos administrativos ou com unidades organizacionais definidas como **Todos** podem criar ou salvar um novo relatório. Para obter mais informações, consulte esta [seção](../../administration/using/users-management.md).

## Acessar relatórios dinâmicos {#accessing-dynamic-reports}

Os relatórios podem ser acessados:

* No home page, selecionando a guia **[!UICONTROL Reports]** na barra superior ou no cartão **[!UICONTROL Reports]** para acessar os relatórios de todos os delivery.

   ![](assets/campaign_reports_access.png)

* Em cada programa, campanha e mensagem, no botão **Relatórios** clicando em **Relatórios dinâmicos** para visualização apenas os relatórios específicos do delivery.

   ![](assets/campaign_reports_description.png)

Determinados relatórios não podem estar disponíveis imediatamente após um delivery, dependendo do tempo necessário para coletar e processar informações.

Os relatórios dinâmicos são divididos em duas categorias:

* **Modelos**, que podem ser modificados copiando-os usando a opção  **Salvar** como (**Projeto > Salvar como...**) no modelo.
* **Relatórios**  personalizados (identificados em azul), que podem ser criados diretamente clicando no botão  **Criar novo** projeto na página  **** Relatórios.

>[!NOTE]
>
>Os dados são filtrados dependendo de suas unidades organizacionais.

![](assets/dynamic_report_overview.png)

## Contrato de uso do relatórios dinâmico {#dynamic-reporting-usage-agreement}

O objetivo do contrato de uso do relatórios dinâmico é funcionar como um consentimento pop-up para o processamento de dados. Por padrão, o contrato só é visível e só pode ser aceito ou recusado por usuários atribuídos com direitos administrativos.

Três opções estão disponíveis:

* **[!UICONTROL Ask me later]**: Ao clicar em  **Perguntar mais tarde**, a janela parará de ser exibida por 24 horas. Até que você aceite ou recuse o contrato, as dimensões do perfil não aparecerão em seus relatórios e as informações de identificação pessoal de seus clientes não serão coletadas ou enviadas.
* **[!UICONTROL Accept]**: Ao aceitar este contrato, você autoriza a Adobe Campaign a coletar as informações de identificação pessoal de seus clientes e a transferi-las para o relatórios ou data center.
* **[!UICONTROL Decline]**: Ao recusar o contrato, as dimensões do perfil não aparecerão em seus relatórios e as informações de identificação pessoal de seus clientes não serão coletadas ou enviadas. Observe que, nesse caso, a externalID ainda será coletada e usada para identificar os usuários finais.

A tabela abaixo exibe o que acontece depois de aceitar este contrato, dependendo da sua região.

|  | Relatórios dinâmico | Conector do Microsoft Dynamics 365 |
|---|---|---|
| Américas e APAC (Pacífico Asiático) | **Recurso disponível**. <br>Todas as informações prontas para uso (ou seja, cidade, país/região, estado, gênero e segmentos com base na idade) e perfis personalizados encaminhados para o centro de relatórios dos EUA. Para obter mais informações sobre dimensões de perfil, consulte esta [página](../../reporting/using/list-of-components-.md) | **Recurso disponível**. <br>Todos os campos de perfis prontos para uso e personalizados e os campos de evento Adobe Campaign Standard são processados no data center dos EUA. |
| EMEA (Europa, Oriente Médio e África) | **Recurso disponível**. <br>Todas as informações prontas para uso (ou seja, cidade, país/região, estado, gênero e segmentos com base na idade) e perfis personalizados encaminhados para o centro de relatórios da EMEA. Para obter mais informações sobre dimensões de perfil, consulte esta [página](../../reporting/using/list-of-components-.md) | **Recurso disponível.** <br>Todos os campos predefinidos e personalizados de perfis e os campos de eventos Adobe Campaign Standard processados no data center da EMEA. <br>**[!UICONTROL Control data]**que contém dados de registro da Adobe I/O e IDs de eventos do usuário final do cliente enviados e armazenados no data center dos EUA. |

A tabela abaixo mostra o que acontece depois de recusar este contrato, dependendo da sua região. Observe que mesmo se você recusar este contrato, o relatórios sobre delivery e a integração com o Microsoft Dynamics 365 ainda estarão disponíveis.

| Região | Relatórios dinâmico | Conector do Microsoft Dynamics 365 |
|---|---|---|
| Américas e APAC (Pacífico Asiático) | **Recurso disponível**. <br> Nenhuma informação predefinida e personalizada sobre perfis enviada para o centro de relatórios dos EUA, com exceção da ExternalID. | **Recurso disponível**. <br>Nenhum campo de perfil personalizado ou predefinido enviado para o data center dos EUA, com exceção da ID externa e da ID do Recipient. <br>Todos os campos do evento Adobe Campaign Standard processados no data center dos EUA, com exceção da ID do mirror page. <br>Para obter mais informações sobre a integração do Microsoft Dynamics 365, consulte esta  [página](../../integrating/using/d365-acs-get-started.md). |
| EMEA (Europa, Oriente Médio e África) | **Recurso disponível**. <br>Nenhuma informação predefinida e personalizada sobre perfis enviada para o centro de relatórios da EMEA, com exceção da ExternalID. | **Recurso disponível.** <br>Nenhum campo de perfil personalizado ou predefinido enviado para o centro de dados da EMEA, com exceção da ID externa e da ID do Recipient. <br>Todos os campos do evento Adobe Campaign Standard processados no data center EMEA, com exceção da ID do mirror page.  <br>**[!UICONTROL Control data]**que contém dados de registro da Adobe I/O e IDs de eventos do usuário final do cliente enviados e armazenados no data center dos EUA.<br>Para obter mais informações sobre a integração do Microsoft Dynamics 365, consulte esta  [página](../../integrating/using/d365-acs-get-started.md). |

Essa opção não é final, você sempre pode alterá-la selecionando **[!UICONTROL Enable PII data to be transferred to US region to use reporting on Profile data]** em **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Options]**.

O valor pode ser alterado a qualquer momento. O valor 1 corresponde a **[!UICONTROL Ask me later]**, 2 **[!UICONTROL Decline]** e 3 **[!UICONTROL Accept]**.

![](assets/pii_window_2.png)
