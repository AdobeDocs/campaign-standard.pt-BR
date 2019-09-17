---
title: 'Criação de emails por meio de integrações do Adobe Campaign '
seo-title: 'Criação de emails por meio de integrações do Adobe Campaign  '
description: 'Criação de emails por meio de integrações do Adobe Campaign '
seo-description: Descubra como criar emails por meio das integrações do Adobe Campaign no Designer de email.
page-status-flag: nunca ativado
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: concepção
content-type: referência
topic-tags: edição-email-conteúdo
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 195e8db45609b8f92f0ec60c987cf6eadfd463eb

---

# Design de e-mail de várias soluções {#multi-solution-email-design}

## Editar conteúdo no Dreamweaver {#editing-content-in-dreamweaver}

A integração do Adobe Campaign Standard com o Dreamweaver permite que você edite o conteúdo de um email na interface do Dreamweaver. Você tem acesso à poderosa interface do Dreamweaver para criar e desenvolver conteúdo responsivo de email.

* **Sincronização bidirecional**

   Sempre que uma edição é feita em um produto, ela é atualizada em tempo real no outro. Se você quiser alterar a cor do texto no Dreamweaver, assim que fizer essa edição, a cor do texto estará ativa no Campaign. Além disso, quando você seleciona o código no Dreamweaver ou Campaign, uma vez que os números de linha são os mesmos, a seleção permanece entre os dois produtos, o que é muito útil ao procurar algo específico no código.

* **Carregar imagens locais no Adobe Campaign por meio do Dreamweaver**

   Ao criar ou editar um email no Dreamweaver, basta selecionar uma imagem do desktop ou da máquina local. Embora o Dreamweaver sempre tenha permitido que você faça isso, quando o Dreamweaver e o Campaign estiverem conectados, o arquivo local será carregado imediatamente no servidor do Adobe Campaign: não é necessário carregar imagens manualmente quando o conteúdo é alterado. Além disso, garante que as imagens mais recentes estejam sempre ativas no Campaign.

* **Adicionar personalização da Campanha no Dreamweaver**

   Para o desenvolvedor de e-mails, não é mais necessário adicionar texto `[[FIRSTNAME_PLACEHOLDER]]` nem procurar a sintaxe das tabelas do modelo de dados. A barra de ferramentas Campanha no Dreamweaver se conecta diretamente ao modelo de dados da sua instância do Campaign. Isso significa que você pode obter todos os dados que desejar para personalização de algo como Nome para Endereço. Se você tiver criado blocos de conteúdo no Campaign, também poderá inseri-los diretamente no Dreamweaver.

Esse recurso é detalhado na Documentação do Dreamweaver acessível [aqui](https://helpx.adobe.com/dreamweaver/using/working-with-dreamweaver-and-campaign.html). Um [vídeo](https://helpx.adobe.com/campaign/kt/acs/using/acs-dreamweaver-integration-feature-video-use.html) de demonstração também está disponível.

## Editar conteúdo no Experience Manager {#editing-content-in-experience-manager}

O conteúdo de email pode ser editado no Experience Manager e usado para uma ou várias mensagens de email no Adobe Campaign Standard. Consulte [este documento](../../integrating/using/integrating-with-experience-manager.md).

## Comparação de opções de design de email {#email-design-options-comparison}

O Adobe Campaign oferece várias opções de criação de email. O quadro abaixo mostra as principais possibilidades, benefícios e limitações para cada uma delas.

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
   <td> <strong>Prova/visualização</strong><br /> </td> 
   <td> Suportado<br /> </td> 
   <td> Visualização na prova do AEM<br /> no Campaign<br /> </td> 
   <td> Visualização e prova no Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Lista de produtos</strong><br /> </td> 
   <td> Suportado em mensagens transacionais de email<br /> </td> 
   <td> Não suportado<br /> </td> 
   <td> Não suportado<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Benefícios</strong><br /> </td> 
   <td> 
     - Criação fácil de emails por meio da experiência<br/>de arrastar e soltar - Funcionalidades semelhantes ao editor<br/>de conteúdo herdado - Conteúdo reutilizável com fragmentos
  </td> 
   <td> 
     - Reutilizar ativos do site em emails<br/>- Aproveitar o poder do Experience Manager em conteúdo de email
    </td> 
   <td> 
    - Capacidade de um desenvolvedor codificar diretamente um email<br/>- Sincronização<br/>bidirecional - Edição offline no Dreamweaver e sincronização posterior<br/>- Carregamento de imagens no Adobe Campaign pelo Dreamweaver
  </td> 
  </tr> 
  <tr> 
   <td> <strong>Limitações</strong><br /> </td> 
   <td> 
     - Nenhum conteúdo condicional nos fragmentos<br/>- Não é possível usar fragmentos do Experience Manager
  </td> 
   <td> 
     - Personalização avançada difícil de implementar<br/>- Necessidade de enviar testes no Adobe Campaign
  </td> 
   <td> Conteúdo dinâmico não suportado<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Público</strong><br /> </td> 
   <td> Profissionais de marketing que desejam manter a flexibilidade para usar componentes HTML em combinação com recursos de arrastar e soltar<br /> </td> 
   <td> Os profissionais de marketing já usam o Experience Manager que desejam usar modelos de email padrão com pouca personalização<br /> </td> 
   <td> Desenvolvedores que desejam codificar o conteúdo do email e integrar-se diretamente ao Adobe Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Para saber mais</strong><br /> </td> 
   <td> Consulte <a href="../../designing/using/overview.md">Sobre o Designer de email</a><br /> </td> 
   <td> Consulte <a href="../../integrating/using/integrating-with-experience-manager.md">Integração com o Experience Manager</a><br /> </td> 
   <td> Consulte <a href="https://helpx.adobe.com/dreamweaver/using/working-with-dreamweaver-and-campaign.html">Dreamweaver e Campaign</a> e assista a este <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-dreamweaver-integration-feature-video-use.html">vídeo</a><br /> </td> 
  </tr> 
 </tbody> 
</table>
