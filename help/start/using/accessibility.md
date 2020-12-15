---
solution: Campaign Standard
product: campaign
title: Acessibilidade no Adobe Campaign Standard
description: Saiba mais sobre o suporte à acessibilidade no Adobe Campaign Standard Workspace.
audience: designing
content-type: reference
topic-tags: accessibility
translation-type: tm+mt
source-git-commit: 6ea28c457b1024dab315b60281adaee56eb80cd0
workflow-type: tm+mt
source-wordcount: '607'
ht-degree: 45%

---


# Acessibilidade no Adobe Campaign Standard {#accessibility-acs}

Saiba mais sobre o suporte à acessibilidade no Adobe Campaign Standard Workspace.

Acessibilidade refere-se à utilização de produtos para pessoas com limitações visuais, auditivas, cognitivas, motoras e outras. Exemplos de recursos de acessibilidade para produtos de software incluem conteúdo semeticamente estruturado, suporte a leitores de tela, equivalentes de texto para gráficos, atalhos de teclado e assim por diante.

A Adobe Campaign Standard fornece recursos que tornam mais acessível o uso, como contraste, rótulos, conteúdo estruturado, navegação pelo teclado e ajuda contextual.

## Recursos de acessibilidade {#accessibility-features}

### Contraste e cor {#contrast}

A interface do usuário do Adobe Campaign Standard se esforça para fornecer contraste suficiente no aplicativo para garantir uma experiência de visualização acessível para usuários com deficiências visuais ou coloridas baixas.

* Texto e cabeçalhos grandes foram aprimorados para atender a uma taxa de contraste de 3:1.

   ![](assets/accessibility_2.png)

* O conteúdo da ajuda e o texto do corpo no aplicativo foram atualizados para atender a uma taxa de contraste de 4.5:1.

* Os ícones de pausa e cancelamento de workflows foram atualizados para melhorar o contraste entre as cores do plano de fundo e do primeiro plano.

   ![](assets/accessibility_1.png)

* Cor, forma e local não são os únicos métodos usados para comunicar informações ou hierarquia no aplicativo.

### Interface do usuário {#user-interface}

A interface do usuário do Adobe Campaign Standard facilita a interação de todos os usuários com o conteúdo, adicionando textos alternativos aos elementos visuais e usando a estrutura semântica para transmitir informações visualmente e programaticamente.

* Quando o usuário deixa um campo de ID obrigatório em branco, um gráfico indica visualmente qual campo está com erro com texto de mensagem de erro e que as mesmas informações são transmitidas programaticamente para usuários com tecnologias de assistência, como leitores de tela.

   ![](assets/accessibility_3.png)

* O conteúdo que aparece ao passar o mouse ou focar pode ser rejeitado pelo usuário e não obscurece outro conteúdo.

   ![](assets/accessibility_4.png)

* Foram adicionados textos alternativos para imagem e nomes acessíveis para botões, que podem ser lidos em voz alta com tecnologia de assistência, em vez de se basearem apenas em dicas visuais para identificar elementos.

<!--
### Create responsive resize for multiple devices {#resize-devices}

When designing for multiple devices and platforms, it's important to create a seamless experience for screen sizes across mobile and desktop resolutions.

Adobe Campaign Standard allows you to design and test emails and push notifications on different devices such as: iPhone, Android devices, iPad, Android tablet and desktop.

![](assets/accessibility_6.png)
-->

## Ajuda contextual {#contextual-help}

A ajuda contextual pode ajudá-lo a entender melhor os diferentes campos e recursos solicitados disponíveis. Ele também orienta você na documentação do produto para obter mais informações sobre o recurso selecionado.

Ao criar um email, você pode acessar uma dica de ferramenta que fornecerá descrições de recursos e links para a documentação do produto.

![](assets/accessibility_7.png)

## Suporte para tecnologia assistiva {#screen-magnifiers}

Procuramos tornar o aplicativo Adobe Campaign Standard o mais utilizável possível por várias tecnologias de assistência, incluindo, mas não limitado a, teclados modificados, softwares de aumento de tela, leitores de tela, software de reconhecimento de voz e outros dispositivos de assistência.

## Trabalhe no seu idioma preferido {#languages}

O Adobe Campaign Standard está disponível em diferentes idiomas: inglês, francês e alemão.

Observe que o idioma está configurado na instalação e não pode ser alterado posteriormente.

## Atalhos de teclado {#shortcuts}

### Página inicial {#homepage-shortcuts}

| Atalho | Ação |
|:-:|:-:|
| Guia | Navegar pelos elementos individuais da interface do usuário |
| Enter ou Space | Ativar o item selecionado |

### Designer de email {#email-designer-shortcuts}

| Atalho | Ação |
|:-:|:-:|
| CTRL + Z | Desfazer |
| CTRL + Y | Refazer |

### Relatórios dinâmicos {#report-shortcuts}

| Atalho | Ação |
|:-:|:-:|
| CTRL + O | Abrir projeto |
| CTRL + S | Salvar |
| Shift + CTRL + S | Salvar como |
| Alt + R | Atualizar projeto |
| Shift + CTRL + V | Baixar CSV |
| Alt + P | Imprimir |
| CTRL + Z | Desfazer |
| CTRL + Shift + Z | Refazer |
| Alt + B | Novo painel em branco |
| Alt + A | Nova forma livre |
| Alt + 1 | Nova tabela de forma livre |
| Alt + 2 | Nova linha |
| Alt + 3 | Nova barra |
| Alt + S | Enviar relatório agora |
| Shift + Alt + S | Enviar relatório programado |
| Shift = Alt + L | Relatórios agendados |

## Leitura adicional {#further-reading}

O Adobe Campaign Standard se esforça para oferecer um grau cada vez maior de acessibilidade, facilitando o uso do produto para todos.

Recomendamos que você use o [Formulário de feedback de acessibilidade da Adobe](https://www.adobe.com/accessibility/feedback.html) para nos enviar sugestões de aprimoramento e problemas de acessibilidade que você esteja observando.

Você também pode consultar as [Notas de versão do Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/release-notes.html?lang=pt-BR#release-notes) para conhecer os últimos recursos e melhorias.