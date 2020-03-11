---
title: Planejamento de lançamento do Campaign Standard
description: Esta página lista as próximas versões do Adobe Campaign Standard.
page-status-flag: never-activated
uuid: null
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: campaign-standard-release-planning
discoiquuid: null
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 8e614bb3e3e559a02ee5e94d9dc21e85d1b4dbd2

---


# Planejamento de versão {#release-planning}

A Adobe melhora continuamente suas soluções adicionando novos recursos, melhorias e correções.

Todas as instâncias do Adobe Campaign Standard são atualizadas com cada nova versão. Nenhuma ação é necessária para atualizar.

As atualizações são implantadas em duas fases. Primeiro, as instâncias do Stage são atualizadas para permitir que nossos clientes testem novos recursos e adaptem suas configurações, se necessário. As instâncias de produção são atualizadas posteriormente.

Todas as datas de lançamento estão sujeitas a alterações: recomendamos que você visite esta página regularmente para verificar se há atualizações.

Inscreva-se para [receber notificações](https://www.adobe.com/subscription/priority-product-update.html) de versão para obter detalhes sobre as versões mais recentes da Adobe Experience Cloud diretamente na sua caixa de entrada.

## Versão 20.2.1 - Versão de abril {#release-20-2-april-release}

As atualizações de ambiente ocorrem em ondas, durante os intervalos de tempo indicados abaixo. Informações detalhadas sobre esta versão estão disponíveis nas [Notas](../../rn/using/release-notes.md)de versão. Caso tenha mais dúvidas, entre em contato com o [Adobe Client Care](https://support.neolane.net/webApp/extranetLogin).

<table> 
 <thead> 
  <tr> 
   <th> Ambiente<br /> </th> 
   <th> Datas<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Estágio<br /> </td> 
   <td> 23-24 de março de 2020<br /> </td> 
  </tr> 
  <tr> 
   <td> Produção<br /> </td> 
   <td> 31 de março - 6 de abril de 2020<br /> </td> 
  </tr> 
 </tbody> 
</table>



## Perguntas e respostas {#questions-and-answers}

**P: Qual é o impacto?**

A: As alterações são listadas nas Notas [de](../../rn/using/release-notes.md)versão, incluindo links para a documentação relacionada. A Adobe também recomenda consultar a página [Recursos removidos e](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html)obsoletos. Essas páginas estão disponíveis para a nova versão na data de atualização do ambiente Stage.

**P: Qual é o processo de validação?**

A: À medida que sua instância de preparo é atualizada, a Adobe recomenda validar seus processos e casos de uso estão funcionando corretamente com essa nova versão e reportar qualquer problema ao [Adobe Client Care](https://support.neolane.net/webApp/extranetLogin).

**P: Haverá acesso à instância durante o processo de atualização?**

A: Não. Durante a atualização da instância, o banco de dados pode não estar acessível em alguns minutos. Todos os processos são reiniciados automaticamente.

**P: As mensagens continuarão a ser enviadas?**

A: Não. As mensagens não serão enviadas durante alguns minutos. Assim que a atualização for concluída, os processos serão reiniciados automaticamente.

**P: Os fluxos de trabalho continuarão em execução e enviarão as entregas?**

A: Não. Durante a atualização da compilação, o servidor de fluxo de trabalho e o MTA são interrompidos. Isso significa que os fluxos de trabalho não serão executados e as entregas não serão enviadas durante alguns minutos. Nenhuma ação é necessária: os fluxos de trabalho serão iniciados novamente assim que a instância for atualizada.

**P: Os links de rastreamento nas mensagens ainda funcionarão durante a atualização?**

A: Sim, eles vão funcionar. Não é possível enviar novos emails durante a atualização, mas os links de rastreamento incluídos em emails já enviados estarão operacionais.

**P: Como saber se a atualização foi concluída?**

A: Ao fazer logon no Campaign, um pop-up de notificação de versão será exibido, com a versão mais recente.

Para quaisquer outras perguntas, entre em contato com o [Adobe Client Care](https://support.neolane.net/webApp/extranetLogin).