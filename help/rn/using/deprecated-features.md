---
solution: Campaign Standard
product: campaign
title: Recursos removidos e obsoletos do Campaign Standard
description: Esta página lista recursos obsoletos e removidos do Adobe Campaign Standard.
audience: rn
content-type: reference
topic-tags: campaign-standard-deprecated-features
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '662'
ht-degree: 35%

---


# Recursos descontinuados e removidos {#deprecated-and-removed-features}

A Adobe avalia constantemente os recursos do produto para identificar aqueles mais antigos que devem ser substituídos por alternativas mais modernas de forma a melhorar o valor geral do cliente, sempre considerando cuidadosamente a compatibilidade com versões anteriores.

Para comunicar a remoção/substituição iminente de recursos de Campaign Standard, as seguintes regras se aplicam:

* O anúncio da descontinuação vem primeiro. Embora os recursos obsoletos ainda possam estar disponíveis para os usuários existentes, eles não serão aprimorados nem documentados.
* A remoção de recursos obsoletos ocorrerá na seguinte versão, o mais tardar. A data da remoção será anunciada nesta página.

Esse processo oferece aos clientes pelo menos um ciclo de lançamento para adaptar sua implementação a uma nova versão ou sucessor de um recurso obsoleto, antes da remoção.

>[!NOTE]
>Adobe Campaign Standard releases and new capabilities are listed in the [Release Notes](../../rn/using/release-notes.md).


## Recursos obsoletos {#deprecated-features}

Esta seção lista recursos e recursos que foram marcados como obsoletos com as versões mais recentes do Campaign Standard.

Geralmente, os recursos que estão planejados para serem removidos em uma versão futura são definidos como obsoletos primeiro, com uma alternativa fornecida. Esses recursos e funcionalidades não estão mais disponíveis para novos clientes do Campaign Standard ou não devem ser usados para novas implementações. Eles também foram removidos da documentação do produto.

Os clientes são aconselhados a revisar se utilizam o recurso/funcionalidade em sua implantação atual e a fazer planos para alterar sua implementação para usar a alternativa fornecida. Consulte a versão de remoção do público alvo para planejar suas atualizações de ambiente e projeto de acordo.

<table> 
 <thead> 
  <tr> 
   <th> <strong>Notificações por push com SDK v4</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> A partir da versão 20.1, o SDK v4 está obsoleto. <a href="https://aep-sdks.gitbook.io/docs/version-4-sdk-end-of-support-faq">Saiba mais</a>.</p><br/>
   <p>O SDK <a href="https://aep-sdks.gitbook.io/docs/">do</a> Adobe Experience Platform Mobile (anteriormente conhecido como v5) oferecerá suporte exclusivo aos recursos e funcionalidades futuros do Adobe Experience Cloud.</p></br>
     <p>
     <em>Data de remoção do público alvo: 30 de setembro de 2020</em></p>
     </td> 
  </tr> 
 </tbody> 
</table>
<table> 
 <thead> 
  <tr> 
   <th> <strong>Solicitações de privacidade - API e interface de Campanha</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>A partir da versão 19.4 da Campanha, o uso da API de Campanha e da interface para acessar e excluir solicitações está obsoleto. A exclusão do perfil de 2 etapas não estará disponível. Use o serviço <a href="https://www.adobe.io/apis/experiencecloud/gdpr.html">principal de privacidade do</a>Adobe.</p></br>
   <p>Consulte também <a href="https://helpx.adobe.com/br/campaign/kb/acs-privacy.html">Gerenciamento de solicitações</a>de privacidade.</p>
  <p> 
  <em>Data de remoção do Target: 2021</em></p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Design de e-mail - Editor de e-mail legado</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>A partir da versão 19.0 da Campanha, o editor de e-mail herdado será substituído. Use <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/designing-content/designing-content-in-adobe-campaign.html">o novo Designer</a> de email para criar e personalizar seu conteúdo de email. </p></br>
   <p>Leia <a href="https://docs.adobe.com/content/help/pt-BR/campaign-standard/using/designing-content/building-email-content/using-existing-content.html">esta seção</a> para saber como adaptar seus modelos de e-mail para o novo editor.</p></br>
  <p> 
  <em>Data de remoção do Target: 2021</em></p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Usuários e segurança - Unidades geográficas</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>A partir da versão 18.7, as unidades geográficas serão descontinuadas. As unidades organizacionais e geográficas são construções idênticas em Campanha. Os usuários devem usar unidades organizacionais sozinhas para criar a permissão do usuário/hierarquia de acesso aos dados. <a href="https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html">Saiba mais</a>. Observe que novas instâncias de Campaign Standard, bem como instâncias existentes sem unidades geográficas criadas, não podem ter esse recurso implementado a partir da versão 18.7.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

## Removed Features {#removed-features}

Esta seção lista os recursos e funcionalidades removidos do Campaign Standard.

<table> 
 <thead> 
  <tr> 
   <th> <strong>Pontuação de propensão com acionadores de Experience Cloud</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>A Pontuação de <b>propensão</b> foi descontinuada do Adobe Experience Cloud Triggers. Como consequência, essa opção foi removida da Adobe Campaign Standard. Para evitar valores desatualizados de Pontuação de propensão nos schemas de Enriquecimento, recomendamos atualizar schemas para recuperar as alterações mais recentes e republicar os Acionadores existentes. Para obter mais informações, consulte <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/integrating-with-adobe-cloud/working-with-campaign-and-triggers/using-triggers-in-campaign.html#publishing-trigger-in-campaign"> Publicar um acionador na Campanha </a>.
</p></br>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Creative SDK para Campaign Standard</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>[!DNL Adobe Creative SDK] foi descontinuado. Como consequência, a edição de imagem fornecida pelo [!DNL Creative SDK] em emails do Campaign Standard não está mais disponível a partir da versão 20.2 da Campaign.</p></br>
   </td> 
  </tr> 
 </tbody> 
</table>

## Fim da compatibilidade do {#end-of-compatibility}

<table> 
 <thead> 
  <tr> 
   <th> <strong>Microsoft Internet Explorer 11</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>A Adobe Campaign e a Adobe Experience Cloud deixaram de oferecer suporte ao Microsoft Internet Explorer 11 a partir do primeiro trimestre de 2019 e da versão Campaign 19.2. Alterne para o Microsoft Edge ou outro navegador compatível. <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/administrating/about-configuration-guidelines.html#compatible-browsers">Saiba mais</a>.</p>
   </td> 
  </tr> 
 </tbody> 
</table>
