---
title: Usar modelos de entrega
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: Os templates do delivery oferecem mais eficiência ao fornecer cenários prontos para os tipos mais comuns de atividades.
feature: Deliverability
role: User
level: Intermediate
exl-id: ca134a7f-9035-4885-b4cb-1170b6ec10cc
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '815'
ht-degree: 63%

---

# Usar modelos {#use-templates}

Os templates da entrega oferecem mais eficiência ao fornecer cenários prontos para os tipos mais comuns de atividades. Com modelos, os profissionais de marketing podem implantar novas campanhas com personalização mínima em um período de tempo menor.

Saiba mais sobre templates da entrega [nesta seção](../../start/using/marketing-activity-templates.md).

## Introdução a modelos de entrega {#gs-templates}

Um [template da entrega](../../start/using/marketing-activity-templates.md#creating-a-new-template) permite definir uma única vez um conjunto de propriedades técnicas e funcionais que atendam às suas necessidades e que possam ser reutilizadas para entregas futuras. Você pode economizar tempo e padronizar entregas quando necessário.

Quando você gerencia várias marcas no Adobe Campaign, a Adobe recomenda ter um subdomínio por marca. Por exemplo, um banco pode ter vários subdomínios correspondentes a cada uma de suas agências regionais. Se um banco for proprietário do domínio bluebank.com, seus subdomínios podem ser @ny.bluebank.com, @ma.bluebank.com, @ca.bluebank.com, etc. Ter um template da entrega por subdomínio permite usar sempre os parâmetros pré-configurados certos para cada marca, o que evita erros e economiza tempo.

**Dica**: para evitar erros de configuração no Campaign, recomendamos duplicar um modelo nativo e alterar suas propriedades em vez de criar um novo modelo.

## Configurar endereços

* O endereço do remetente é obrigatório para o envio de um email.

* Alguns ISPs (provedores de serviço de internet) verificam a validade do endereço do remetente antes de aceitarem mensagens.

* Um endereço formado incorretamente pode resultar na rejeição pelo servidor de recebimento. Você precisa ter certeza de que o endereço informado está correto.

* O endereço deve identificar explicitamente o remetente. O domínio deve ser de propriedade e registrado pelo remetente.

* A Adobe recomenda a criação de contas de email que correspondam aos endereços especificados para entrega e respostas. Verifique com o administrador do sistema de mensagens.

Na seção **[!UICONTROL Advanced parameters]** das propriedades de um modelo de email, o campo **[!UICONTROL From (email address)]** corresponde ao endereço do remetente.

![](assets/template-parameters.png)

O domínio de endereço deve ser o mesmo que o subdomínio que você configurou.

Os campos **[!UICONTROL Reply to]** correspondem ao endereço de email e ao nome usados para respostas.

**Dica** - a Adobe recomenda o uso de um endereço real, como o atendimento ao cliente da sua marca. Nesse caso, se um destinatário enviar uma resposta, o atendimento ao cliente poderá resolvê-lo.

Para alterar o nome do remetente que aparecerá no cabeçalho das mensagens enviadas, vá para a guia **[!UICONTROL Properties]** da página inicial do Designer de Email (acessível por meio do ícone de início) e clique no bloco **[!UICONTROL Default sender name]**.

![](assets/template-content.png)

Para aumentar a taxa de abertura de suas entregas, a Adobe recomenda usar um nome que seja facilmente identificável pelos destinatários, como o nome da sua marca.

**Dica** - Para melhorar ainda mais a experiência do destinatário, você pode adicionar o nome de uma pessoa, por exemplo &quot;Emma da Megastore&quot;.

Para obter mais informações sobre como personalizar o nome do remetente, consulte [Remetente de email](../../designing/using/subject-line.md#email-sender).

## Personalizar o nome do remetente do SMS

Na seção **Parâmetros avançados** das propriedades de um modelo de SMS, a opção **De** permite personalizar o nome do remetente da mensagem SMS usando uma sequência de caracteres. Ele aparecerá como o nome do remetente da mensagem SMS no celular do destinatário.

Se esse campo estiver vazio, será usado o número de origem fornecido na conta externa. Se nenhum número de origem for fornecido, o código curto será usado. Para saber mais, consulte [Configuração de SMS](../../administration/using/configuring-sms-channel.md).

**Dica** - Verifique a legislação do seu país em relação à modificação do endereço do remetente. Você também deve consultar seu provedor de serviço SMS se ele oferecer essa funcionalidade.

## Configurar um grupo de controle

Depois que a entrega é enviada, você pode comparar o comportamento dos destinatários excluídos com os destinatários que receberam a entrega. Você pode então medir a eficiência de suas campanhas. Saiba mais sobre grupos de controle [nesta seção](../../sending/using/control-group.md).

## Usar tipologias para aplicar filtros ou regras de controle

Uma tipologia contém regras de verificação aplicadas durante a fase de análise, antes de enviar qualquer mensagem.

Na seção **[!UICONTROL Advanced parameters]** > **[!UICONTROL Preparation]** das propriedades do modelo, altere a tipologia padrão de acordo com suas necessidades.

Por exemplo, para controlar melhor o tráfego de saída, você pode definir quais endereços IP podem ser usados, estabelecendo uma afinidade por subdomínio e criando uma tipologia por afinidade. As afinidades são definidas no arquivo de configuração da instância. Entre em contato com o administrador do Adobe Campaign.

Para obter mais informações sobre tipologias, consulte [esta seção](../../sending/using/managing-typologies.md).

## Vincular uma marca a um modelo

Os parâmetros dos e-mails enviados relacionados à identidade de uma marca (como o logotipo da marca ou o endereço do remetente) são gerenciados centralmente no Adobe Campaign. Você pode criar uma ou várias marcas e vinculá-las a templates do delivery.

Para obter mais informações sobre como usar e configurar marcas no Adobe Campaign, consulte Marcas.

Para exibir ou alterar a marca atribuída a um modelo de entrega, selecione o botão Editar propriedades do modelo e navegue até os detalhes da marca.

![](assets/template-brand.png)

Para obter mais informações sobre vincular uma marca a um modelo, consulte [Atribuição de uma marca a um email](../../administration/using/branding.md#assigning-a-brand-to-an-email).

Saiba como criar e configurar uma marca [nesta seção](../../administration/using/branding.md#creating-a-brand).
