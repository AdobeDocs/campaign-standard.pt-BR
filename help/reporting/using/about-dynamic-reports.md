---
solution: Campaign Standard
product: campaign
title: Introdução a relatórios dinâmicos
description: Com relatórios dinâmicos, arraste e solte variáveis e dimensões em seu ambiente de forma livre e analise o sucesso de suas campanhas.
audience: reporting
content-type: reference
topic-tags: about-reporting
feature: Reporting
role: Leader
level: Beginner
translation-type: tm+mt
source-git-commit: fb9a6218bb754f803affde1fdf6c6fc01570126f
workflow-type: tm+mt
source-wordcount: '794'
ht-degree: 6%

---


# Introdução a relatórios dinâmicos {#about-dynamic-reports}

Os Relatórios dinâmicos fornecem relatórios totalmente personalizáveis e em tempo real. Ele adiciona acesso aos dados do perfil, permitindo a análise demográfica por dimensões de perfil, como gênero, cidade e idade, além de dados funcionais de campanha de email, como aberturas e cliques. Com a interface de arrastar e soltar, você pode explorar dados, determinar o desempenho de suas campanhas de email em relação aos segmentos de clientes mais importantes e medir seu impacto nos recipients.

>[!NOTE]
>
>Somente os usuários com direitos administrativos ou com unidades organizacionais definidas como **Todos** podem criar ou salvar um novo relatório. Para obter mais informações, consulte esta [seção](../../administration/using/users-management.md).

## Acesso aos relatórios dinâmicos {#accessing-dynamic-reports}

Os relatórios podem ser acessados:

* Na página inicial, selecionando a guia **[!UICONTROL Reports]** na barra superior ou o cartão **[!UICONTROL Reports]** para acessar os relatórios de todos os deliveries.

   ![](assets/campaign_reports_access.png)

* Em cada programa, campanha e mensagem, no botão **Reports** clicando em **Dynamic Reports** para exibir apenas os relatórios específicos do delivery.

   ![](assets/campaign_reports_description.png)

Determinados relatórios não podem estar disponíveis imediatamente após um delivery, dependendo do tempo que leva para coletar e processar informações.

Os relatórios dinâmicos são divididos em duas categorias:

* **Modelos**, que podem ser modificados ao copiá-los usando a opção  **Salvar** (**Projeto > Salvar como...**) no modelo.
* **Relatórios personalizados**  (identificados em azul), que podem ser criados diretamente ao clicar no botão  **Criar novo** projeto na página  **** Relatórios .

>[!NOTE]
>
>Os dados são filtrados dependendo das unidades organizacionais.

![](assets/dynamic_report_overview.png)

## Contrato de uso do relatório dinâmico {#dynamic-reporting-usage-agreement}

O objetivo do contrato de uso do Dynamic Reporting é funcionar como um consentimento pop-up para o processamento de dados. Por padrão, o contrato é visível apenas e só pode ser aceito ou recusado por usuários atribuídos com direitos administrativos.

Três opções estão disponíveis:

* **[!UICONTROL Ask me later]**: Ao clicar em  **Perguntar mais tarde**, a janela deixará de ser exibida por 24 horas. Até aceitar ou recusar o contrato, as dimensões de perfil não aparecerão em seus relatórios e as informações de identificação Pessoal dos clientes não serão coletadas ou enviadas.
* **[!UICONTROL Accept]**: Ao aceitar este contrato, você autoriza a Adobe Campaign a coletar as informações de identificação Pessoal de seus clientes e a transferi-las para o data center ou relatórios.
* **[!UICONTROL Decline]**: Ao recusar o contrato, as dimensões do perfil não aparecerão em seus relatórios e as informações de identificação pessoal dos clientes não serão coletadas ou enviadas. Observe que, nesse caso, a externalID ainda será coletada e usada para identificar usuários finais.

A tabela abaixo exibe o que acontece depois de aceitar este contrato, dependendo da sua região.

|  | Relatórios dinâmicos | Conector do Microsoft Dynamics 365 |
|---|---|---|
| Américas e APAC (Pacífico Asiático) | **Recurso disponível**. <br>Informações completas (ou seja, cidade, país/região, estado, gênero e segmentos com base na idade) e perfis personalizados enviadas para o centro de relatórios dos EUA. Para obter mais informações sobre dimensões de perfil, consulte esta [página](../../reporting/using/list-of-components-.md) | **Recurso disponível**. <br>Todos os campos de perfis prontos para uso e personalizados e os campos de eventos do Adobe Campaign Standard são processados no data center dos EUA. |
| EMEA (Europa, Oriente Médio e África) | **Recurso disponível**. <br>Informações completas (ou seja, cidade, país/região, estado, gênero e segmentos com base na idade) e perfis personalizados enviadas para o centro de relatórios da EMEA. Para obter mais informações sobre dimensões de perfil, consulte esta [página](../../reporting/using/list-of-components-.md) | **Recurso disponível.** <br>Todos os campos de perfis prontos para uso e personalizados e campos de eventos do Adobe Campaign Standard processados no data center da EMEA. <br>**[!UICONTROL Control data]**que contém dados de registro de Adobe I/O e IDs de eventos de usuário final do cliente enviados e armazenados no data center dos EUA. |

A tabela abaixo exibe o que acontece depois de recusar esse contrato, dependendo da sua região. Observe que mesmo que você recuse esse contrato, os relatórios sobre entregas e integração com o Microsoft Dynamics 365 ainda estarão disponíveis.

| Região | Relatórios dinâmicos | Conector do Microsoft Dynamics 365 |
|---|---|---|
| Américas e APAC (Pacífico Asiático) | **Recurso disponível**. <br> Nenhuma informação predefinida e personalizada de perfis enviada para o centro de relatórios dos EUA, com exceção da ExternalID. | **Recurso disponível**. <br>Nenhum campo de perfil pronto para uso ou personalizado enviado para o data center dos EUA, com exceção da ID externa e da ID do destinatário. <br>Todos os campos de evento do Adobe Campaign Standard processados no data center dos EUA, com exceção da ID da mirror page. <br>Para obter mais informações sobre a integração com o Microsoft Dynamics 365, consulte esta  [página](../../integrating/using/d365-acs-get-started.md). |
| EMEA (Europa, Oriente Médio e África) | **Recurso disponível**. <br>Nenhuma informação predefinida e personalizada de perfis enviada para o centro de relatórios da EMEA, com exceção da ExternalID. | **Recurso disponível.** <br>Nenhum campo de perfil pronto para uso ou personalizado enviado para o data center da EMEA, com exceção da External ID e da ID do destinatário. <br>Todos os campos de evento do Adobe Campaign Standard processados no data center da EMEA, com exceção da ID da mirror page.  <br>**[!UICONTROL Control data]**que contém dados de registro de Adobe I/O e IDs de eventos de usuário final do cliente enviados e armazenados no data center dos EUA.<br>Para obter mais informações sobre a integração com o Microsoft Dynamics 365, consulte esta  [página](../../integrating/using/d365-acs-get-started.md). |

Essa opção não é definitiva, você sempre pode alterá-la selecionando **[!UICONTROL Enable PII data to be transferred to US region to use reporting on Profile data]** em **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Options]**.

O valor pode ser alterado a qualquer momento. O valor 1 corresponde a **[!UICONTROL Ask me later]**, 2 **[!UICONTROL Decline]** e 3 **[!UICONTROL Accept]**.

![](assets/pii_window_2.png)
