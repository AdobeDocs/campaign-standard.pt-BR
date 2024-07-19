---
title: Perguntas frequentes sobre Designer
description: Perguntas frequentes sobre Email Designer.
audience: designing
content-type: reference
topic-tags: working-with-campaign-and-analytics
feature: Email Design
role: User
level: Intermediate
exl-id: f3208380-a4cf-4944-aa24-883995d1075d
source-git-commit: 13d419c5fc51845ee14f8a3b288f4c467e0a60d9
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 3%

---

# Perguntas frequentes sobre Designer

## Qual é a diferença entre blocos de conteúdo e fragmentos de conteúdo?

Blocos de conteúdo e fragmentos de conteúdo são conteúdos reutilizáveis comuns em vários emails. Eles são usados para garantir a consistência entre os emails e também para otimizar/padronizar a criação de emails. As diferenças entre blocos de conteúdo e fragmentos de conteúdo são o nível de personalização possível.

* Os blocos de conteúdo são HTML puro, em que o código HTML é inserido manualmente (não é uma interface amigável, é um código-fonte direto). Embora seja realmente direcionado para pessoas com conhecimento em HTML, permite um nível de personalização não disponível em fragmentos de conteúdo.

* Fragmentos de conteúdo são partes visuais do conteúdo criadas por meio do Designer de email, usando sua interface de usuário amigável. No entanto, não é possível personalizar o conteúdo. Se a personalização for necessária, ela só poderá ser feita por meio de blocos de conteúdo.

## Como posso adicionar preenchimento a um elemento da estrutura HTML?

Você pode adicionar preenchimento usando a navegação estrutural do HTML.

1. Na parte inferior esquerda da tela, clique na navegação estrutural do HTML.

   ![](assets/do-not-localize/breadcrumb.png)

1. Clique no elemento que deseja adicionar um preenchimento.
1. Clique na tag principal na navegação estrutural do HTML.
Agora você pode adicionar um preenchimento a este elemento.

## Posso importar conteúdo de HTML no Designer de email?

Você pode fazer upload do seu próprio conteúdo de HTML para o Designer de email. Se não tiver sido criado pelo Email Designer, ele será carregado no modo de compatibilidade, projetado para manter seu HTML original, mas limita determinados recursos de edição por meio da interface do usuário.

Para obter mais informações, consulte [Modo de compatibilidade](../../designing/using/using-existing-content.md#compatibility-mode)

## Como crio meu primeiro conteúdo de e-mail?

Primeiro de tudo, crie um email a partir da página inicial.
Em seguida, para adicionar conteúdo a um email, é necessário adicionar um componente de estrutura e inserir um componente de conteúdo nele.

Para obter mais informações, consulte [Criando um email do zero](../../designing/using/quick-start.md#from-scratch-email)

## Por que preciso atualizar fragmentos?

O Designer de email está em melhoria contínua. Se você criou um conteúdo de email do zero, a partir de um modelo predefinido ou se criou fragmentos, talvez seja necessário atualizar o conteúdo para a versão mais recente para evitar problemas como problemas de colisão de CSS.

Para obter mais informações, consulte [Atualizando fragmentos](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-updates)

## Posso salvar estilos em um tema?

Os estilos não podem ser salvos como um tema para futura reutilização. No entanto, o estilo CSS pode ser salvo em um modelo de conteúdo ou em um email.

Para obter mais informações, consulte [Estilos](../../designing/using/styles.md)

## Quais fontes estão disponíveis?

Ao editar estilos, somente as fontes da Web oficialmente compatíveis pela maioria dos clientes de email estarão disponíveis por padrão por meio da interface do usuário. O uso de fontes personalizadas requer a atualização do código de HTML.
