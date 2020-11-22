---
solution: Campaign Standard
product: campaign
title: Recursos preditivos de engajamento do usuário
description: Saiba como usar tempo de envio preditivo e pontuação de engajamento.
audience: sending
content-type: reference
topic-tags: ai-powered-emails
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '1061'
ht-degree: 100%

---


# Otimizar o design e o delivery com emails alimentados por IA{#journey-ai}

## Comece a usar emails alimentados por IA{#journey-ai-ovv}

Com o Campaign, você pode otimizar o design e o delivery de jornadas de clientes para prever a preferência de engajamento de cada pessoa. Com a tecnologia Journey AI, o Adobe Campaign pode analisar e prever taxas abertas, tempos de envio ideais e probabilidade de churn com base em métricas históricas de engajamento.

**Modelos de aprendizado de máquina**

O Adobe Campaign Standard oferece dois novos modelos de aprendizado de máquina: **Otimizações preditivas de tempo de envio** e **Pontuação preditiva de engajamento**. Juntos, esses dois modelos são chamados de Journey AI, uma classe de modelos de aprendizado de máquina específicos para projetar e fornecer melhores jornadas ao cliente.

* **Otimização preditiva do tempo de envio**: A otimização preditiva do tempo de envio prevê qual é o melhor tempo de envio para cada perfil de recipient para aberturas e cliques de email. As pontuações indicam o melhor horário de envio para cada dia da semana e qual o melhor dia para enviar a fim de obter melhores resultados para cada perfil de recipient.

* **Pontuação preditiva de engajamento**: A pontuação preditiva de engajamento prevê a probabilidade de um recipient se envolver com uma mensagem, bem como a probabilidade de opt out (cancelamento de inscrição) nos 7 dias seguintes ao envio do próximo email. As probabilidades são divididas em lotes de acordo com o risco específico de desvinculação, sendo médio ou baixo. Nesse percurso, o modelo também fornece a classificação do percentual de risco para que os clientes entendam a classificação de um determinado cliente em relação aos outros.

>[!CAUTION]
>Esse recurso não está disponível para uso imediato como parte do produto. A implementação exige o engajamento da Adobe Consulting. Entre em contato com seu representante da Adobe para obter mais detalhes.
>
>O recurso exige o uso de um armazenamento do Azure que deve ser fornecido pelo cliente.

## Otimização preditiva do tempo de envio{#predictive-send-time}

### Otimizar cliques e aberturas{#about-predictive-send-time}

A otimização preditiva do tempo de envio prevê qual é o melhor momento de envio para aberturas e cliques no email para cada perfil de recipient. As pontuações indicam o melhor horário de envio para cada dia da semana e qual o melhor dia para enviar a fim de obter melhores resultados para cada perfil de recipient.

Há dois submodelos dentro do modelo de otimizações preditivas de tempo de envio:
* O tempo preditivo de envio para abrir é o melhor horário para o envio da comunicação ao cliente para maximizar as aberturas
* O tempo preditivo de envio para cliques é o melhor horário para o envio de uma comunicação ao cliente para maximizar os cliques

**Entrada do modelo**: Logs do delivery, logs de rastreamento e atributos de perfil (não PII)

**Saída do modelo**: Melhor horário para o envio de uma mensagem (para aberturas e cliques)


Detalhes da saída

* Calcule o melhor horário do dia para enviar um email nos 7 dias da semana com intervalos de 1 hora (por exemplo: 9h, 10h, 11h)
* O modelo indicará o melhor dia da semana e o melhor horário do dia
* Cada horário ideal é calculado duas vezes: uma vez para maximizar a taxa de abertura e outra para maximizar a taxa de cliques
* São administrados 16 campos (14 para os dias da semana e 2 para a semana inteira):
   * melhor horário para enviar um email para otimizar cliques na segunda-feira – valores entre 0 e 23
   * melhor horário para enviar um email para otimizar as aberturas na segunda-feira – valores entre 0 e 23
   * melhor horário para enviar um email para otimizar cliques na terça-feira – valores entre 0 e 23
   * ...
   * melhor horário para enviar um email para otimizar cliques no domingo – valores entre 0 e 23
   * melhor horário para enviar um email para otimizar as aberturas no domingo – valores entre 0 e 23
   * ...
   * melhor dia para enviar um email para otimizar as aberturas da semana inteira – de segunda a domingo
   * o melhor horário para enviar um email para otimizar as aberturas da semana inteira – valores entre 0 e 23

