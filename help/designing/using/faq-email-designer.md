---
title: 'Perguntas frequentes sobre o Designer de email '
description: Perguntas frequentes sobre o Email Designer.
page-status-flag: never-activated
uuid: effa1028-66b2-4bef-b5e4-7319dbb23d5d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: working-with-campaign-and-analytics
discoiquuid: eb3639f5-7246-46c4-8ddb-da9413b40c32
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 23d6c78f924635a8ce512fd91b4a46db395e8bd1

---


# Perguntas frequentes sobre o Designer de email

## Qual é a diferença entre blocos de conteúdo e fragmentos de conteúdo?

Os blocos de conteúdo e fragmentos de conteúdo são pedaços de conteúdo reutilizável que são comuns em vários emails. Eles são usados para garantir a consistência entre e-mails e também para otimizar/padronizar a criação de e-mails. As diferenças entre blocos de conteúdo e fragmentos de conteúdo são o nível de personalização possível.

* Os blocos de conteúdo são HTML puro, no qual o código HTML é inserido manualmente (não é uma interface de usuário fácil de usar, é um código fonte direto). Embora esteja realmente orientado para pessoas com conhecimento HTML, permite que o nível de personalização não esteja disponível em fragmentos de conteúdo.

* Fragmentos de conteúdo são partes visuais do conteúdo criado por meio do Email Designer, usando sua interface de usuário amigável. No entanto, não é possível personalizar o conteúdo. Se a personalização for necessária, ela só poderá ser feita por meio de blocos de conteúdo.

## Como posso adicionar preenchimento a um elemento da estrutura HTML?

Você pode adicionar preenchimento usando a navegação estrutural HTML.

1. Na parte inferior esquerda da tela, clique na trilha de navegação HTML.

   ![](assets/breadcrumb.png)

1. Clique no elemento que deseja adicionar um preenchimento.
1. Clique na marca pai na navegação estrutural HTML.
Agora você pode adicionar um preenchimento a esse elemento.

## É possível importar conteúdo HTML no Designer de email?

Você pode fazer upload de seu próprio conteúdo HTML para o Designer de email. Se não tiver sido criado por meio do Email Designer, ele será carregado no modo de compatibilidade, projetado para manter seu HTML original, mas limita determinados recursos de edição por meio da interface do usuário.

Para obter mais informações, consulte o modo [Compatibilidade](../../designing/using/using-existing-content.md#compatibility-mode)

## Como criar meu primeiro conteúdo de email?

Primeiro, crie um email a partir do home page.
Em seguida, para adicionar conteúdo a um email, é necessário adicionar um componente de estrutura e inserir um componente de conteúdo nele.

Para obter mais informações, consulte [Criar um email do zero](../../designing/using/quick-start.md#from-scratch-email)

## Por que preciso atualizar fragmentos?

O Designer de e-mail está em melhoria contínua. Se você criou um conteúdo de email do zero, de um modelo predefinido ou se criou fragmentos, pode ser necessário atualizar o conteúdo para a versão mais recente para evitar problemas como problemas de colisão de CSS.

Para obter mais informações, consulte [Atualização de fragmentos](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-updates)

## Posso salvar estilos em um tema?

Os estilos não podem ser salvos como um tema para reutilização futura. Entretanto, o estilo CSS pode ser salvo em um modelo de conteúdo ou em um email.

Para obter mais informações, consulte [Estilos](../../designing/using/styles.md)

## Quais fontes estão disponíveis?

Ao editar estilos, somente as fontes da Web oficialmente suportadas pela maioria dos clientes de e-mail estão disponíveis por padrão na interface do usuário. O uso de fontes personalizadas requer a atualização do código HTML.
