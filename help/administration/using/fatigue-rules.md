---
title: Regras de esgotamento
seo-title: Regras de esgotamento
description: Regras de esgotamento
seo-description: Crie regras de fadiga para gerenciar a comunicação excessiva com perfis.
page-status-flag: nunca ativado
uuid: fa5e3ded-36c2-4f16-b97a-119b85adf679
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: administração
content-type: referência
topic-tags: regras de trabalho com tipologia
discoiquuid: 4337a80b-0fb9-4a37-bce3-fe2121a66586
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 51d80fc9c683e39b9d08ba7d36b76b71a9dd1e8c

---


# Regras de esgotamento{#fatigue-rules}

## Sobre regras de fadiga {#about-fatigue-rules}

As regras de fadiga permitem que os comerciantes definam regras comerciais globais entre canais que excluirão automaticamente perfis solicitados em excesso das campanhas.

Para implementar regras de fadiga, defina um número máximo de mensagens por perfil e selecione um período no qual a regra será aplicada. Durante a preparação da entrega, os perfis são excluídos da entrega, se aplicável, dependendo do número de mensagens já enviadas a eles.

>[!NOTE]
>
>Para que as regras de fadiga sejam aplicadas, é necessário definir uma data de contato para a entrega. Se você optar por enviar mensagens imediatamente, a regra de fadiga não será aplicada.

Tópicos relacionados:

