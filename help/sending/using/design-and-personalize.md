---
title: Criar conteúdo personalizado
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: Saiba como projetar o conteúdo da mensagem e tente evitar problemas comuns que possam impedir a execução da entrega. 
feature: Deliverability
role: User
level: Intermediate
exl-id: 938989c9-ef19-4297-9b8b-c38eb1cec1f0
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1039'
ht-degree: 69%

---

# Criar conteúdo personalizado {#build-personalized-content}

Ao criar o conteúdo da sua mensagem, tente evitar problemas comuns que possam impedir a execução da entrega. Na maioria das vezes, possíveis erros estão relacionados à [personalização](../../designing/using/personalization.md), formatação ao [usar um conteúdo existente](../../designing/using/using-existing-content.md) - e [conversão de um conteúdo de HTML](../../designing/using/using-existing-content.md#converting-an-html-content) - e [imagens](../../designing/using/images.md).

## Otimizar personalização {#optimize-personalization}

Para evitar problemas comuns que podem impedir a execução da entrega e melhorar a experiência dos destinatários, o Adobe Campaign permite personalizar suas mensagens.

Você pode usar os dados dos destinatários armazenados no banco de dados do Adobe Campaign ou coletados por meio de rastreamento, landing pages, assinaturas, etc.
As noções básicas de personalização são apresentadas [nesta seção](../../designing/using/personalization.md).

Verifique se o conteúdo da sua mensagem foi projetado corretamente para evitar erros, que geralmente estão relacionados à personalização.

O conteúdo dinâmico pode ser adicionado manualmente para exibir um conteúdo diferente para seus destinatários, de acordo com as condições definidas no editor de expressão. Ao adicionar conteúdo dinâmico, você sempre deve deixar uma variante padrão para destinatários que não atendem às condições selecionadas.
Para obter mais informações sobre conteúdo dinâmico, consulte [esta seção](../../designing/using/personalization.md#defining-dynamic-content-in-an-email).

**Dicas** - Visualize seu email com diferentes perfis de teste para verificar se o conteúdo dinâmico foi configurado corretamente.

## Criar conteúdo otimizado {#optimize-content}

Ao criar e-mails, lembre-se das práticas recomendadas gerais abaixo.

* Mantenha o design simples

* Lembre-se dos usuários de dispositivos móveis

* Evite criar emails só com imagens

* Use fontes seguras para emails

* Codifique caracteres especiais

### Linha de assunto

Trabalhe a [linha de assunto](../../designing/using/subject-line.md) para melhorar as taxas de abertura:

* Evite assuntos muito longos. Use no máximo 50 caracteres

* Evite usar palavras repetitivas como “grátis” ou “oferta”, que podem ser consideradas spam

* Evite letras maiúsculas e caracteres especiais como “!”, “£”, “€” e “$”.

### Mirror page

Sempre inclua um link de mirror page. A posição preferencial é a parte superior do email. [Saiba mais](../../designing/using/personalization.md#adding-a-content-block)

### Link de unsubscription

O link de unsubscription é essencial. Deve ser visível e válido e o formulário deve ser funcional. Saiba mais sobre as diretrizes de link de cancelamento de assinatura [nesta seção](../../designing/using/personalization.md#about-targeting-dimension).

Por padrão, quando a mensagem é analisada, uma [regra de tipologia](../../sending/using/control-rules.md) de controle verifica se um link para opção de não participação foi incluído e gera um aviso caso ele esteja ausente.

**Dica**: como o erro humano é sempre possível, verifique se o link para opção de não participação funciona corretamente antes de cada envio. Por exemplo, ao enviar a prova, verifique se o link é válido, se o formulário está online e se o campo “Não contatar mais este destinatário” foi alterado para Sim.

Veja [nesta seção](../../designing/using/personalization.md#adding-a-content-block) como inserir um link para opção de não participação.

### Tamanho do email {#email-size}

Para evitar problemas de desempenho ou de entrega, o tamanho máximo recomendado de um email é de aproximadamente **35KB**.

Para manter o email abaixo do limite, considere o seguinte:

* Remover estilos redundantes ou em desuso

* Mover um conteúdo de email para uma [página inicial](../../channels/using/getting-started-with-landing-pages.md)

* Minimizar o uso de código

Certifique-se de que testou as alterações antes do envio final.

No Adobe Campaign, o tamanho máximo padrão de um email está definido como **100MB**. <!--This limit enables to prevent any error that could indefinitely increase the size of an email, which can lead to a system crash.-->

Se o limite for atingido, a mensagem que excede o limite falhará e uma mensagem de erro será exibida nos logs de delivery. As outras mensagens do mesmo delivery não serão afetadas. Nesse caso, você deve adaptar a parte dinâmica do template de email ou os fragmentos de conteúdo usados pelo delivery. <!--If you need assistance, or if you have any question or request about the **[!UICONTROL Maximum message size]** option, reach out to your Adobe contact.-->

O Adobe recomenda manter o valor padrão do tamanho máximo da mensagem. No entanto, este valor pode ser alterado na opção **[!UICONTROL Maximum message size]**, por meio do menu **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**, somente por [administradores funcionais](../../administration/using/users-management.md#functional-administrators).

>[!IMPORTANT]
>
>Se você definir esse valor como zero, nenhum limite será aplicado.

### Duração do SMS

Por padrão, o número de caracteres em um SMS atende aos padrões do GSM (Global System for Mobile Communications). As mensagens SMS que usam a codificação GSM são limitadas a 160 caracteres ou a 153 caracteres por SMS para as mensagens enviadas em várias partes.

A transliteração consiste em substituir um caractere de um SMS por outro quando esse caractere não é considerado pelo padrão GSM. Observe que a inserção de campos de personalização no conteúdo da mensagem SMS pode inserir caracteres que não são considerados pela codificação GSM. Você pode autorizar a transliteração de caracteres marcando a caixa correspondente na guia Configurações do canal SMPP da **[!UICONTROL External account]** correspondente.
Saiba mais [nesta seção](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration).

**Dicas**:

* Para manter todos os caracteres inalterados nas mensagens SMS, a fim de não alterar os nomes próprios por exemplo, não ative a transliteração.

* No entanto, se suas mensagens SMS contiverem muitos caracteres que não forem considerados pelo padrão GSM, habilite a transliteração para limitar os custos de envio das mensagens.

Saiba mais [nesta seção](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration).

### Design de email responsivo

O design responsivo garante que o email seja processado de maneira ideal para o dispositivo no qual ele é aberto.

* Use HTML responsivo de email em vez de HTML para web

* Use o modo de visualização e envie provas para testar a renderização no máximo de dispositivos possível. Saiba como [visualizar mensagem](../../sending/using/previewing-messages.md) antes de enviar.

* O Campaign Email Designer vem com modelos formatados com design responsivo para dispositivos móveis. Saiba mais [nesta página](../../designing/using/using-reusable-content.md#content-templates).

## Gerenciamento de imagens {#manage-images}

Siga as diretrizes abaixo ao usar imagens.

### Impedir o bloqueio de imagens

Alguns clientes de e-mail bloqueiam imagens por padrão, e alguns usuários alteram suas configurações para impedir que imagens sejam salvas em caso de uso de dados. Portanto, se as imagens não forem baixadas, a mensagem inteira poderá ser perdida. Para evitar isso:

* Equilibre imagens e texto no seu conteúdo. Evite criar emails só com imagens.

* Se o texto precisa estar contido em uma imagem, use alt e title para garantir que sua mensagem seja exibida. Estilize o texto alt/title para melhorar a aparência.

* Evite o uso de imagens de fundo, pois elas não são suportadas por alguns clientes de e-mail.

### Tornar as imagens responsivas

Tente tornar as imagens responsivas e redimensionáveis. Observe que isso pode ter um impacto no custo, pois demora mais para ser criado.

### Usar referência de imagem absoluta

Para serem acessadas de fora, as imagens usadas em emails e recursos públicos vinculados a campanhas devem estar presentes em um servidor acessível externamente.

## Visualizar sua mensagem {#preview-msg}

A Adobe recomenda visualizar a mensagem para verificar a personalização e como os destinatários verão a entrega.

No Designer de email, o botão **[!UICONTROL Preview]** permite exibir a renderização de cada conteúdo para um destinatário. Os campos de personalização e os elementos condicionais do conteúdo são substituídos pelas informações correspondentes para o perfil selecionado. [Saiba mais](../../sending/using/previewing-messages.md)
