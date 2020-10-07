---
title: 'Criação de emails por meio de integrações Adobe Campaign '
description: Descubra como projetar emails por meio de integrações Adobe Campaign no Designer de email.
page-status-flag: never-activated
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '709'
ht-degree: 7%

---


# Design de email de várias soluções {#multi-solution-email-design}

A Adobe Campaign oferta várias opções de criação de e-mail. Você pode usar soluções como o Dreamweaver para editar seu conteúdo de email e criar mensagens responsivas no Designer de email. Você também pode enviar conteúdo por email com o Adobe Experience Manager e usá-lo em seus emails no Adobe Campaign Standard.

## Editar conteúdo no Dreamweaver {#editing-content-in-dreamweaver}

A integração do Adobe Campaign Standard com o Dreamweaver permite que você edite o conteúdo de um email na interface do Dreamweaver. Você tem acesso à poderosa interface da Dreamweaver para criar e desenvolver conteúdo responsivo de email.

* **Sincronização bidirecional**

   Sempre que uma edição é feita em um produto, ela é atualizada em tempo real no outro. Se você quiser alterar a cor do texto no Dreamweaver, assim que fizer essa edição, a cor do texto estará em Campanha. Além disso, quando você seleciona o código no Dreamweaver ou na Campanha, uma vez que os números de linha são os mesmos, a seleção permanece entre os dois produtos, o que é muito útil ao procurar algo específico no código.

* **Upload de imagens locais no Adobe Campaign por meio do Dreamweaver**

   Ao criar ou editar um email no Dreamweaver, basta selecionar uma imagem do desktop ou da máquina local. Embora a Dreamweaver sempre tenha permitido que você faça isso, quando a Dreamweaver e a Campanha estiverem conectadas, o arquivo local será carregado imediatamente no servidor Adobe Campaign: não é necessário carregar imagens manualmente quando o conteúdo é alterado. Além disso, garante que as imagens mais recentes estejam sempre ao vivo na Campanha.

* **Adicionar personalização de Campanha no Dreamweaver**

   Para o desenvolvedor de e-mails, não é mais necessário adicionar texto `[[FIRSTNAME_PLACEHOLDER]]` nem procurar a sintaxe das tabelas do modelo de dados. A barra de ferramentas de Campanha no Dreamweaver se conecta diretamente ao modelo de dados da instância de Campanha. Isso significa que você pode obter todos os dados que desejar para personalização de algo como Nome para Endereço. Se você tiver criado blocos de conteúdo dentro da Campanha, também poderá inseri-los diretamente no Dreamweaver.