* [Preparação](../../administration/using/configuring-email-channel.md#preparation)
* [Gerenciamento de tipologias](../../administration/using/about-typology-rules.md#managing-typologies)
* [Regras de tipologia](../../administration/using/about-typology-rules.md#typology-rules)
* [Otimizar a frequência de comunicação para evitar a fadiga de contato](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Engageyourcustomersateverystep)

## Criação de uma regra de fadiga {#creating-a-fatigue-rule}

To create and configure a **[!UICONTROL Fatigue]** typology rule, apply the following steps:

1. Clique no logotipo do Adobe Campaign, no canto superior esquerdo da interface, em seguida, selecione **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Typologies]** &gt; **[!UICONTROL Typology rules]**.

   ![](assets/fatigue4.png)

1. Na lista de regras de tipologia, clique em **[!UICONTROL Create]**.

   ![](assets/fatigue.png)

1. No **[!UICONTROL Rule type]** campo, selecione **[!UICONTROL Fatigue]**.

   ![](assets/fatigue3.png)

1. No **[!UICONTROL Channel]** campo, selecione a qual canal sua regra será aplicada. Você pode selecionar um único canal (email, SMS, mala direta, aplicativo móvel) ou selecionar **[!UICONTROL All channels]**. Consulte [Escolhendo o canal](#choosing-the-channel).

   ![](assets/fatigue5.png)

1. Na **[!UICONTROL General]** guia, defina o método para calcular o número máximo de mensagens por perfil. Você pode escolher um limite constante ou uma variável. Você também pode refinar o limite de perfis e entregas. Para obter mais informações, consulte [Definição do limite](#defining-the-threshold).

   ![](assets/fatigue2.png)

1. Escolha um **[!UICONTROL Sliding period]** em que a regra de tipologia será aplicada. Para obter mais informações, consulte [Configuração do período](#setting-the-sliding-period)deslizante.

   ![](assets/fatigue6.png)

   Neste exemplo (veja as capturas de tela anteriores), optamos por enviar um número máximo de 4 mensagens em um período deslizante de 15 dias.

1. Na **[!UICONTROL Application criteria]** guia, você pode optar por aplicar essa regra a todas as entregas ou restringir a aplicabilidade da regra de acordo com a mensagem a ser enviada. A regra só será executada se a condição do aplicativo for atendida. Por exemplo, você pode aplicar a regra somente em mensagens com um rótulo começando por uma determinada palavra ou com uma ID contendo determinadas letras. Consulte [Limitação da aplicabilidade de uma regra](../../administration/using/filtering-rules.md#restricting-the-applicability-of-a-filtering-rule)de filtragem.

   ![](assets/fatigue20.png)

1. Selecione a **[!UICONTROL Typologies]** guia e vincule sua regra de tipologia à tipologia usada para as entregas. Consulte [Gerenciamento de tipologias](../../administration/using/about-typology-rules.md#managing-typologies) e regras [](../../administration/using/about-typology-rules.md#typology-rules)de tipologia.

   ![](assets/fatigue12.png)

   >[!NOTE]
   >
   >A tipologia poderá ser definida no template de delivery para ser aplicada automaticamente a todos os deliveries criados usando esse template.

Durante a preparação da entrega, os perfis são excluídos da entrega, se for caso disso, dependendo do número de entregas que já lhes foram enviadas. Você pode exibir os resultados da execução da regra de fadiga nos registros de entrega. Consulte [Visualização dos resultados](#viewing-the-fatigue-results)de fadiga.

![](assets/fatigue16.png)

>[!CAUTION]
>
>Para que as regras de fadiga funcionem, é necessário definir uma data de contato para a entrega. Se você optar por enviar mensagens imediatamente, a regra de fadiga não será aplicada.

## Escolhendo o canal {#choosing-the-channel}

As regras de fadiga estão disponíveis para vários canais. O canal é definido no **[!UICONTROL Channel]** campo das configurações da regra de tipologia. Você pode selecionar um único canal ou selecionar **[!UICONTROL All channels]**.

![](assets/fatigue5.png)

**Canais disponíveis**

Os seguintes canais estão disponíveis:

* Email
* Móvel
                            (SMS)
* Mala direta
* Aplicativo móvel: esse canal permite enviar notificações por push para perfis ou assinantes do aplicativo. Se você optar por enviar notificações a perfis, eles serão compatíveis com as regras de fadiga de vários canais.

   >[!CAUTION]
   >
   >As regras de fadiga não são compatíveis com as notificações por push enviadas aos assinantes do aplicativo. Se você estiver enviando mensagens para assinantes do aplicativo, as regras de fadiga não se aplicarão.

* Todos os canais: essa opção permite que você aplique a regra a todos os canais. Por exemplo, você pode decidir enviar no máximo 3 mensagens por mês em qualquer canal. Se você enviou dois emails para um perfil na semana passada e tentar enviar uma notificação por push hoje, o mesmo perfil será excluído.

**Tipos de entrega**

As regras de esgotamento são compatíveis com todos os tipos de entrega: entregas únicas, entregas recorrentes, entregas de fluxo de trabalho e mensagens transacionais.

**As mensagens** transacionais podem ser usadas para enviar mensagens de serviço direcionadas a um evento (rtEvent), bem como mensagens de marketing (perfis de definição de metas), por exemplo uma mensagem de remarketing. As regras de fadiga são compatíveis apenas com mensagens de marketing (perfis de definição de metas). As mensagens transacionais de eventos não contêm informações de perfil, portanto, não são compatíveis com regras de fadiga (mesmo no caso de enriquecimento com perfis). Com o suporte de mensagens de marketing em mensagens transacionais, você pode **aplicar uma regra de fadiga a todos os canais, incluindo mensagens** transacionais de marketing.

## Definição do limite {#defining-the-threshold}

Cada regra de fadiga define um limite, isto é, o número máximo de mensagens que podem ser enviadas para um perfil durante um determinado período. Depois que esse limite for atingido, não poderá ocorrer mais deliveries até que o final do período seja considerado. Esse processo permite que você exclua automaticamente um perfil de uma entrega se uma mensagem exceder o limite definido, evitando assim a solicitação excessiva.

Os valores de limite podem ser constantes ou variáveis. Isso significa que, para um determinado período, os limites podem variar de um perfil para outro, ou mesmo para o mesmo perfil.

**Uso de um limite de correção**

O limite representa o maior número de mensagens que podem ser enviadas para um perfil durante o período em questão.

Por padrão, o limite é constante e você precisa indicar um número máximo de mensagens autorizadas pela regra.

![](assets/fatigue2.png)

**Uso de um limite de variável**

Para definir um limite de variável, selecione o **[!UICONTROL Depends on the recipient]** valor no **[!UICONTROL Threshold type]** campo.

![](assets/fatigue15.png)

Em seguida, você tem duas opções:

* selecione um campo de perfil: o limite variará para cada perfil de acordo com o campo selecionado. Por exemplo, se você tiver estendido o recurso de perfis com um campo "Frequência de comunicação", clique no botão à direita do **[!UICONTROL Threshold computation formula]** campo e selecione seu campo. Para cada perfil, o limite assumirá o valor do campo "Frequência de comunicação".

   ![](assets/fatigue21.png)

* defina uma fórmula: clique no segundo botão à direita do **[!UICONTROL Threshold computation formula]** campo para definir uma fórmula de cálculo de limite avançada. Por exemplo, você pode indexar o número de mensagens autorizadas de acordo com o segmento ao qual o perfil pertence. Isso significa que um perfil pertencente ao segmento 'Web' pode receber mais mensagens do que outros perfis. Uma fórmula de **[!UICONTROL Iif (@origin='Web', 5, 3)]** tipo autoriza a entrega de 5 mensagens para perfis do segmento da Web e 3 para outros segmentos.

   ![](assets/fatigue14.png)

**Refinar o limite de perfis e entregas**

Por padrão, todas as mensagens são consideradas para o cálculo do limite. Marque a **[!UICONTROL Refine Threshold on profiles and deliveries]** caixa para filtrar os perfis e as entregas a serem contados ao preparar a entrega.

No exemplo a seguir, somente os perfis masculinos são contados e somente as entregas com um rótulo que começa com **Newsletters** são contadas.

![](assets/fatigue13.png)

Refinar o limite de entregas é diferente de restringir a aplicabilidade da regra inteira ( **[!UICONTROL Application criteria]** guia):

* **[!UICONTROL Application criteria]**: você escolhe executar a regra ou não de acordo com critérios específicos. Por exemplo, se sua condição de aplicativo for "Label começa com Newsletter", a regra será aplicada somente às entregas que respeitam essa condição. Se o rótulo da entrega começar com "Promoção", a regra não será executada.
* **[!UICONTROL Refine threshold on profiles and deliveries > Deliveries to count]**: todas as entregas que usam essa regra de tipologia executarão a regra, mas você decide, entre as entregas passadas e programadas, quais as que deseja contar. Por exemplo, se sua restrição for "Label começa com Newsletter", a regra será executada mesmo se o rótulo de entrega começar com "Promo". Contará, durante o período deslizante selecionado, o número de entregas cujo rótulo começa com "Newsletter".

## Definir o período deslizante {#setting-the-sliding-period}

As regras de fadiga são definidas em períodos flexíveis de n dias. O período é configurado na **[!UICONTROL Sliding period]** seção, por exemplo 2 semanas, 7 dias ou 5 horas.

![](assets/fatigue6.png)

Quando a regra é executada, as entregas passadas e as entregas programadas são levadas em conta. Isto garante que, num determinado período de deslizamento, o limiar nunca seja ultrapassado.

Por exemplo, se você definir um período de 48 horas, o sistema terá uma aparência de 48 horas **antes da data** do contato e 48 horas **após a data** do contato. Assim, o período selecionado é duplicado para permitir a integração de entregas futuras e de entregas anteriores.

Para restringir as entregas consideradas para um período de 2 semanas, informe **Dia** e **7** ou 1 semana na seção Período **** deslizante. As entregas enviadas até 7 dias antes da data de entrega e programadas até 7 dias após a data de entrega em que a regra é aplicada serão consideradas no cálculo.

## Ver os resultados da fadiga {#viewing-the-fatigue-results}

Durante a preparação da entrega, os perfis são excluídos da entrega, se for caso disso, dependendo do número de entregas que já lhes foram enviadas. Para exibir os resultados da execução da regra de fadiga, clique no botão no canto inferior direito do **[!UICONTROL Deployment]** bloco.

![](assets/fatigue22.png)

Três guias estão disponíveis, mostrando os detalhes dos resultados da execução de fadiga, incluindo o nome da regra que se aplica:

* Registros de entrega:

   ![](assets/fatigue17.png)

* Logs de exclusão:

   ![](assets/fatigue18.png)

* Causas de exclusão:

   ![](assets/fatigue19.png)

## Exibindo o relatório resumido da regra de fadiga {#viewing-the-fatigue-rule-summary-report}

O Adobe Campaign apresenta um relatório dedicado sobre regras de fadiga para ajudá-lo a entender como elas são aplicadas a suas campanhas. Isso permite que você saiba como suas campanhas impactam umas às outras e faça os ajustes corretos.

O **[!UICONTROL Fatigue rules summary]** relatório pode ser acessado a partir do **[!UICONTROL Reports]** botão, no canto superior direito de cada programa, campanha e mensagem.

![](assets/fatigue27.png)

Na parte esquerda da tela, você pode filtrar os dados do relatório na data de contato das entregas. Por padrão, o período selecionado começa 15 dias antes da data atual e termina 15 dias depois. Você também pode filtrar por uma regra de fadiga específica.

O gráfico setorial exibe as seguintes informações sobre o período selecionado:

* **[!UICONTROL Total targeted]**: o alvo total antes da preparação da mensagem
* **[!UICONTROL Excluded]**: o número total de exclusões devido à aplicação da regra de fadiga
* **[!UICONTROL Other exclusions]**: o número total de exclusões devido a outras regras de tipologia
* **[!UICONTROL To deliver]**: o número total de mensagens a entregar após a preparação da mensagem ( **[!UICONTROL To deliver]** = **[!UICONTROL Total targeted]** - **[!UICONTROL Excluded]** - **[!UICONTROL Other exclusions]** )

À direita do gráfico, você encontrará o número de exclusões, detalhadas pela regra de fadiga.

A tabela inferior exibe todas as entregas dentro do período selecionado. Para cada entrega, você pode ver as regras de fadiga que se aplicaram e as exclusões correspondentes. As entregas que não têm uma data de contato também são exibidas na tabela.

* **[!UICONTROL 0]** significa que a regra da fadiga se aplica, mas não houve exclusão.
* **[!UICONTROL -N]** significa que ocorreram N exclusões.
* um campo vazio significa que a regra de fadiga não se aplica.

>[!NOTE]
>
>Os dados exibidos não são contextuais ao programa, mensagem ou campanha de onde você acessa o relatório. Este relatório exibe todas as regras de fadiga e entregas para todas as unidades organizacionais. Isso permite obter uma exibição global de todas as entregas para entender como suas campanhas são influenciadas por outras pessoas.

## Exemplos {#examples}

Há muitas possibilidades em termos de implementação da gestão da fadiga. Estes são alguns exemplos do que você pode fazer:

* Crie uma regra de fadiga usando um limite **** constante que se aplica a **todos os canais**:

   Digamos que você crie uma regra multicanal, com um limite constante de 3 durante um período deslizante de 7 dias.

   Na semana passada, seus perfis premium receberam um email promocional e um email transacional de remarketing. Você também agendou um SMS que será enviado na semana que vem. Hoje, você decide enviar uma notificação por push direcionando todos os seus perfis. Os perfis premium serão excluídos do push de hoje porque seu número máximo de mensagens em um período de 2 semanas já foi atingido.

   ![](assets/fatigue23.png)

* Crie uma regra de fadiga usando um limite **de** variável com base em um campo **de** perfil:

   Você estendeu o recurso de perfis com um campo "Limite de comunicação" para definir um limite diferente para cada perfil. Na regra de fadiga, defina um limite de variável com base nesse campo e selecione um período deslizante de 2 dias. Vamos dar dois exemplos de perfis: John tem um limite de comunicação de 1 e David tem um limite de 2. Ambos já receberam um email com newsletter ontem. Você decide enviar outro email para eles hoje. Só o David o receberá, porque o John foi excluído do alvo.

   ![](assets/fatigue24.png)

* Crie uma regra de fadiga usando uma fórmula **de cálculo de** limite:

   Você deseja alterar o limite de acordo com a idade de seus perfis. Se um perfil estiver abaixo de 40, defina um limite de 4 e para perfis mais antigos, um limite de 2. Em vez de definir esse limite para cada perfil com um campo estendido, você pode criar uma fórmula diretamente na regra de fadiga para calcular o limite de acordo com a idade dos perfis. Em nosso exemplo, a fórmula seria **[!UICONTROL Iif (@age<40, 4, 2)]**.

   ![](assets/fatigue25.png)

   >[!NOTE]
   >
   >Esta seção também inclui um exemplo passo a passo de uma regra de fadiga usando uma fórmula de cálculo de limite.

* Crie uma regra de fadiga que **refina o limite** em perfis e entregas:

   Você estendeu o recurso de perfis com um campo "Pontuação" e também estendeu o recurso de entregas com um campo "Tipo". Você deseja definir um limite constante de 3, mas deseja excluir da contagem todas as entregas do tipo 'Alerta' ou 'Sexta-feira negra' e todos os perfis com uma pontuação maior que 10. Quando a regra for executada, contará, entre as entregas passadas e programadas, todas as entregas que não sejam do tipo 'Alerta' ou 'Sexta-feira negra' enviadas para perfis cuja pontuação seja menor que 10.

   ![](assets/fatigue26.png)

Este é um exemplo passo a passo de uma regra de fadiga usando uma fórmula de cálculo de limite.

Nesse caso de uso, queremos criar uma regra de tipologia para impedir a entrega de mais de 2 mensagens por semana para perfis premium e 2 mensagens por semana para perfis padrão.

Para identificar clientes e clientes potenciais, estendemos o recurso de perfis com o **[!UICONTROL Status]** campo, que contém 0 para perfis premium e 1 para perfis padrão.

Para criar a regra, aplique as seguintes etapas:

1. Create a new **Fatigue** type typology rule.
1. Na **[!UICONTROL Threshold]** seção, queremos criar uma fórmula para calcular o limite dependendo de cada perfil. Selecione o **[!UICONTROL Depends on the recipient]** valor no **[!UICONTROL Threshold type]** campo e clique no ícone no segundo botão à direita do **[!UICONTROL Threshold computation formula]** campo.

   ![](assets/fatigue7.png)

1. Na **[!UICONTROL List of functions]** seção, clique duas vezes na função **Iif** no **[!UICONTROL Others]** nó.

   ![](assets/fatigue8.png)

1. Em seguida, selecione o **Status** do perfil na **[!UICONTROL Available fields]** seção.

   ![](assets/fatigue9.png)

1. Insira os valores desejados para criar a seguinte fórmula: **Iif(@status=0,2,4)**

   ![](assets/fatigue10.png)

   Essa fórmula permite atribuir o valor 2 se o status for igual a 0, e o valor 4 para todos os outros status.

1. Click **[!UICONTROL Confirm]** to approve the formula.
1. Indique a regra **[!UICONTROL Sliding period]** em que será aplicada: 7 dias, neste caso, para limitar as entregas tomadas em consideração a um período de 2 semanas.

   ![](assets/fatigue11.png)

1. Agora, vincule a regra que você acabou de criar a uma tipologia para aplicá-la às entregas. Para fazer isso, selecione a **[!UICONTROL Typologies]** guia, clique **[!UICONTROL Create element]** e selecione a tipologia usada para as entregas.

   ![](assets/fatigue12.png)

1. Salve a regra para aprovar a criação.

A regra será aplicada a todas as entregas com base na tipologia.
