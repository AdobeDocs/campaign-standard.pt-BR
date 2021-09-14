---
title: Notas de versão anteriores
description: Notas de versão anteriores
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '413'
ht-degree: 100%

---

# Notas de versão anteriores {#new-release}

Esta página descreve novos recursos, melhorias e correções incluídos na próxima versão do Campaign Standard.

>[!CAUTION]
>
> Esse conteúdo está sujeito a alterações sem aviso prévio até a data de atualização dos ambientes de estágio. Saiba mais na [página de planejamento de versão](../../rn/using/release-planning.md).

## Versão 21.3 - Setembro de 2021 {#release-21-3---sept-2021}


**Novidades**


<table> 
<thead> 
<tr> 
<th> <strong>Interface unificada da Experience Cloud</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>A barra de cabeçalho do Adobe Campaign foi alterada para unificar e melhorar sua experiência em todos os produtos e serviços da Experience Cloud. Essas alterações foram projetadas para facilitar sua vida, inclusive:</p>
<ul>
<li>É mais fácil alternar entre suas organizações ou mudar de aplicativo.</li>
<li>Ajuda do usuário aprimorada: com a inclusão da Experience League no produto, os resultados da pesquisa também abrangem resultados de fóruns da comunidade e mais conteúdo de vídeo, facilitando o acesso a mais conteúdo para aproveitar ao máximo o aplicativo. Também adicionamos um mecanismo de feedback diretamente no menu Ajuda, facilitando o relato de problemas ou o compartilhamento de suas ideias.</li>
<li>Notificações aprimoradas: o menu suspenso Notificações agora tem duas guias, uma para suas próprias notificações de produtos e uma para anúncios de produtos mais globais.</li>
</ul>
<!--<p>For more information refer to the <a href="../../start/using/interface-description.md#top-bar">detailed documentation</a>.
</p>-->
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>Trilha de auditoria</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>A nova trilha de auditoria captura em tempo real uma lista abrangente de ações e eventos que ocorrem no Adobe Campaign. Ela inclui uma forma de autoatendimento a fim de acessar um histórico de dados para ajudar a responder a perguntas como:</p>
<ul>
<li>O que aconteceu com esse fluxo de trabalho e quem o atualizou pela última vez?</li>
<li>Quem fez as últimas mudanças?</li>
<li>Qual era o estado anterior?</li>
</ul>
<p>O Adobe Campaign agora audita ações de criação, edição e exclusão para: workflows, opções e recursos personalizados. As modificações desses itens também são rastreadas.</p>
<!--<p>For more information refer to the <a href="../../administration/using/audit.md">detailed documentation</a>.
</p>-->
</td> 
</tr> 
</tbody> 
</table>


<table> 
<thead> 
<tr> 
<th> <strong>Modo de diagnóstico do fluxo de trabalho</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>Agora você pode executar workflows da campanha no modo de diagnóstico. Esse modo registra informações para ajudar a solucionar problemas de execução. Todo o plano de execução é registrado se uma consulta de fluxo de trabalho levar, por padrão, mais de um minuto.</p>
<!--<p>For more information refer to the <a href="../../administration/using/audit.md">detailed documentation</a>.
</p>-->
</td> 
</tr> 
</tbody> 
</table>

**Melhorias**

* Ao ser criada uma entrega recorrente em um fluxo de trabalho, vinculado a um conteúdo do Adobe Experience Manager, o status de aprovação do conteúdo agora é verificado antes do envio.
* O limite de conexão de banco de dados agora está alinhado ao pacote do Campaign para evitar erros de conexão.
* Adição de uma verificação de consistência ao criar índices em recursos personalizados e melhoria das mensagens de erro.

**Correções**

* Correção de um erro de tempo limite ao importar conteúdo de email de um URL. (CAMP-49054)
* Correção de um erro (-69) causado pelo fim da sessão ao acessar um URL marcado ou atualizar uma página do navegador. (CAMP-49003, CAMP-48930, CAMP-48894)
* Correção de um problema ao sincronizar regras do servidor de capacidade de entrega herdado para o novo servidor de capacidade de entrega. (CAMP-48923)
* Correção de um problema ao carregar um modelo de email com tags HTML no Designer de email. (CAMP-48243)
