---
title: Versão mais recente
description: Esta página lista todas as versões recentes do Adobe Campaign Standard.
page-status-flag: never-activated
uuid: 1cf2e40c-beca-43db-8261-a1820ee86ad3
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
discoiquuid: 5c7bfb74-4002-4ffe-87e8-bddb41d34b41
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2646aa9ad60805a4dedc6b8a1f91c16f6e1b438d

---


# Versão mais recente{#latest-release}

[Planejamento](https://helpx.adobe.com/br/campaign/kb/acs-release-planning.html) da versão| Versões [do Painel](https://docs.adobe.com/content/help/pt-BR/control-panel/using/release-notes.html) de controle| Atualizações [da](../../rn/using/documentation-updates.md) documentação| Notas [de versão](../../rn/using/release-notes-2019.md) anteriores| Recursos [obsoletos](https://helpx.adobe.com/br/campaign/kb/acs-deprecated-and-removed-features.html)

[Clique aqui](http://amc-mkt-prod1-t.adobe-campaign.com/lp/LP25?service=%40rZ5cqp2DgNzrgz0alKPInakNbPSTeJYozZYnS7Wbs802u4GlISkHZX4omtK00nAU6xzZ6luEWQzr7kQ9pkCwJYumWkU) para assinar as notificações de lançamento e obter detalhes sobre as versões mais recentes da Adobe Experience Cloud diretamente na sua caixa de entrada.

## Versão 20.2 - abril de 2020 {#release-20-2---april-2020}

**Novidades**

<table> 
 <thead> 
  <tr> 
   <th> <strong>Integração do Blob do Azure</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>O conector do armazenamento Blob do Azure agora pode ser usado para importar ou exportar dados para o Adobe Campaign usando uma atividade de fluxo de trabalho de arquivo <strong></strong> Transferir. </p>
    <p>Para obter mais informações, consulte a <a href="../../administration/using/external-accounts.md#microsoft-azure-external-account">documentação detalhada</a>.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Teste de email usando perfis direcionados</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Além de testar perfis, agora você pode testar seus e-mails em perfis direcionados reais. Isso permite obter uma representação exata da mensagem que o perfil receberá: campos personalizados, informações dinâmicas e personalizadas, incluindo dados adicionais de workflows etc. </p>
    <p>Para obter mais informações, consulte a <a href="../../sending/using/testing-messages-using-target.md">documentação detalhada</a> e o <a href="https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/communication-channels/email/profile-substitution.html">vídeo tutorial</a>. </p>
   </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Novos recursos serão lançados no Painel de Controle de Campanha em abril, incluindo o gerenciamento de registros do Google TXT, monitoramento de espaço do banco de dados e alerta de email. Para obter mais informações sobre esses recursos, consulte a Nota [de versão do Painel de](https://docs.adobe.com/content/help/pt-BR/control-panel/using/release-notes.html)controle.

**Aprimoramentos**

* A experiência do usuário de mensagens transacionais foi aprimorada e a consistência da interface foi aprimorada. [Leia mais](../../channels/using/about-transactional-messaging.md)
* O Campaign Standard agora permite enviar provas para o Teste de perfis usando dados adicionais de workflows.
* As garantias para a atividade de API externa foram atualizadas. [Leia mais](../../automating/using/external-api.md)

**Aprimoramentos do Designer de email**

* Correção de um problema que afetava a fuga ao clicar várias vezes em uma imagem personalizada.
* Correção de um problema ao duplicar componentes de texto dinâmicos que resultava na duplicação da linha errada. (CAMP-41249)
* Correção de um problema com o preenchimento no Outlook ao definir o preenchimento no nível da tabela em vez do nível div.
* Correção de um problema que fazia com que a largura de uma imagem fosse modificada ao alternar para o modo HTML. (CAMP-41116)
* Corrigido um problema que impedia que o componente de mídia social ficasse acessível ao fornecer texto alternativo aos ícones. (CAMP-41345)
* Correção de um problema que fazia com que `<br>` as tags visíveis fossem exibidas ao usar a colagem de cópia no Designer de email.
* Correção de um problema que fazia com que tags HTML fossem exibidas no email após alternar de conteúdo HTML para Texto simples. (CAMP-41138)
* Correção de um problema que impedia a renderização de botões com apenas uma borda definida.
* Corrigido um problema no recuo HTML que fazia com que o rodapé dos emails se movesse para a esquerda no Microsoft Outlook. (CAMP-40987)
* Correção de um problema que fazia com que campos de personalização direcionados a um atributo de coleção definido em HTML fossem copiados no conteúdo de texto simples ao alternar para o modo de texto sem formatação. (CAMP-40365)
* Correção de um problema que impedia a inserção de links em um segmento de texto selecionado. (CAMP-41406)
* Correção de um problema que fazia com que a data fosse alterada ao selecionar um fuso horário no editor de query. (CAMP-38277)

**Outras alterações**

* A Reconciliação de **KPIs com o fluxo de trabalho predefinido do Adobe Analytics** agora é executada até a data atual, em vez de ser executada por um único dia.
* O MCPNS não suporta a adição de APNS e APNS-SANDBOX como plataformas em um aplicativo. Depois de adicionar o certificado com êxito no Adobe Campaign Standard, você não poderá mais alterar suas configurações novamente, pois apenas uma plataforma APNS (produção ou caixa de proteção) pode ser adicionada ao aplicativo MCPNS.

**Integrações da plataforma Experience**

>[!NOTE]
>
>Os recursos da plataforma Adobe Experience no Campaign Standard estão atualmente em beta, o que pode estar sujeito a atualizações frequentes sem aviso prévio. Consulte a documentação detalhada: Conector [de dados da plataforma](../../administration/using/aep-about-data-connector.md)Experience, destinos [de Audiência](../../audiences/using/aep-about-audience-destinations-service.md)

* Nos logs de fluxo de trabalho, a cada 10 minutos, a Campanha agora exibe o número de registros já processados pelo trabalho que está sendo executado no momento.
* Correção de um problema que ocorria ao importar um perfil da plataforma Adobe Experience que havia sido excluído do banco de dados.
* Correção de um problema nos logs de fluxo de trabalho, que poderia exibir um resultado incorreto para o número total de registros importados.

**Correções**

* Correção de um problema com a atividade do fluxo de trabalho do **Enriquecimento** que poderia ocorrer ao adicionar espaços no campo **Alias** , que criava um novo item de linha. (CAMP-39229)
* Correção de um problema em que cada perfil de teste podia ser direcionado ao enviar uma mensagem de prova.
* Correção de um problema que ocorria após a despublicação e exclusão de uma configuração de evento. [Leia mais](../../administration/using/configuring-transactional-messaging.md#deleting-an-event)
* Correção de um problema em que o botão **Salvar** desaparecia ao fazer alterações em workflows.
* Correção de um problema ao excluir uma solicitação de privacidade manualmente na Campanha depois de ela ter sido processada, o que impedia que os dados associados à solicitação fossem excluídos mesmo após a limpeza.
* Correção de um problema que ocorria ao visualizar ou enviar mensagens que incluíam caracteres especiais do Adobe Experience Manager.
* Correção de um problema que ocorria em workflows ao executar uma atividade com várias transições de entrada.