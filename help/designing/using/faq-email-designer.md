---
solution: Campaign Standard
product: campaign
title: 'Perguntas frequentes sobre o Designer de email '
description: Perguntas frequentes sobre o Email Designer.
audience: designing
content-type: reference
topic-tags: working-with-campaign-and-analytics
feature: Design de email
role: Profissional
level: Intermediário
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '445'
ht-degree: 7%

---


# Perguntas frequentes sobre o Designer de email

## Qual é a diferença entre blocos de conteúdo e fragmentos de conteúdo?

Blocos de conteúdo e fragmentos de conteúdo são pedaços de conteúdo reutilizável que são comuns em vários emails. Eles são usados para garantir a consistência entre emails e também para otimizar/padronizar a criação de email. As diferenças entre blocos de conteúdo e fragmentos de conteúdo são o nível de personalização possível.

* Os blocos de conteúdo são HTML puro, onde o código HTML é inserido manualmente (não é uma interface do usuário fácil de usar, é um código de fonte direta). Embora seja realmente orientado para pessoas com conhecimento em HTML, permite o nível de personalização não disponível em fragmentos de conteúdo.

* Fragmentos de conteúdo são partes visuais do conteúdo criadas por meio do Designer de email, usando sua interface de usuário amigável. No entanto, não é possível personalizar o conteúdo. Se a personalização for necessária, ela só poderá ser feita por meio de blocos de conteúdo.

## Como posso adicionar preenchimento a um elemento da estrutura HTML?

Você pode adicionar o preenchimento usando a navegação estrutural HTML.

1. Na parte inferior esquerda da tela, clique na navegação estrutural HTML.

   ![](assets/do-not-localize/breadcrumb.png)

1. Clique no elemento que deseja adicionar um preenchimento.
1. Clique na tag principal na navegação estrutural HTML.
Agora você pode adicionar um preenchimento a esse elemento.

## Posso importar conteúdo HTML no Email Designer?

Você pode fazer upload de seu próprio conteúdo HTML para o Designer de email. Se ele não tiver sido criado por meio do Email Designer, ele será carregado no modo de compatibilidade que foi projetado para manter seu HTML original, mas limita determinados recursos de edição por meio da interface do usuário.

Para obter mais informações, consulte [Modo de compatibilidade](../../designing/using/using-existing-content.md#compatibility-mode)

## Como criar meu primeiro conteúdo de e-mail?

Primeiro de tudo, crie um email na página inicial.
Em seguida, para adicionar conteúdo a um email, é necessário adicionar um componente de estrutura e inserir um componente de conteúdo nele.

Para obter mais informações, consulte [Criação de um email do zero](../../designing/using/quick-start.md#from-scratch-email)

## Por que preciso atualizar fragmentos?

O Designer de email está em melhoria contínua. Se você criou um conteúdo de email do zero, de um modelo predefinido ou criou fragmentos, pode ser necessário atualizar o conteúdo para a versão mais recente para evitar problemas como problemas de colisão de CSS.

Para obter mais informações, consulte [Atualização de fragmentos](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-updates)

## Posso salvar estilos em um tema?

Os estilos não podem ser salvos como um tema para futura reutilização. Entretanto, o estilo CSS pode ser salvo em um modelo de conteúdo ou em um email.

Para obter mais informações, consulte [Estilos](../../designing/using/styles.md)

## Quais fontes estão disponíveis?

Ao editar estilos, somente as fontes da Web oficialmente compatíveis pela maioria dos clientes de email estarão disponíveis por padrão por meio da interface do usuário. O uso de fontes personalizadas requer a atualização do código HTML.
