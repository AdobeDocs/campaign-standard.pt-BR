---
title: Solução de problemas de entrega no Adobe Campaign Standard
description: Saiba o que fazer ao enfrentar problemas de entrega com o Adobe Campaign Standard.
page-status-flag: never-activated
uuid: 286fceee-65a9-4cb9-b205-9ce5d024675c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sheduling-messages
discoiquuid: 9c7fd670-bba9-4f3c-8cb1-87397a1acd27
context-tags: delivery,schedule,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 87168dca3604073d8a540c579448ab65f07cd976

---


# Solução de problemas{#troubleshooting}

Você está enfrentando um problema de entrega? Você pode encontrar a solução aqui.

## Mesma mensagem de erro para um ISP {#same-error-for-an-isp}

**Por que recebo sempre a mesma mensagem de erro para um provedor de serviços específico?**

Se você receber sempre a mesma mensagem de erro para um ISP, seu email ou IP pode ter sido detectado como defeituoso pelo ISP. Execute as seguintes recomendações:
* Verifique se você recebe uma grande porcentagem de falhas vinculadas a endereços de email inexistentes (falhas desconhecidas **do** usuário).
* Atualize seus formulários de subscrição para detectar quaisquer erros nos nomes de domínio inseridos (por exemplo: gmaul.com ou yaho.com).
* Se você notar erros que indicam que suas mensagens são declaradas como spam, ou que suas mensagens estão constantemente bloqueadas, tente excluir os recipient que não abriram ou clicaram em uma de suas mensagens nos últimos 12 meses a partir do público alvo.

Se o problema persistir, entre em contato com os serviços comerciais ou de entrega ou com o suporte ao Adobe Campaign.

## Listas negras versus quarentenas {#blacklisting-versus-quarantine}

* **Qual é a diferença entre um endereço de email incluído na blacklist e um endereço de email em quarentena?**

   * O status **[!UICONTROL Blacklisted]** é resultado de um ciclo de feedback (quando uma pessoa reporta uma mensagem como spam).

   * O status **[!UICONTROL Quarantined]** é resultado de um salto suave ou forte.
   For more on this, see this [section](../../sending/using/understanding-quarantine-management.md#quarantine-vs-blacklisting).

* **O que significam os diferentes motivos de erro de quarentena?**

   Aqui estão 10 possíveis motivos: não definido, usuário desconhecido, domínio inválido, endereço incluído na blacklist, recusado, erro ignorado, inacessível, conta desativada, caixa de correio cheia, não conectado.

   Para obter mais informações, consulte [Entendendo o gerenciamento](../../sending/using/understanding-quarantine-management.md)de quarentenas.

## Sem lista negra {#unblacklisting}

* **Um dos meus recipient foi incluído na blacklist por engano. Como faço para desfazer a lista negra deles para que eu possa start de enviar mensagens para eles novamente?**

   * Vá para **[!UICONTROL Administration > Channels > Quarantines > Addresses]**.
   * Nos detalhes do registro correspondente, defina o valor do **[!UICONTROL Status]** campo como **[!UICONTROL Valid]**.
   * Salve o registro.

* **Como posso descobrir se um dos meus IPs é incluído na blacklist? Como faço para desfazer a lista negra de meus IPs?**

   Para verificar se seu endereço IP é incluído na blacklist, você pode usar vários sites para verificá-lo:
   * https://mxtoolbox.com/
   * https://whatismyipaddress.com/blacklist-check
   * https://www.blacklistalert.org/
   Geralmente, o resultado da verificação de endereço IP retornará uma lista que contém detalhes da lista negra e também o nome do site que incluído na blacklist o endereço IP.

   Ao clicar no link correspondente, você pode acessar os detalhes do site.

   Em seguida, você pode solicitar que seu site seja excluído do site que incluído na blacklist o endereço IP.

   >[!NOTE]
   >
   >O processo de exclusão pode variar dependendo do site. Alguns sites exigem que você crie uma conta, enquanto outros precisam apenas que você forneça o endereço IP.
