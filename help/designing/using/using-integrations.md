---
title: Criação de emails por meio de integrações do Adobe Campaign
description: Descubra como projetar emails por meio de integrações do Adobe Campaign na Designer de email.
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Intermediate
exl-id: d5c72f69-68a2-4523-956f-f265ae79b470
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '706'
ht-degree: 5%

---

# Design de email de várias soluções {#multi-solution-email-design}

O Adobe Campaign oferece várias opções de criação de email. Você pode usar soluções como o Dreamweaver para editar o conteúdo de email e criar mensagens responsivas no Designer de email. Você também pode enviar conteúdo por email com o Adobe Experience Manager e usá-lo em seus emails no Adobe Campaign Standard.

## Edição de conteúdo no Dreamweaver {#editing-content-in-dreamweaver}

A integração do Adobe Campaign Standard com o Dreamweaver permite editar o conteúdo de um email na interface do Dreamweaver. Você tem acesso à poderosa interface do Dreamweaver para projetar e desenvolver conteúdo de email responsivo.

* **Sincronização bidirecional**

  Sempre que uma edição é feita em um produto, ela é atualizada em tempo real no outro. Se você quiser alterar a cor do texto no Dreamweaver, assim que fizer essa edição, a cor do texto estará ativa no Campaign. Além disso, ao selecionar o código no Dreamweaver ou Campaign, como os números de linha são os mesmos, a seleção permanece entre os dois produtos, o que é muito útil ao procurar algo específico no código.

* **Carregar imagens locais para o Adobe Campaign por meio do Dreamweaver**

  Ao criar ou editar um email no Dreamweaver, você pode simplesmente selecionar uma imagem do seu desktop ou computador local. Embora o Dreamweaver sempre tenha permitido que você faça isso, quando o Dreamweaver e o Campaign estiverem conectados, o arquivo local será carregado imediatamente no servidor do Adobe Campaign: não é necessário carregar imagens manualmente conforme o conteúdo é alterado. Além disso, garante que as imagens mais recentes estejam sempre ativas no Campaign.

* **Adicionar personalização do Campaign no Dreamweaver**

  Para o desenvolvedor de email, não é mais necessário adicionar texto como `[[FIRSTNAME_PLACEHOLDER]]`, nem pesquisar a sintaxe das tabelas do seu modelo de dados. A barra de ferramentas do Campaign no Dreamweaver se conecta diretamente ao modelo de dados da instância do Campaign. Isso significa que você pode obter quaisquer dados que desejar para personalização de algo como Nome para Endereço. Se você tiver criado blocos de conteúdo no Campaign, também poderá puxá-los diretamente para o Dreamweaver.

