---
title: Por que usar APIs do Campaign Standard?
description: Saiba mais sobre as APIs do Campaign Standard e por que usá-las.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
old-role: Data Architect
role: Developer
level: Experienced
exl-id: ef045e5d-cd02-44a0-9a1e-d468483a38d9
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
    internal-label: APIs
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '498'
ht-degree: 1%
---
# Por que usar APIs do Campaign Standard {#why-using-campaign-standard-apis}

O Adobe Campaign Standard fornece APIs que permitem que os sistemas existentes se integrem à plataforma do Campaign para resolver problemas do mundo real em tempo real.

Sites públicos, como a página de inscrição ou recusa, precisam se conectar a sistemas de back-end para armazenar informações de perfil. Sistemas de back-end como o Adobe Campaign têm a flexibilidade e o poder de assimilar dados de perfil e executar operações personalizadas neles.

Veja alguns exemplos:

* Registro de clientes potenciais online.
* Perfil do cliente existente e gerenciamento de preferência de comunicação de marketing.
* Acionamento de comunicação transacional com base em eventos - confirmação de pedido, itinerário de reserva, redefinição de senha etc.
* Até mesmo abandono de carrinho por e-mail.

As páginas de aterrissagem de inscrição fornecem uma maneira de os clientes ou clientes potenciais registrarem seu nome e endereço de email. Depois que o Campaign Standard captura as informações do perfil e as preferências, ele pode enviar mensagens personalizadas com base nos interesses da pessoa.

Eles são criados com os elementos abaixo:

1. Um formulário de registro com ouvintes de API de campanha.

   ![alt texto](assets/apis_uc1.png)

1. Ações personalizadas a serem executadas com base em caixas de seleção. Um cliente que selecionasse &quot;Ofertas especiais de email&quot; receberia um email personalizado diferente com um cupom de presente em comparação ao processo normal de registro.

   ![alt texto](assets/apis_uc2.png)

1. Um perfil pode alterar seus detalhes depois de clicar no link &quot;Atualizar detalhes&quot; no email. Isso leva o perfil à página &quot;Atualizar seu perfil e detalhes de preferência&quot;. Para executar a operação, os detalhes do perfil (Pkey) são passados para o servidor do Campaign e o perfil é recuperado e representado. Quando o perfil clicar no botão &quot;Atualizar&quot;, as informações serão atualizadas no sistema (por meio de um comando do PATCH).

   ![alt texto](assets/apis_uc3.png)

Uma coleção de solicitações está disponível para ajudá-lo a se familiarizar com as solicitações de APIs do Campaign Standard. Essa coleção no formato JSON fornece solicitações de API pré-projetadas que representam casos de uso comuns.

As etapas abaixo descrevem um caso de uso passo a passo para importar e usar a coleção para criar um perfil no banco de dados do Campaign Standard.

>[!NOTE]
>
>Nosso exemplo usa Postman. No entanto, fique à vontade para usar seu cliente REST favorito.

1. Baixe a coleção JSON clicando [aqui](https://helpx.adobe.com/content/dam/help/en/campaign/kb/working-with-acs-api/_jcr_content/main-pars/download_section/download-1/KB_postman_collection.json.zip).

1. Abra o Postman e selecione o menu **Arquivo** / **Importar**.

1. Arraste e solte o arquivo baixado na janela. As solicitações de API pré-projetadas são exibidas, prontas para uso.

   ![alt texto](assets/postman_collection.png)

1. Selecione a solicitação **Criação de um perfil** e atualize a solicitação POST e a guia **Cabeçalhos** com suas próprias informações (&lt;ORGANIZATION>, &lt;API_KEY>, &lt;ACCESS_TOKEN>). Para obter mais informações, consulte [esta seção](../../api/using/setting-up-api-access.md).

   ![alt texto](assets/postman_uc1.png)

1. Preencha a guia **Corpo** com as informações que deseja adicionar ao novo perfil e clique no botão **Enviar** para executar a solicitação.

   ![alt texto](assets/postman_uc2.png)

1. Depois que um objeto é criado, uma chave primária (PKey) é associada a ele. Ela é visível na resposta da solicitação, bem como em outros atributos.

   ![alt texto](assets/postman_uc3.png)

1. Abra a instância do Campaign Standard e verifique se o perfil foi criado com todas as informações da carga.

   ![alt texto](assets/postman_uc4.png)
