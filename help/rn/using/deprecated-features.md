---
title: Recursos obsoletos e removidos do Campaign Standard
description: Esta página lista recursos obsoletos e removidos do Adobe Campaign Standard.
audience: rn
content-type: reference
topic-tags: campaign-standard-deprecated-features
feature: Overview
role: User
level: Beginner
exl-id: 03797137-c01c-48dc-b25b-8e72741abb04
source-git-commit: 47d0f4c42d84e2107da65fae5528af0705f2165f
workflow-type: tm+mt
source-wordcount: '868'
ht-degree: 63%

---

# Recursos obsoletos e removidos {#deprecated-and-removed-features}

A Adobe avalia constantemente os recursos do produto para identificar os mais antigos que devem ser substituídos por alternativas mais modernas para melhorar o valor geral oferecido ao cliente, sempre considerando cuidadosamente a compatibilidade com versões anteriores.

Para comunicar a remoção/substituição iminente dos recursos do Adobe Campaign Standard, são aplicadas as seguintes regras:

* O anúncio da descontinuação vem primeiro. Embora os recursos obsoletos ainda possam estar disponíveis para os usuários existentes, eles não serão aprimorados nem documentados.
* A remoção de recursos obsoletos ocorrerá na seguinte versão, o mais tardar. A data da remoção será anunciada nesta página.

Esse processo oferece aos clientes pelo menos um ciclo de lançamento para adaptar sua implementação a uma nova versão ou sucessor de um recurso obsoleto, antes da remoção.

>[!NOTE]
>As versões do Adobe Campaign Standard e os novos recursos estão listados nas [Notas de versão](../../rn/using/release-notes.md).


## Recursos obsoletos {#deprecated-features}

Esta seção lista os recursos e funcionalidades marcados como obsoletos nas versões mais recentes do Campaign Standard.

Geralmente, os recursos que estão planejados para serem removidos em uma versão futura são definidos como obsoletos primeiro, com uma alternativa fornecida. Esses recursos e funcionalidades não estão mais disponíveis para novos clientes do Campaign Standard ou não devem ser usados para novas implementações. Eles também foram removidos da documentação do produto.

Os clientes são aconselhados a revisar se utilizam o recurso/funcionalidade em sua implantação atual e a fazer planos para alterar sua implementação para usar a alternativa fornecida. Consulte a versão de remoção de público alvo para planejar de modo adequado suas atualizações de ambiente e de projeto.

<table> 
 <thead> 
  <tr> 
   <th> <strong>Integração com o serviço Destinos do público-alvo</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> A partir da versão do Campaign Standard 21.3, a integração com o serviço de Destinos do público-alvo será descontinuada. </p>
   <p>Para uma nova implementação, não é mais possível integrar o serviço Destinos do público-alvo ao Adobe Campaign Standard. No entanto, é possível integrar o Campaign e o Adobe Experience Platform por meio de Fontes e Destinos. <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/aep-sources-destinations/get-started-sources-destinations.html?lang=en">Saiba mais</a>.</p>
     <em>Data de remoção do Target: Setembro de 2022</em></p>
     </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Integração com o Adobe Experience Platform Data Connector</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> A partir da versão Campaign Standard 21.3, a integração com o Adobe Experience Platform Data Connector será substituída. </p>
   <p>Para nova implementação, não é mais possível integrar o Adobe Experience Platform Data Connector ao Adobe Campaign Standard. No entanto, é possível integrar o Campaign e o Adobe Experience Platform por meio de Fontes e Destinos. <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/aep-sources-destinations/get-started-sources-destinations.html?lang=en">Saiba mais</a>.</p>
     <em>Data de remoção do Target: Setembro de 2022</em></p>
     </td> 
  </tr> 
 </tbody> 
</table>


