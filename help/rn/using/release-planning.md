---
title: Planejamento de versões do Campaign Standard
description: Esta página lista as próximas versões do Adobe Campaign Standard.
audience: rn
content-type: reference
topic-tags: campaign-standard-release-planning
feature: Overview
role: User
level: Beginner
exl-id: 1f48d4da-5622-4fab-af87-fcce0e40ade1
source-git-commit: 8b049f7decc95d3959feb0193bf51287422ddaec
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 99%

---

# Planejamento da versão {#release-planning}

A Adobe está constantemente aprimorando suas soluções, adicionando novos recursos, melhorias e correções.

Todas as instâncias do Adobe Campaign Standard são atualizadas com cada nova versão. Nenhuma ação é necessária para fazer a atualização.

As atualizações são implantadas em duas fases. Primeiro, as instâncias de Preparo estão atualizadas para permitir que nossos clientes testem novos recursos e adaptem suas configurações, se necessário. As instâncias de Produção são atualizadas posteriormente.

Todas as datas de lançamento estão sujeitas a alterações. Visite esta página regularmente para verificar se há atualizações.

## Versão 22.3 - Versão de setembro de 2022 {#release-22-3-release}

As atualizações de ambientes ocorrem em ondas, durante os intervalos indicados abaixo. As datas exatas são comunicadas por email a cada cliente.

Informações detalhadas sobre esta versão estarão disponíveis nas Notas de versão antecipadas quando as atualizações do ambiente de preparo forem lançadas.

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
   <td>De 6 a 7 de setembro de 2022<br /> </td>
  </tr>
  <tr>
   <td>Produção<br /> </td>
   <td>De 13 a 29 de setembro de 2022<br /> </td>
  </tr>
 </tbody>
</table>

Caso tenha mais dúvidas, entre em contato com o [Atendimento ao cliente da Adobe](https://helpx.adobe.com/br/enterprise/using/support-for-experience-cloud.html).

## Perguntas e respostas {#questions-and-answers}

**P: Qual é o impacto?**

R: As alterações estão listadas nas [Notas de versão](../../rn/using/release-notes.md), incluindo links para a documentação relacionada. A Adobe também recomenda consultar a página [Recursos removidos e obsoletos](../../rn/using/deprecated-features.md). Essas páginas estarão disponíveis para a nova versão na data de atualização do ambiente de Preparo.

**P: Qual é o processo de validação?**

R: À medida que a sua instância de preparo for atualizada, a Adobe recomenda validar se os seus processos e casos de uso estão funcionando corretamente com essa nova versão e comunicar qualquer problema ao [Atendimento ao cliente da Adobe](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html).

**P: Haverá acesso à instância durante o processo de atualização?**

R: Não. Durante a atualização da instância, o banco de dados pode não ficar acessível durante alguns minutos. Todos os processos serão reiniciados automaticamente.

**P: As mensagens continuarão a ser enviadas?**

R: Não. Mensagens não serão enviadas durante alguns minutos. Quando a atualização é concluída, os processos são reiniciados automaticamente.

**P: Os workflows continuarão em execução e enviarão os deliveries?**

R: Não. Durante a atualização da build, o servidor de workflow e o MTA são ambos interrompidos. Isso significa que os workflows não serão executados e os deliveries não serão enviados durante alguns minutos. Nenhuma ação é necessária: os workflows serão iniciados novamente assim que a instância for atualizada.

**P: Os links de rastreamento nas mensagens ainda funcionarão durante a atualização?**

R: Sim, eles funcionarão. Não é possível enviar novos emails durante a atualização, mas os links de rastreamento incluídos em emails já enviados estarão operacionais.

**P: Como saber se a atualização foi concluída?**

R: Ao fazer logon no Campaign, um pop-up de notificação de versão será exibido com a versão mais recente.

Para outras perguntas, entre em contato com o [Atendimento ao cliente da Adobe](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html).
