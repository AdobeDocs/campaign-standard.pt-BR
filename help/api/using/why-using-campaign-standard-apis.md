---
solution: Campaign Standard
product: campaign
title: Por que usar APIs do Campaign Standard?
description: Saiba mais sobre as APIs do Campaign Standard e por que usá-las.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '495'
ht-degree: 3%

---


# Por que usar APIs do Campaign Standard {#why-using-campaign-standard-apis}

O Adobe Campaign Standard fornece APIs que permitem a integração de sistemas existentes com a plataforma Campaign para solucionar problemas reais em tempo real.

Sites públicos como a página de inscrição ou recusa precisam se conectar a sistemas de backend para armazenar informações de perfil. Sistemas de backend como o Adobe Campaign têm a flexibilidade e a capacidade de assimilar dados de perfil e executar operações personalizadas nele.

Veja alguns exemplos:

* Prospecto de registro online.
* Perfil do cliente existente e gerenciamento de preferências de comunicação de marketing.
* Acionamento da comunicação transacional com base em evento - confirmação de pedido, reserva do Itinerário, redefinição de senha etc.
* Até mesmo comunicação por email de abandono de carrinho.

As landing pages de assinatura fornecem uma maneira para os clientes ou prospetos registrarem seu nome e endereço de email. Depois que o Campaign Standard captura as informações e preferências do perfil, ele pode enviar mensagens personalizadas com base nos interesses da pessoa.

Eles são construídos com os elementos abaixo:

1. Um formulário de registro com ouvintes da API do Campaign.

   ![texto alternativo](assets/apis_uc1.png)

1. Ações personalizadas a serem executadas com base em caixas de seleção. Um cliente que seleciona &quot;Ofertas especiais de email&quot; receberia um email personalizado diferente com um cupom de oferta em comparação ao processo normal de registro.

   ![texto alternativo](assets/apis_uc2.png)

1. Um perfil pode alterar seus detalhes depois de clicar no link &quot;Atualizar detalhes&quot; no email. Isso traz o perfil para a página &quot;Atualizar seu perfil e detalhes de preferência&quot;. Para executar a operação, os detalhes do perfil (Pkey) são passados para o servidor do Campaign e o perfil é recuperado e representado. Quando o perfil clica no botão &quot;Update&quot; (Atualizar), as informações são atualizadas no sistema (por meio de um comando PATCH).

   ![texto alternativo](assets/apis_uc3.png)

Uma coleção de solicitações está disponível para ajudar você a se familiarizar com solicitações de APIs do Campaign Standard. Essa coleção no formato JSON fornece solicitações de API pré-projetadas que representam casos de uso comuns.

As etapas abaixo descrevem um caso de uso passo a passo para importar e usar a coleção para criar um perfil no banco de dados do Campaign Standard.

>[!NOTE]
>
>Nosso exemplo usa o Postman. Entretanto, sinta-se à vontade para usar seu cliente REST favorito.

1. Baixe a coleção JSON clicando [aqui](https://helpx.adobe.com/content/dam/help/en/campaign/kb/working-with-acs-api/_jcr_content/main-pars/download_section/download-1/KB_postman_collection.json.zip).

1. Abra o Postman e selecione o menu **File** / **Import**.

1. Arraste e solte o arquivo baixado na janela . As solicitações de API pré-projetadas são exibidas, prontas para serem usadas.

   ![texto alternativo](assets/postman_collection.png)

1. Selecione a solicitação **Criação de um perfil** e atualize a solicitação do POST e a guia **Cabeçalhos** com suas próprias informações (&lt;ORGANIZAÇÃO>, &lt;API_KEY>, &lt;ACCESS_TOKEN>). Para obter mais informações, consulte [esta seção](../../api/using/setting-up-api-access.md).

   ![texto alternativo](assets/postman_uc1.png)

1. Preencha a guia **Body** com as informações que deseja adicionar ao novo perfil e clique no botão **Send** para executar a solicitação.

   ![texto alternativo](assets/postman_uc2.png)

1. Depois que um objeto é criado, uma chave primária (PKey) é associada a ele. É visível na resposta da solicitação, bem como em outros atributos.

   ![texto alternativo](assets/postman_uc3.png)

1. Abra a instância do Campaign Standard e verifique se o perfil foi criado, com todas as informações da carga útil.

   ![texto alternativo](assets/postman_uc4.png)