<table> 
 <thead> 
  <tr> 
   <th> <strong>Email Design – Editor de email legado</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>A partir da versão 19.0 do Campaign, o editor de email legado se tornará obsoleto. Use <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/designing-content-in-adobe-campaign.html">Designer de email do Campaign</a> para criar e personalizar o conteúdo do email. </p></br>
   <p>Leia <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/building-email-content/using-existing-content.html">esta seção</a> para saber como adaptar seus modelos de email ao novo editor.</p></br>
  <p> 
  <em>Data de remoção do target: fim de 2022</em></p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Usuários e segurança – Unidades geográficas</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>A partir da versão 18.7 do Campaign, as unidades geográficas ficarão obsoletas. As unidades organizacionais e geográficas são construções idênticas no Campaign. Os usuários devem usar unidades organizacionais sozinhas para criar a permissão do usuário/hierarquia de acesso aos dados. <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/users-and-security/organizational-units.html?lang=pt-BR#administrating">Saiba mais</a>. Observe que novas instâncias do Campaign Standard, bem como instâncias existentes sem unidades geográficas criadas, não podem ter esse recurso implementado a partir da versão 18.7.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

## Recursos removidos {#removed-features}

Esta seção lista os recursos e funcionalidades removidos do Campaign Standard.



<table> 
 <thead> 
  <tr> 
   <th> <strong>Notificações por push com o SDK v4</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> A partir da versão 20.1 do Campaign, o SDK v4 ficará obsoleto. <a href="https://aep-sdks.gitbook.io/docs/version-4-sdk-end-of-support-faq">Saiba mais</a>.</p><br/>
   <p>O <a href="https://aep-sdks.gitbook.io/docs/">Adobe Experience Platform Mobile SDK</a> (anteriormente conhecido como v5) agora oferecem suporte exclusivo para recursos e funcionalidades futuros do Adobe Experience Cloud.</p>
   <p>Após 31 de agosto de 2021, os clientes podem continuar baixando e usando os SDKs versão 4, mas não haverá suporte do Atendimento ao cliente nem acesso aos fóruns.</p>
   <p>Saiba como migrar do SDK v4 para o Adobe Experience Platform Mobile SDK <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/configuring-mobile/sdkv4-migration.html">nesta página</a>.</p></br>
     </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Solicitações de privacidade – API e interface do Campaign</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>A partir da versão 21.2 do Campaign, o uso da API e da interface do Campaign para solicitações de acesso e exclusão se tornará obsoleto. A exclusão do perfil de 2 etapas não estará disponível. Use o <a href="https://developer.adobe.com/experience-platform-apis/references/privacy-service">serviço principal de privacidade da Adobe</a>.</p></br>
   <p>Consulte também o <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/getting-started/privacy/privacy-requests.html?lang=br">Gerenciamento de solicitações de acesso a dados pessoais</a>.</p>
  </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
 <tr> 
   <th> <strong>Linha de assunto preditiva</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> A partir de abril de 2021, o recurso de Linha de assunto preditiva será desativado.</p><br/>
   <p>Sugerimos que você aproveite os recursos de email alimentados por IA para analisar e prever taxas abertas, tempos de envio ideais e probabilidade de churn com base em métricas históricas de engajamento. <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/preparing-and-testing-messages/predictive.html">Saiba mais</a></p></br>
     </td> 
  </tr> 
  </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Pontuação de propensão com acionadores da Experience Cloud</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>A <b>Pontuação de propensão</b> foi desativada dos acionadores da Adobe Experience Cloud. Como consequência, essa opção foi removida do Adobe Campaign Standard. Para evitar valores desatualizados de Pontuação de propensão nos esquema de enriquecimento, recomendamos a atualização de esquemas para recuperar as alterações mais recentes e republicar os acionadores existentes. Para obter mais informações, consulte <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/working-with-campaign-and-triggers/using-triggers-in-campaign.html"> Publicar um acionador no Campaign </a>.
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
   <td> <p>[!DNL Adobe Creative SDK] foi desativado. Como consequência, a edição de imagem fornecida por [!DNL Creative SDK] em emails do Campaign Standard não está mais disponível a partir da versão 20.2 do Campaign.</p></br>
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
   <td> <p>O Adobe Campaign e a Adobe Experience Cloud deixaram de oferecer suporte ao Microsoft Internet Explorer 11 a partir do segundo trimestre de 2019, e da versão 19.2 do Campaign. Use o Microsoft Edge ou outro navegador compatível. <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/about-configuration-guidelines.html">Saiba mais</a>.</p>
   </td> 
  </tr> 
 </tbody> 
</table>