>[!NOTE]
>
>Esses recursos preditivos se aplicam apenas para deliveries de email.
>
>O modelo precisa de pelo menos um mês de dados para produzir resultados significativos.


### Pontuações de perfil de acesso{#access-predictive-send-time-scores}

Depois de implementados no Campaign, os recursos de aprendizado de máquina enriquecem os dados dos perfis com novas guias e as melhores pontuações de abertura/clique. As métricas são computadas pelo Journey AI e são trazidas para o Campaign utilizando workflows técnicos.

Para acessar essas métricas, é necessário:

1. Abrir um perfil e clicar no botão Editar.

1. Clicar na guia **Enviar pontuação de tempo por clique** ou **Enviar pontuação de tempo ao abrir**.

Por padrão, as pontuações do perfil oferecerão o melhor horário do dia para cada dia da semana e o melhor horário geral da semana.

![](assets/do-not-localize/SendTimeScore.png)

### Enviar mensagens no melhor momento{#use-predictive-send-time}

Para que os emails sejam enviados no horário ideal por perfil, o delivery deve ser programado usando a opção **[!UICONTROL Send at a custom date defined by a formula]**.
Saiba como calcular a data de envio [nesta seção](../../sending/using/computing-the-sending-date.md).

A fórmula precisa ser preenchida com o melhor horário específico do dia em que o delivery for lançado.

![](assets/do-not-localize/ComputeSendingDate.png)

Exemplo de fórmula:

```
AddHours([currentDelivery/scheduling/@contactDate], 
[cusSendTimeScoreByClickprofile_link/@EMAIL_BEST_TIME_TO_CLICK_WEDNESDAY])
```

![](assets/do-not-localize/SendingDateFormula.png)

>[!NOTE]
>
>O modelo de dados pode ser diferente dependendo da implementação.



## Pontuação preditiva de engajamento {#predictive-scoring}

A pontuação preditiva de engajamento permite:

* **Selecionar um público**: ao usar a atividade de query, você pode selecionar o público que vai se engajar com uma mensagem específica
* **Excluir um público**: usando a atividade de query, você pode remover o público para cancelar a inscrição
* **Personalizar**: personalizar mensagem de acordo com o nível de engajamento (usuários altamente engajados receberão uma mensagem diferente daqueles não engajados)

Este modelo usa várias pontuações para indicar:

* **Pontuação de engajamento ao abrir/Pontuação de engajamento ao clicar**: esse valor corresponde à probabilidade de um assinante se engajar com uma mensagem específica (abrir ou clicar). Os valores variam de 0,0 a 1,0.
* **Probabilidade de cancelamento de inscrição**: esse valor corresponde à probabilidade do recipient cancelar a inscrição do canal de email considerando um email aberto. Os valores variam de 0,0 a 1,0.
* **Nível de retenção**: esse valor classifica os usuários em três níveis: baixo, médio e alto. O alto tem mais probabilidade de adesão à marca, enquanto o baixo provavelmente cancelará a assinatura.
* **Classificação de percentual de retenção**: Classificação do perfil em termos de probabilidade de cancelamento de assinatura. Os valores variam de 0,0 a 1,0. Por exemplo, se a classificação de porcentagem de retenção for de 0,953, esse recipient terá maior probabilidade de permanecer com a marca e menos probabilidade de cancelar a assinatura do que 95,3% de todos os recipient.

>[!NOTE]
>
>Esses recursos preditivos se aplicam apenas para deliveries de email.
>
>O modelo precisa de pelo menos um mês de dados para produzir resultados significativos.


**Entrada do modelo**: Logs do delivery, logs de rastreamento e atributos específicos do perfil

**Saída do modelo**: Um atributo de perfil que descreve a pontuação e a categoria do perfil


### Usar a pontuação de engajamento para o canal de email

Para acessar essas métricas, é necessário:

1. Abrir um perfil e clicar no botão Editar.

1. Clicar na guia **Pontuações de engajamento para canal de email**.

Ao usar uma atividade de query em um workflow, a pontuação pode ser usada para otimizar o público.

Por exemplo, com os critérios **Nível de retenção**:

![](assets/do-not-localize/predictive_score_query.png)























