---
title: Recursos removidos e obsoletos do Campaign Standard
description: Esta página lista recursos obsoletos e removidos do Adobe Campaign Standard.
page-status-flag: never-activated
uuid: null
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: campaign-standard-deprecated-features
discoiquuid: null
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d8ad3801dba50e357c21a7551e897e0e2c5aedc5

---


# Recursos descontinuados e removidos {#deprecated-and-removed-features}

A Adobe avalia constantemente os recursos do produto para identificar recursos mais antigos que devem ser substituídos por alternativas mais modernas para melhorar o valor geral do cliente, sempre considerando cuidadosamente a compatibilidade com versões anteriores.

Para comunicar a remoção/substituição iminente dos recursos do Campaign Standard, as seguintes regras se aplicam:

* O anúncio da desaprovação vem primeiro. Embora os recursos obsoletos ainda possam estar disponíveis para os usuários existentes, eles não serão aprimorados nem documentados.
* A remoção de recursos obsoletos ocorrerá na seguinte versão, o mais tardar. A data de destino real para remoção é anunciada nesta página.

Esse processo oferece aos clientes pelo menos um ciclo de lançamento para adaptar sua implementação a uma nova versão ou sucessor de um recurso obsoleto, antes da remoção real.

>[!NOTE]
>As versões do Adobe Campaign Standard e os novos recursos estão listados nas [Notas](../../rn/using/release-notes.md)de versão.


## Recursos obsoletos {#deprecated-features}

Esta seção lista os recursos e recursos que foram marcados como obsoletos com as versões mais recentes do Campaign Standard.

Geralmente, os recursos que estão planejados para serem removidos em uma versão futura são definidos como obsoletos primeiro, com uma alternativa fornecida. Esses recursos e recursos não estão mais disponíveis para novos clientes do Campaign Standard ou não devem ser usados para nenhuma nova implementação. Eles também são removidos da documentação do produto.

Os clientes são aconselhados a revisar se utilizam o recurso/recurso em sua implantação atual e a fazer planos para alterar sua implementação para usar a alternativa fornecida. Consulte a data de remoção da meta para planejar suas atualizações de ambiente e projeto de acordo.

<table> 
 <thead> 
  <tr> 
   <th> <strong>Notificações por push com SDK v4</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> A partir da versão 20.1, o SDK v4 está obsoleto. <a href="https://aep-sdks.gitbook.io/docs/version-4-sdk-end-of-support-faq">Saiba mais</a>.</p><br/>
   <p>O SDK <a href="https://aep-sdks.gitbook.io/docs/">do</a> Adobe Experience Platform Mobile (anteriormente conhecido como v5) oferecerá suporte exclusivo aos recursos e funcionalidades futuros da Adobe Experience Cloud.</p></br>
     <p>Data de remoção de meta: 30 de setembro de 2020</p>
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
   <td> <p>O Adobe Creative SDK foi descontinuado. Como consequência, a edição de imagens com o Creative SDK nos e-mails do Campaign Standard foi substituída a partir da versão 20.1.</p></br>
  <p> Data de remoção de meta: Março de 2020 - versão 20.2 da Campanha</p>
   </td> 
  </tr> 
 </tbody> 
</table>
<table> 
 <thead> 
  <tr> 
   <th> <strong>Solicitações de privacidade - API e interface do Campaign</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>A partir da versão 19.4 da Campanha, o uso da API da Campanha e da interface para acessar e excluir solicitações está obsoleto. A exclusão de perfil de 2 etapas não estará disponível. Use o <a href="https://www.adobe.io/apis/experiencecloud/gdpr.html">Adobe Privacy Core Service</a>.</p></br>
   <p>Consulte também Gerenciamento de <a href="https://helpx.adobe.com/campaign/kb/acs-privacy.html">privacidade no Campaign Standard</a>.</p>
  <p> Data de remoção de meta: Julho de 2020 - lançamento da Campanha 20.5</p>
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
   <td> <p>A partir da versão 19.0 do Campaign, o editor de e-mail herdado será substituído. Use <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/designing-content/designing-content-in-adobe-campaign.html">o novo Designer</a> de email para criar e personalizar seu conteúdo de email. </p></br>
   <p>Leia <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/designing-content/building-email-content/using-existing-content.html">esta seção</a> para saber como adaptar seus modelos de e-mail para o novo editor.</p></br>
  <p> Data de remoção de meta: Outubro de 2020 - lançamento da Campanha 20.6</p>
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
   <td> <p>A partir da versão 18.7, as unidades geográficas serão descontinuadas. As unidades organizacionais e geográficas são construções idênticas no Campaign. Os usuários devem usar unidades organizacionais sozinhas para criar a permissão do usuário/hierarquia de acesso aos dados. <a href="https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html">Saiba mais</a>. Observe que as novas instâncias do Campaign Standard, bem como as instâncias existentes sem unidades geográficas criadas, não podem ter esse recurso implementado a partir da versão 18.7.</p>
   </td> 
  </tr> 
 </tbody> 
</table>


## Fim da compatibilidade {#end-of-compatibility}

<table> 
 <thead> 
  <tr> 
   <th> <strong>Microsoft Internet Explorer 11</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>O Adobe Campaign e a Adobe Experience Cloud deixaram de oferecer suporte ao Microsoft Internet Explorer 11 a partir do primeiro trimestre de 2019 e da versão 19.2 do Campaign. Alterne para o Microsoft Edge ou outro navegador compatível. <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/getting-started/discovering-the-interface/compatible-browsers.html">Saiba mais</a>.</p>
   </td> 
  </tr> 
 </tbody> 
</table>
