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
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 16%

---

# Regras de controle {#control-rules}

As regras de controle permitem verificar a validade e a qualidade das mensagens antes de serem enviadas, como exibição de caracteres, tamanho da mensagem SMS, formato de endereço etc.

>[!NOTE]
>
>Por motivos de segurança, as regras de controle são somente leitura e não podem ser modificadas.

## Regras de controle padrão {#default-control-rules}

Um conjunto de regras padrão garante os controles padrão. A tabela abaixo fornece informações sobre essas regras, bem como seu canal e [fases de execução](#control-rules-execution-phases).

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
| **[!UICONTROL Check unsubscription link]** | Email | No início da personalização | Verifica a presença de pelo menos um URL de cancelamento de subscrição (opt-out) em cada conteúdo (HTML e Text). |
| **[!UICONTROL Check URL labels]** | Email | No início da personalização | Verifica se cada URL de rastreamento tem um rótulo. |
| **[!UICONTROL Check URLs]** | Email | No início da personalização | Verifica as URLs de rastreamento (presença do caractere &quot;&amp;&quot;). |

## Fases de execução das regras de controle {#control-rules-execution-phases}

As regras de controle podem ser aplicadas em diferentes fases do ciclo de vida do delivery:

* **No início do direcionamento**: a regra de controle pode ser aplicada nesta fase para que a etapa de personalização não seja executada em caso de erro.

* **Após o direcionamento**: a execução após o direcionamento permite saber o volume do público-alvo para aplicar a regra de controle.

  Por exemplo, a variável **Verificar tamanho da prova** control rule applies after the targeting stage: essa regra impede a preparação da personalização da mensagem se houver muitos recipients de prova.

* **No início da personalização**: se aplica quando a verificação está relacionada à aprovação da personalização da mensagem. A personalização da mensagem é realizada durante a fase de análise.

* **No final da análise**: quando uma verificação requer que a personalização da mensagem seja concluída.