Esse recurso está detalhado na Documentação do Dreamweaver acessível [aqui](https://helpx.adobe.com/br/dreamweaver/using/working-with-dreamweaver-and-campaign.html).

![](assets/do-not-localize/how-to-video.png) [Conheça este recurso no vídeo](#video)

## Edição de conteúdo no Experience Manager {#editing-content-in-experience-manager}

O conteúdo do email pode ser editado no Experience Manager e, em seguida, usado para uma ou várias mensagens de email no Adobe Campaign Standard. Consulte [este documento](../../integrating/using/integrating-with-experience-manager.md).

## Listagens de produtos {#product-listing}

>[!CONTEXTUALHELP]
>id="ac_product_listing"
>title="Utilização de listagens de produtos"
>abstract="As listas de produtos permitem que você faça referência a uma coleção de dados e a exiba no conteúdo do email."

As listas de produtos permitem fazer referência a uma ou mais coleções de dados no conteúdo do email. Essas listas estão disponíveis para emails transacionais. Uma seção dedicada para este recurso está disponível [aqui](../../designing/using/using-product-listings.md).

## Comparação das opções de design de email {#email-design-options-comparison}

O Adobe Campaign oferece várias opções de criação de email. A tabela abaixo mostra as principais possibilidades, benefícios e limitações para cada um deles.

<table> 
 <thead> 
  <tr> 
   <th> </th> 
   <th> Designer de email<br /> </th> 
   <th> Experience Manager<br /> </th> 
   <th> Dreamweaver<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <strong>Iniciar email em branco</strong><br /> </td> 
   <td> Com suporte<br /> </td> 
   <td> Com suporte<br /> </td> 
   <td> Com suporte<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Gravar HTML</strong><br /> </td> 
   <td> Com suporte<br /> </td> 
   <td> Sem suporte<br /> </td> 
   <td> Com suporte<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Atualizar HTML</strong><br /> </td> 
   <td> Somente dentro de um componente de HTML <br /> </td> 
   <td> Sem suporte<br /> </td> 
   <td> Com suporte<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Personalização básica</strong><br /> </td> 
   <td> Com suporte<br /> </td> 
   <td> Com suporte<br /> </td> 
   <td> Com suporte<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Personalização avançada</strong><br /> </td> 
   <td> Com suporte<br /> </td> 
   <td> Sem suporte<br /> </td> 
   <td> Sem suporte<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Prova/Visualização</strong><br /> </td> 
   <td> Com suporte<br /> </td> 
   <td> Visualizar no AEM<br /> Prova no Campaign<br /> </td> 
   <td> Pré-visualização e prova no Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Listagens de produtos</strong><br /> </td> 
   <td> Suportado em mensagens transacionais de email<br /> </td> 
   <td> Sem suporte<br /> </td> 
   <td> Sem suporte<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Benefícios</strong><br /> </td> 
   <td> 
     <p>- Fácil criação de email por meio da experiência de arrastar e soltar</p>
     <p>- Funcionalidades semelhantes ao editor de conteúdo herdado</p>
     <p>- Conteúdo reutilizável com fragmentos</p>
  </td> 
   <td> 
     <p>- Reutilizar ativos do site em emails</p>
     <p>- Aproveitar o potencial do Experience Manager em conteúdo de e-mail</p>
    </td> 
   <td> 
    <p>- Recurso para um desenvolvedor codificar diretamente um email</p>
    <p>- Sincronização bidirecional</p>
    <p>- Edição offline no Dreamweaver e sincronização posterior</p>
    <p>- Upload de imagens no Adobe Campaign por meio do Dreamweaver</p>
  </td> 
  </tr> 
  <tr> 
   <td> <strong>Limitações</strong><br /> </td> 
   <td> 
     <p>- Nenhum conteúdo condicional nos fragmentos</p>
     <p>- Não é possível usar fragmentos de Experience Manager</p>
  </td> 
   <td> 
     <p>- Dificuldade para implementar a personalização avançada</p>
     <p>- É necessário enviar testes no Adobe Campaign</p>
  </td> 
   <td> Conteúdo dinâmico sem suporte<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Público-alvo</strong><br /> </td> 
   <td> Profissionais de marketing que desejam manter a flexibilidade para usar componentes de HTML em combinação com recursos de arrastar e soltar<br /> </td> 
   <td> Profissionais de marketing que já usam o Experience Manager e que desejam usar modelos de email padrão com pouca personalização<br /> </td> 
   <td> Desenvolvedores que desejam codificar conteúdo de email e integrar diretamente com o Adobe Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Para saber mais</strong><br /> </td> 
   <td> Consulte <a href="../../designing/using/designing-content-in-adobe-campaign.md">Sobre o Designer de email</a>.<br /> </td> 
   <td> Consulte <a href="../../integrating/using/integrating-with-experience-manager.md">Integração com o Experience Manager</a>.<br /> </td> 
   <td> Veja o <a href="https://helpx.adobe.com/br/dreamweaver/using/working-with-dreamweaver-and-campaign.html">Dreamweaver e Campaign</a> e assista a este <a href="#video">vídeo</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Tutorial em vídeo {#video}

Este vídeo mostra como criar e editar conteúdo para o Adobe Campaign Standard usando o Dreamweaver.

>[!VIDEO](https://video.tv.adobe.com/v/33209?quality=12&captions=por_br)

Vídeos extras explicativos do Campaign Standard estão disponíveis [aqui](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=pt-BR).
