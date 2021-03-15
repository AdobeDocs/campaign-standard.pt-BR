---
solution: Campaign Standard
product: campaign
title: 'Criar emails por meio de integrações do Adobe Campaign '
description: Descubra como criar emails por meio de integrações Adobe Campaign no Designer de email.
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Design de email
role: Profissional
level: Intermediário
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '726'
ht-degree: 8%

---


# Design de email de várias soluções {#multi-solution-email-design}

O Adobe Campaign oferece várias opções de criação de email. Você pode usar soluções como o Dreamweaver para editar seu conteúdo de email e criar mensagens responsivas no Designer de email. Você também pode enviar conteúdo por email com o Adobe Experience Manager e usá-lo em seus emails no Adobe Campaign Standard.

## Edição de conteúdo no Dreamweaver {#editing-content-in-dreamweaver}

A integração do Adobe Campaign Standard com o Dreamweaver permite editar o conteúdo de um email na interface do Dreamweaver. Você tem acesso à poderosa interface do Dreamweaver para projetar e desenvolver conteúdo responsivo de email.

* **Sincronização bidirecional**

   Sempre que uma edição é feita em um produto, ela é atualizada em tempo real no outro. Se quiser alterar a cor do texto no Dreamweaver, assim que fizer essa edição, a cor do texto estará ativa no Campaign. Além disso, ao selecionar o código no Dreamweaver ou no Campaign, como os números de linha são os mesmos, a seleção permanece entre os dois produtos, o que é muito útil ao procurar algo específico no código.

* **Upload de imagens locais no Adobe Campaign por meio do Dreamweaver**

   Ao criar ou editar um email no Dreamweaver, você pode simplesmente selecionar uma imagem no desktop ou computador local. Embora o Dreamweaver sempre tenha permitido que você faça isso, quando o Dreamweaver e o Campaign estiverem conectados, o arquivo local será carregado imediatamente no servidor do Adobe Campaign: não é necessário carregar imagens manualmente conforme o conteúdo é alterado. Além disso, garante que as imagens mais recentes estejam sempre ativas no Campaign.

* **Adicionar personalização do Campaign no Dreamweaver**

   Para o desenvolvedor de email, não há mais a necessidade de adicionar texto como `[[FIRSTNAME_PLACEHOLDER]]` nem de buscar a sintaxe das tabelas do modelo de dados. A barra de ferramentas do Campaign no Dreamweaver se conecta diretamente ao modelo de dados da instância do Campaign. Isso significa que você pode inserir os dados que quiser para personalização de algo como Nome para Endereço. Se você criou Blocos de conteúdo no Campaign, também pode enviá-los diretamente para o Dreamweaver.

Esse recurso é detalhado na Documentação do Dreamweaver acessível [aqui](https://helpx.adobe.com/dreamweaver/using/working-with-dreamweaver-and-campaign.html).

![](assets/do-not-localize/how-to-video.png) [Descubra este recurso no vídeo](#video)

## Edição de conteúdo em Experience Manager {#editing-content-in-experience-manager}

O conteúdo de email pode ser editado no Experience Manager e, em seguida, usado para uma ou várias mensagens de email no Adobe Campaign Standard. Consulte [este documento](../../integrating/using/integrating-with-experience-manager.md).

## Listas de produtos {#product-listing}

>[!CONTEXTUALHELP]
>id="ac_product_listing"
>title="Uso das listagens de produtos"
>abstract="As listas de produtos permitem que você faça referência a uma coleta de dados e a exiba no conteúdo do email."

As listas de produtos permitem fazer referência a uma ou mais coleções de dados no conteúdo do email. Essas listas estão disponíveis para emails transacionais. Uma seção dedicada para este recurso está disponível [aqui](../../designing/using/using-product-listings.md).

## Comparação de opções de design de email {#email-design-options-comparison}

O Adobe Campaign oferece várias opções de criação de email. A tabela abaixo mostra as principais possibilidades, benefícios e limitações de cada uma delas.

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
   <td> <strong>Iniciar email em branco</strong><br /> </td> 
   <td> Suportado<br /> </td> 
   <td> Suportado<br /> </td> 
   <td> Suportado<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Gravar HTML</strong><br /> </td> 
   <td> Suportado<br /> </td> 
   <td> Não suportado<br /> </td> 
   <td> Suportado<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Atualizar HTML</strong><br /> </td> 
   <td> Somente dentro de um componente HTML<br /> </td> 
   <td> Não suportado<br /> </td> 
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
   <td> Não suportado<br /> </td> 
   <td> Não suportado<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Prova/Visualização</strong><br /> </td> 
   <td> Suportado<br /> </td> 
   <td> Visualização no AEM<br /> Prova no Campaign<br /> </td> 
   <td> Visualização e prova no Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Listas de produtos</strong><br /> </td> 
   <td> Suportado em mensagens transacionais de email<br /> </td> 
   <td> Não suportado<br /> </td> 
   <td> Não suportado<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Benefícios</strong><br /> </td> 
   <td> 
     <p>- Fácil criação de email por meio de uma experiência de arrastar e soltar</p>
     <p>- Funcionalidades semelhantes ao editor de conteúdo herdado</p>
     <p>- Conteúdo reutilizável com fragmentos</p>
  </td> 
   <td> 
     <p>- Reutilizar ativos do site em emails</p>
     <p>- Aproveitar o poder do Experience Manager no conteúdo de email</p>
    </td> 
   <td> 
    <p>- Capacidade de um desenvolvedor codificar diretamente um email</p>
    <p>- Sincronização bidirecional</p>
    <p>- Editar offline no Dreamweaver e sincronizar mais tarde</p>
    <p>- Upload de imagens no Adobe Campaign por meio do Dreamweaver</p>
  </td> 
  </tr> 
  <tr> 
   <td> <strong>Limitações</strong><br /> </td> 
   <td> 
     <p>- Sem conteúdo condicional nos fragmentos</p>
     <p>- Não é possível usar fragmentos de Experience Manager</p>
  </td> 
   <td> 
     <p>- Personalização avançada difícil de implementar</p>
     <p>- Precisa enviar testes no Adobe Campaign</p>
  </td> 
   <td> Conteúdo dinâmico não suportado<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Audience</strong><br /> </td> 
   <td> Profissionais de marketing que desejam manter a flexibilidade para usar componentes HTML em combinação com recursos de arrastar e soltar<br /> </td> 
   <td> Os profissionais de marketing já usam o Experience Manager que desejam usar modelos de email padrão com pouca personalização<br /> </td> 
   <td> Desenvolvedores que desejam codificar o conteúdo do email e integrar-se diretamente ao Adobe Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Para saber mais</strong><br /> </td> 
   <td> Consulte <a href="../../designing/using/designing-content-in-adobe-campaign.md">Sobre o Email Designer</a>.<br /> </td> 
   <td> Consulte <a href="../../integrating/using/integrating-with-experience-manager.md">Integração com Experience Manager</a>.<br /> </td> 
   <td> Consulte <a href="https://helpx.adobe.com/dreamweaver/using/working-with-dreamweaver-and-campaign.html">Dreamweaver e Campaign</a> e assista a este <a href="#video">vídeo</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Vídeo tutorial {#video}

Este vídeo mostra como criar e editar conteúdo para o Adobe Campaign Standard usando o Dreamweaver.

>[!VIDEO](https://video.tv.adobe.com/v/23121?quality=12&captions=eng)

Os vídeos de instruções adicionais do Campaign Standard estão disponíveis [aqui](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=pt-BR).
