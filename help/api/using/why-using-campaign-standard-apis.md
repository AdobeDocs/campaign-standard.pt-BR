---
title: Por que usar as APIs do Campaign Standard?
description: Saiba mais sobre as APIs do Campaign Standard e por que usá-las.
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 47b5cf6aee969c7a199ec934b5be6bf80bee590e

---


# Por que usar APIs do Campaign Standard {#why-using-campaign-standard-apis}

O Adobe Campaign Standard fornece APIs que permitem que os sistemas existentes se integrem com a plataforma ACS para solucionar problemas reais em tempo real.

Sites públicos como a página de inscrição ou não participação precisam se conectar a sistemas de backend para armazenar informações de perfil. Os sistemas de backend, como o Adobe Campaign, têm a flexibilidade e o poder para assimilar dados de perfil e executar operações personalizadas nele.

Estes são alguns exemplos:

* Perspectivas de registro online.
* Gerenciamento de preferência de perfil de cliente e comunicação de marketing existente.
* Disparo de comunicação transacional com base em eventos - confirmação de pedido, reserva de Itinerário, redefinição de senha, etc.
* Até mesmo comunicação por email de abandono de carrinho.

Inscreva-se em páginas de aterrissagem para fornecer uma maneira aos clientes atuais ou potenciais de registrarem seu nome e endereço de email. Depois que o Campaign Standard capturar as informações e preferências do perfil, ele poderá enviar mensagens personalizadas com base nos interesses da pessoa.

Eles são construídos com os elementos abaixo:

1. Um formulário de inscrição com ouvintes da API de campanha.

   ![texto alternativo](assets/apis_uc1.png)

1. Ações personalizadas a serem executadas com base em caixas de seleção. Um cliente que selecionar "Ofertas especiais de e-mail" receberia um e-mail personalizado diferente com um cupom de presente em comparação ao processo normal de registro.

   ![texto alternativo](assets/apis_uc2.png)

1. Um perfil pode alterar seus detalhes depois de clicar no link "Atualizar detalhes" no email. Isso traz o perfil para a página "Atualizar seu perfil e detalhes de preferência". Para executar a operação, os detalhes do perfil (Pkey) são passados para o servidor da Campanha e o perfil é recuperado e representado. Quando o perfil clica no botão "Atualizar", as informações são atualizadas no sistema (por meio de um comando PATCH).

   ![texto alternativo](assets/apis_uc3.png)

Uma coleção de solicitações está disponível para ajudá-lo a se familiarizar com as solicitações de APIs do Campaign Standard. Esta coleção no formato JSON fornece solicitações de API pré-projetadas que representam casos de uso comuns.

As etapas abaixo descrevem um caso de uso passo a passo para importar e usar a coleção para criar um perfil no banco de dados do Campaign Standard.

>[!NOTE]
>
>Nosso exemplo usa o Postman. Entretanto, sinta-se à vontade para usar seu cliente REST favorito.

1. Baixe a coleção JSON clicando [aqui](https://helpx.adobe.com/content/dam/help/en/campaign/kb/working-with-acs-api/_jcr_content/main-pars/download_section/download-1/KB_postman_collection.json.zip).

1. Abra o Postman e selecione o menu **Arquivo** / **Importar** .

1. Arraste e solte o arquivo baixado na janela. As solicitações de API pré-projetadas são exibidas, prontas para serem usadas.

   ![texto alternativo](assets/postman_collection.png)

1. Selecione **Criando uma solicitação de perfil** , em seguida, atualize a solicitação POST e a guia **Cabeçalhos** com suas próprias informações (&lt;ORGANIZAÇÃO&gt;, &lt;API_KEY&gt;, &lt;ACCESS_TOKEN&gt;). Para obter mais informações, consulte [esta seção](../../api/using/setting-up-api-access.md).

   ![texto alternativo](assets/postman_uc1.png)

1. Preencha a guia **Corpo** com as informações que deseja adicionar ao novo perfil e clique no botão **Enviar** para executar a solicitação.

   ![texto alternativo](assets/postman_uc2.png)

1. Depois que um objeto é criado, uma chave primária (PKey) é associada a ele. Ela é visível na resposta da solicitação, bem como em outros atributos.

   ![texto alternativo](assets/postman_uc3.png)

1. Abra a instância do Campaign Standard e verifique se o perfil foi criado, com todas as informações da carga.

   ![texto alternativo](assets/postman_uc4.png)
