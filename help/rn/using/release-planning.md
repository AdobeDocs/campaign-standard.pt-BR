---
solution: Campaign Standard
product: campaign
title: Planejamento de versões do Campaign Standard
description: Esta página lista as próximas versões do Adobe Campaign Standard.
audience: rn
content-type: reference
topic-tags: campaign-standard-release-planning
translation-type: tm+mt
source-git-commit: 1b971fbf7b5d36283434db0389534a3dda2ebb45
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 99%

---


# Planejamento de versão {#release-planning}

A Adobe melhora continuamente suas soluções, adicionando novos recursos, melhorias e correções.

Todas as instâncias do Adobe Campaign Standard são atualizadas com cada nova versão. Nenhuma ação é necessária para fazer a atualização.

As atualizações são implantadas em duas fases. Primeiro, as instâncias de Preparo são atualizadas para permitir que nossos clientes testem novos recursos e adaptem suas configurações, se necessário. As instâncias de Produção são atualizadas posteriormente.

Todas as datas de lançamento estão sujeitas a alterações: recomendamos que você visite esta página regularmente para verificar se há atualizações.

## Versão 21.2 - Versão de maio {#release-21-2-release}

As atualizações de ambientes ocorrem em ondas, durante os intervalos de tempo indicados abaixo. As datas exatas são comunicadas por email a cada cliente.

Informações detalhadas sobre esta versão ficam disponíveis nas [Notas de versão](../../rn/using/release-notes.md) quando as atualizações do ambiente de preparo começam.

<table>
 <thead>
  <tr>
   <th> Ambiente<br /> </th>
   <th> Datas<br /> </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td>Preparo<br /> </td>
   <td>19 de abril - 20 de abril de 2021<br /> </td>
  </tr>
  <tr>
   <td> Produção<br /> </td>
   <td>26 de abril - 3 de maio de 2021<br /> </td>
  </tr>
 </tbody>
</table>

Caso tenha mais dúvidas, entre em contato com o [Atendimento ao cliente da Adobe](https://helpx.adobe.com/br/enterprise/using/support-for-experience-cloud.html).

Assine as [notificações de versão do Campaign Standard](http://amc-mkt-prod1-t.adobe-campaign.com/lp/LP25?service=%40rZ5cqp2DgNzrgz0alKPInakNbPSTeJYozZYnS7Wbs802u4GlISkHZX4omtK00nAU6xzZ6luEWQzr7kQ9pkCwJYumWkU) para receber detalhes sobre as próximas versões diretamente na sua caixa de entrada.

## Perguntas e respostas {#questions-and-answers}

**P: Qual é o impacto?**

R: As alterações estão listadas nas [Notas de versão](../../rn/using/release-notes.md), incluindo links para a documentação relacionada. A Adobe também recomenda consultar a página [Recursos removidos e obsoletos](../../rn/using/deprecated-features.md). Essas páginas estarão disponíveis para a nova versão na data de atualização do ambiente de Preparo.

**P: Qual é o processo de validação?**

R: À medida que a sua instância de preparo for atualizada, a Adobe recomenda validar se os seus processos e casos de uso estão funcionando corretamente com essa nova versão e comunicar qualquer problema ao [Atendimento ao cliente da Adobe](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html).

**P: Haverá acesso à instância durante o processo de atualização?**

R: Não. Durante a atualização da instância, o banco de dados pode não ficar acessível durante alguns minutos. Todos os processos serão reiniciados automaticamente.

**P: As mensagens continuarão a ser enviadas?**

R: Não. Mensagens não serão enviadas durante alguns minutos. Assim que a atualização for concluída, os processos serão reiniciados automaticamente.

**P: Os workflows continuarão em execução e enviarão os deliveries?**

R: Não. Durante a atualização da build, o servidor de workflow e o MTA são ambos interrompidos. Isso significa que os workflows não serão executados e os deliveries não serão enviados durante alguns minutos. Nenhuma ação é necessária: os workflows serão iniciados novamente assim que a instância for atualizada.

**P: Os links de rastreamento nas mensagens ainda funcionarão durante a atualização?**

R: Sim, eles funcionarão. Não é possível enviar novos emails durante a atualização, mas os links de rastreamento incluídos em emails já enviados estarão operacionais.

**P: Como saber se a atualização foi concluída?**

R: Ao fazer logon no Campaign, um pop-up de notificação de versão será exibido com a versão mais recente.

Para outras perguntas, entre em contato com o [Atendimento ao cliente da Adobe](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html).