Esse recurso é detalhado na Documentação do Dreamweaver acessível [aqui](https://helpx.adobe.com/dreamweaver/using/working-with-dreamweaver-and-campaign.html). Um [vídeo](https://docs.adobe.com/content/help/pt-BR/campaign-standard-learn/tutorials/designing-content/email-designer/dreamweaver-integration.translate.html) de demonstração também está disponível.

## Edição de conteúdo no Experience Manager {#editing-content-in-experience-manager}

O conteúdo de email pode ser editado no Experience Manager e usado para uma ou várias mensagens de email no Adobe Campaign Standard. Consulte [este documento](../../integrating/using/integrating-with-experience-manager.md).

## Lista de produtos {#product-listing}

>[!CONTEXTUALHELP]
>id="ac_product_listing"
>title="Uso das listagens de produtos"
>abstract="As listas de produtos permitem que você faça referência a uma coleção de dados e exiba-a no conteúdo do email."

As listas de produtos permitem que você faça referência a uma ou mais coleções de dados no conteúdo do email. Essas listas estão disponíveis para e-mails transacionais. Uma seção dedicada para este recurso está disponível [aqui](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message).

## Comparação de opções de design de email {#email-design-options-comparison}

A Adobe Campaign oferta várias opções de criação de e-mail. O quadro abaixo mostra as principais possibilidades, benefícios e limitações para cada uma delas.

<table> 
 <thead> 
  <tr> 
   <th> </th> 
   <th> Email Designer<br /> </th> 
   <th> Experience Manager<br /> </th> 
   <th> Dreamweaver<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <strong>Email em branco do start</strong><br /> </td> 
   <td> Suportado<br /> </td> 
   <td> Suportado<br /> </td> 
   <td> Suportado<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Gravar HTML</strong><br /> </td> 
   <td> Suportado<br /> </td> 
   <td> Not supported<br /> </td> 
   <td> Suportado<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Atualizar HTML</strong><br /> </td> 
   <td> Somente dentro de um componente HTML<br /> </td> 
   <td> Not supported<br /> </td> 
   <td> Suportado<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Personalização básica</strong><br /> </td> 
   <td> Suportado<br /> </td> 
   <td> Suportado<br /> </td> 
   <td> Suportado<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Personalização avançada</strong><br /> </td> 
   <td> Suportado<br /> </td> 
   <td> Not supported<br /> </td> 
   <td> Not supported<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Prova/Pré-visualização</strong><br /> </td> 
   <td> Suportado<br /> </td> 
   <td> Pré-visualização na Prova AEM<br /> na Campanha<br /> </td> 
   <td> Pré-visualização e prova na Campanha<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Lista de produtos</strong><br /> </td> 
   <td> Suportado em mensagens transacionais de e-mail<br /> </td> 
   <td> Not supported<br /> </td> 
   <td> Not supported<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Benefícios</strong><br /> </td> 
   <td> 
     <p>- Criação fácil de emails por meio da experiência de arrastar e soltar</p>
     <p>- Funcionalidades semelhantes ao editor de conteúdo herdado</p>
     <p>- Conteúdo reutilizável com fragmentos</p>
  </td> 
   <td> 
     <p>- Reutilizando ativos do site em emails</p>
     <p>- Aproveitando o poder do Experience Manager em conteúdo de e-mail</p>
    </td> 
   <td> 
    <p>- Capacidade de um desenvolvedor para codificar diretamente um email</p>
    <p>- Sincronização bidirecional</p>
    <p>- Edição offline no Dreamweaver e sincronização posterior</p>
    <p>- Carregamento de imagens para o Adobe Campaign por meio do Dreamweaver</p>
  </td> 
  </tr> 
  <tr> 
   <td> <strong>Limitações</strong><br /> </td> 
   <td> 
     <p>- Nenhum conteúdo condicional nos fragmentos</p>
     <p>- Não é possível usar fragmentos de Experience Manager</p>
  </td> 
   <td> 
     <p>- Personalização avançada difícil de implementar</p>
     <p>- Necessidade de enviar testes no Adobe Campaign</p>
  </td> 
   <td> Conteúdo dinâmico não suportado<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Audience</strong><br /> </td> 
   <td> Profissionais de marketing que desejam manter a flexibilidade para usar componentes HTML em combinação com recursos de arrastar e soltar<br /> </td> 
   <td> Os profissionais de marketing já usam o Experience Manager que desejam usar modelos de email padrão com pouca personalização<br /> </td> 
   <td> Desenvolvedores que desejam codificar o conteúdo do email e integrar-se diretamente à Adobe Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Para saber mais</strong><br /> </td> 
   <td> Consulte <a href="../../designing/using/designing-content-in-adobe-campaign.md">Sobre o Designer</a>de email.<br /> </td> 
   <td> See <a href="../../integrating/using/integrating-with-experience-manager.md">Integrating with Experience Manager</a>.<br /> </td> 
   <td> Assista ao <a href="https://helpx.adobe.com/dreamweaver/using/working-with-dreamweaver-and-campaign.html">Dreamweaver e à Campanha</a> e assista a este <a href="https://docs.adobe.com/content/help/pt-BR/campaign-standard-learn/tutorials/designing-content/email-designer/dreamweaver-integration.translate.html">vídeo</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>
