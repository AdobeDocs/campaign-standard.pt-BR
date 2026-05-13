---
title: Regras de controle
description: Saiba como reforçar a verificação de qualidade de suas mensagens com regras de controle.
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
feature: Typology Rules
role: User
level: Intermediate
exl-id: 6461c128-1e42-4685-88f8-507244147e6f
TQID: https://experienceleague.adobe.com/lpPFofV3IPl7zmbaR4TOuyCcVqgjwI3maxr-jKzkd0Q
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: d095671a-1355-40aa-8b5f-06c33c68080bid: e0eb8757-182f-49f3-94a4-1587d16f5094id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 449
ht-degree: 17%

---

# Regras de controle {#control-rules}

As regras de controle permitem verificar a validade e a qualidade das mensagens antes de serem enviadas, como exibição de caracteres, tamanho da mensagem SMS, formato de endereço etc.

>[!NOTE]
>
>Por motivos de segurança, as regras de controle são somente leitura e não podem ser modificadas.

## Regras de controle padrão {#default-control-rules}

Um conjunto de regras padrão garante os controles padrão. A tabela abaixo fornece informações sobre essas regras, bem como seu canal relacionado e [fases de execução](#control-rules-execution-phases).

| Rótulo | Canal | Fase de execução | Descrição |
|---------|----------|---------|---------|
| **[!UICONTROL A/B Test]** | Email | No início da personalização | Extrai a população de teste para um delivery com um teste A/B. |
| **[!UICONTROL Check delivery size]** | Todos | Após o direcionamento | Verifica o tamanho das mensagens. |
| **[!UICONTROL Check email content is not empty]** | Email | Após o direcionamento | Gera um erro se o conteúdo da mensagem estiver vazio. |
| **[!UICONTROL Check In-App content for broadcast template]** | No aplicativo | No início da personalização | Verifica se os acionadores/conteúdo no aplicativo não estão vazios para o modelo de transmissão. |
| **[!UICONTROL Check In-App content for profile template]** | No aplicativo | No início da personalização | Verifica se os acionadores/conteúdo no aplicativo não estão vazios para o modelo de perfil. |
| **[!UICONTROL Check In-App content for subscriber template]** | No aplicativo | No início da personalização | Verifica se os acionadores/conteúdo no aplicativo não estão vazios para o modelo do assinante. |
| **[!UICONTROL Check proof size]** | Todos | Após o direcionamento | Gera uma mensagem de erro se a população do target de prova exceder 100 destinatários. |
| **[!UICONTROL Check social network sharing link]** | Email | No início da personalização | Verifica a presença de um link para uma mirror page ao incluir um link de compartilhamento de rede social (ViralLinks) no conteúdo. |
| **[!UICONTROL Check subject]** | Email | No início da personalização | Verifica se o assunto e o endereço do remetente não contêm caracteres especiais que podem causar problemas em determinados agentes de transferência de email e verifica se o assunto da mensagem foi concluído. |
| **[!UICONTROL Check unsubscription link]** | Email | No início da personalização | Verifica a presença de pelo menos um URL de cancelamento de subscrição (recusa) em cada conteúdo (HTML e Text). |
| **[!UICONTROL Check URL labels]** | Email | No início da personalização | Verifica se cada URL de rastreamento tem um rótulo. |
| **[!UICONTROL Check URLs]** | Email | No início da personalização | Verifica as URLs de rastreamento (presença do caractere &quot;&amp;&quot;). |

## Fases de execução das regras de controle {#control-rules-execution-phases}

As regras de controle podem ser aplicadas em diferentes fases do ciclo de vida do delivery:

* **No início do direcionamento**: a regra de controle pode ser aplicada nesta fase para que a etapa de personalização não seja executada em caso de erro.

* **Após o direcionamento**: executar após o direcionamento permite que você saiba o volume do destino para aplicar a regra de controle.

  Por exemplo, a regra de controle **Verificar tamanho da prova** se aplica após o estágio de direcionamento: essa regra impede a preparação da personalização da mensagem se houver muitos recipients de prova.

* **No início da personalização**: aplica-se quando a verificação está relacionada à aprovação da personalização da mensagem. A personalização da mensagem é realizada durante a fase de análise.

* **No final da análise**: quando uma verificação exige a personalização da mensagem para ser concluída.
