---
title: Sobre o design de conteúdo da página de aterrissagem
seo-title: Sobre o design de conteúdo da página de aterrissagem
description: Sobre o design de conteúdo da página de aterrissagem
seo-description: Saiba mais sobre as especificidades do editor de conteúdo da página de aterrissagem.
page-status-flag: nunca ativado
uuid: 8b230690-8a63-44da-b4ed-8e9d8fd84262
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: concepção
content-type: referência
topic-tags: edição-página-inicial-conteúdo
discoiquuid: 212720d2-5d57-4e7a-bb72-10512050e78c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ea825afe573959d95d0f7f3f6e79dd38ac5a678a

---

# Sobre o design de conteúdo da página de aterrissagem{#about-landing-page-content-design}

Use o editor de conteúdo padrão para criar e modificar o conteúdo de suas páginas iniciais no Adobe Campaign.

Esta seção descreve as especificidades do editor de conteúdo da página inicial:

* [Interface do editor de conteúdo da página de aterrissagem](../../channels/using/landing-page-content-editor-interface.md)
* [Gerenciamento da estrutura e do estilo da página inicial](../../channels/using/managing-landing-page-structure-and-style.md)
* [Alteração de propriedades de dados de formulário de página inicial](../../channels/using/changing-a-landing-page-form-data-properties.md)

Para saber mais sobre ações comuns a uma ou mais atividades de marketing, consulte as seguintes seções:

* Para obter mais informações sobre como personalizar um conteúdo de página inicial, consulte [Inserir um campo](../../designing/using/personalization.md#inserting-a-personalization-field) de personalização e [Adicionar um bloco](../../designing/using/personalization.md#adding-a-content-block)de conteúdo.
* Para obter mais informações sobre a definição de conteúdo dinâmico em uma página de aterrissagem, consulte [Definição de conteúdo dinâmico em uma página](../../channels/using/defining-dynamic-content-in-a-landing-page.md)de aterrissagem.
* Para obter mais informações sobre como inserir links em uma página de aterrissagem, consulte [Inserir um link](../../designing/using/links.md#inserting-a-link).
* Para obter mais informações sobre como inserir imagens em uma página de aterrissagem, consulte [Inserir imagens](../../designing/using/images.md).

Verifique também as práticas recomendadas [gerais para o design](../../designing/using/overview.md#content-design-best-practices)de conteúdo.

>[!NOTE]
>
>Se sua instância foi instalada antes da versão 19.0 do Adobe Campaign Standard, você ainda terá acesso ao editor de conteúdo de email herdado. A interface, os princípios de uso e configuração são os mesmos descritos abaixo para as páginas iniciais. No entanto, todos os recursos podem não estar disponíveis ou mantidos no editor de conteúdo de e-mail herdado, que foi substituído a partir da versão 19.0. Para editar rapidamente seu conteúdo de email por meio de uma interface de arrastar e soltar com funcionalidades estendidas, use o [Email Designer](../../designing/using/overview.md).

## Práticas recomendadas de design de página inicial {#landing-pages-best-practices-design}

* Ao editar o conteúdo **da página** inicial:

   * Antes de importar um modelo de página HTML no Adobe Campaign, verifique se o modelo é aberto e exibido corretamente em vários navegadores.
   * Se a página HTML contiver scripts JavaScript, eles precisarão ser executados sem erros fora do editor. Em geral, evite usar scripts no conteúdo da mensagem para garantir que ele seja processado corretamente pelos clientes de email.
   * Ao criar um modelo, recomendamos adicionar um atributo **'type'** às tags. Essas informações serão processadas pelo editor e ajudarão o usuário a vincular um campo de banco de dados ao campo de formulário ao configurar o aplicativo da Web.
   Exemplo de código HTML no modelo:

   ```
   <input id="email" type="email" name="email"/>
   ```

   A lista oficial de atributos 'type' está disponível no seguinte endereço: [http://www.w3schools.com/tags/att_input_type.asp](http://www.w3schools.com/tags/att_input_type.asp)