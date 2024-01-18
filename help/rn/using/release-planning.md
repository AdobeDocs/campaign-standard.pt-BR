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
source-git-commit: ff6e926b66547632b74e58cc0e419c83a4ea556e
workflow-type: ht
source-wordcount: '408'
ht-degree: 100%

---

# Planejamento da versão {#release-planning}

A Adobe está constantemente aprimorando suas soluções, adicionando novos recursos, melhorias e correções.

Todas as instâncias do Adobe Campaign Standard são atualizadas com cada nova versão. Nenhuma ação é necessária para fazer a atualização.

As atualizações são implantadas em duas fases. Primeiro, as instâncias de Preparo estão atualizadas para permitir que nossos clientes testem novos recursos e adaptem suas configurações, se necessário. As instâncias de Produção são atualizadas posteriormente.

Todas as datas de lançamento estão sujeitas a alterações; acesse esta página com frequência para verificar se há atualizações. As atualizações de ambientes ocorrem em ondas, durante os intervalos indicados abaixo. As datas exatas são comunicadas por email a cada cliente.

## Versão 24.1 – Versão do inverno de 2024 {#release-24-1-release}

Informações detalhadas sobre esta versão estão disponíveis nas [Notas de versão](release-notes.md) quando as atualizações do ambiente de preparo são iniciadas.

<table>
 <thead>
  <tr>
   <th> Ambientes </th>
   <th> Datas </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td>Preparo </td>
   <td>16 de janeiro a 13 de fevereiro de 2024 </td>
  </tr>
  <tr>
   <td>Produção </td>
   <td>23 de janeiro a 20 de fevereiro de 2024 </td>
  </tr>
 </tbody>
</table>

## Perguntas e respostas {#questions-and-answers}

**P: Qual é o impacto?**

R: As alterações estão listadas nas [Notas de versão](../../rn/using/release-notes.md), incluindo links para a documentação relacionada. A Adobe também recomenda consultar a página [Recursos removidos e obsoletos](../../rn/using/deprecated-features.md). Essas páginas estarão disponíveis para a nova versão na data de atualização do ambiente de Preparo.

**P: Qual é o processo de validação?**

R: À medida que a sua instância de preparo for atualizada, a Adobe recomenda validar se os seus processos e casos de uso estão funcionando corretamente com essa nova versão e comunicar qualquer problema ao [Atendimento ao cliente da Adobe](https://helpx.adobe.com/br/enterprise/using/support-for-experience-cloud.html).

**P: Haverá acesso à instância durante o processo de atualização?**

R: Não. Durante a atualização da instância, o banco de dados pode não ficar acessível durante alguns minutos. Todos os processos serão reiniciados automaticamente.

**P: As mensagens continuarão a ser enviadas?**

R: Não. Mensagens não serão enviadas durante alguns minutos. Quando a atualização é concluída, os processos são reiniciados automaticamente.

**P: Os workflows continuarão em execução e enviarão as entregas?**

R: Não. Durante a atualização da build, o servidor de workflow e o MTA são ambos interrompidos. Isso significa que os workflows não serão executados e as entregas não serão enviadas durante alguns minutos. Nenhuma ação é necessária: os workflows serão iniciados novamente assim que a instância for atualizada.

**P: Os links de rastreamento nas mensagens ainda funcionarão durante a atualização?**

R: Sim, eles funcionarão. Não é possível enviar novos emails durante a atualização, mas os links de rastreamento incluídos em emails já enviados estarão operacionais.

**P: Como saber se a atualização foi concluída?**

R: Ao fazer logon no Campaign, um pop-up de notificação de versão será exibido com a versão mais recente.

Para outras perguntas, entre em contato com o [Atendimento ao cliente da Adobe](https://helpx.adobe.com/br/enterprise/using/support-for-experience-cloud.html).
