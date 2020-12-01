---
solution: Campaign Standard
product: campaign
title: Acessibilidade no Adobe Campaign Standard
description: Saiba mais sobre o suporte de acessibilidade no Adobe Campaign Standard Workspace.
audience: designing
content-type: reference
topic-tags: accessibility
translation-type: tm+mt
source-git-commit: c10633d1371cd6475a573a8c851c5f7e364baf62
workflow-type: tm+mt
source-wordcount: '682'
ht-degree: 0%

---


# Acessibilidade no Adobe Campaign Standard {#accessibility-acs}

Saiba mais sobre o suporte de acessibilidade no Adobe Campaign Standard Workspace.

Acessibilidade refere-se à utilização de produtos para pessoas com deficiências visuais, auditivas, cognitivas, motoras e outras. Exemplos de recursos de acessibilidade para produtos de software incluem suporte a leitores de tela, equivalentes de texto para gráficos, atalhos de teclado, mudança de cores de exibição para alto contraste e assim por diante.

A Adobe Campaign Standard fornece algumas ferramentas que tornam o uso acessível, como contraste, navegação pelo teclado, ajuda contextual e redimensionamento responsivo.

## Recursos de acessibilidade {#accessibility-features}

### Contraste {#contrast}

A interface do usuário do Adobe Campaign Standard se esforça para fornecer contraste suficiente no aplicativo para garantir uma experiência de visualização acessível para usuários com deficiências visuais ou coloridas baixas.

* Os ícones de pausa e cancelamento de workflows foram atualizados para melhorar o contraste entre o plano de fundo e o primeiro plano.

   ![](assets/accessibility_1.png)

* O texto exibido quando um delivery é bem-sucedido continha um texto verde grande com um contraste insuficiente entre o plano de fundo e o primeiro plano. O contraste foi atualizado com uma relação mínima de 3:1.

   ![](assets/accessibility_2.png)

* A Adobe Campaign Standard garante que a cor, a forma ou o local não sejam os únicos métodos usados para comunicar informações ou hierarquia.

### Interface do usuário {#user-interface}

A interface do usuário do Adobe Campaign Standard facilita a visualização e a audição de conteúdo, incluindo a separação de primeiro plano e a adição de textos alternativos aos diferentes botões disponíveis.

* Quando o usuário deixa um campo de ID obrigatório em branco, um gráfico indica visualmente qual campo está com erro com um texto de mensagem de erro.

   ![](assets/accessibility_3.png)

* O conteúdo que aparece ao passar o mouse ou no foco pode ser rejeitado pelo usuário e não obscurece outro conteúdo.

   ![](assets/accessibility_4.png)

* Textos alternativos para botões de imagem foram adicionados e podem ser lidos em vez de exibirem uma ilustração.

   ![](assets/accessibility_5.png)

* As células dos cabeçalhos da tabela de dados não ficam vazias no canto da tabela ao usar o lista.

### Criar redimensionamento responsivo para vários dispositivos {#resize-devices}

Ao projetar para vários dispositivos e plataformas, é importante criar uma experiência perfeita para tamanhos de tela em resoluções móveis e de desktop.

A Adobe Campaign Standard permite que você crie e teste emails e envie notificações por push em diferentes dispositivos, como: iPhone, dispositivos Android, iPad, tablet e desktop Android.

![](assets/accessibility_6.png)

## Ajuda contextual {#contextual-help}

>[!NOTE]
>
> A ajuda contextual só está disponível ao usar o designer de email.

A ajuda contextual pode ajudá-lo a entender melhor os diferentes campos e recursos solicitados disponíveis. Ele também orienta você na documentação do produto para obter mais informações sobre o recurso selecionado.

Ao criar um email, você pode passar o cursor sobre o botão de informações. Uma dica de ferramenta será exibida, fornecendo descrições dos recursos e links para a documentação do produto.

![](assets/accessibility_7.png)

## Suporte para ampliadores de tela {#screen-magnifiers}

Um leitor de tela lê o texto que aparece na tela do computador. Ele também lê informações não textuais, como rótulos de botões ou descrições de imagens no aplicativo, fornecidas em tags de acessibilidade ou atributos.

No Adobe Campaign Standard, o conteúdo e a funcionalidade ainda estão disponíveis mesmo se o usuário substituir as propriedades de espaçamento do texto.

## Trabalhe no seu idioma preferido {#languages}

O Adobe Campaign Standard está disponível em diferentes idiomas: Inglês, Francês e Alemão.

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

A Adobe Campaign Standard se esforça para oferecer um grau cada vez maior de acessibilidade, facilitando o uso do produto para todos.

Recomendamos que você use o [Formulário de feedback sobre acessibilidade do Adobe](https://www.adobe.com/accessibility/feedback.html) para nos enviar sugestões de aprimoramento e problemas de acessibilidade que você está enfrentando.

Você também pode consultar [Notas de versão do Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/release-notes.html?lang=en#release-notes) para seguir as melhorias e os recursos mais recentes.