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
source-git-commit: 33d4704d664a809073790e47ab6bb84e9c2b07d5

---


# Solução de problemas{#troubleshooting}

Você está enfrentando um problema de entrega? Você pode encontrar a solução aqui...

**Por que recebo sempre a mesma mensagem de erro para um provedor de serviços específico?**

Se você receber sempre a mesma mensagem de erro para um ISP, seu email ou IP pode ter sido detectado como defeituoso pelo ISP. Execute as seguintes recomendações:
* Verifique se você recebe uma grande porcentagem de falhas vinculadas a endereços de email inexistentes (falhas desconhecidas **do** usuário).
* Atualize seus formulários de assinatura para detectar quaisquer erros nos nomes de domínio inseridos (por exemplo: gmaul.com ou yaho.com).
* Se você notar erros que indicam que suas mensagens são declaradas como spam, ou que suas mensagens estão constantemente bloqueadas, tente excluir os destinatários que não abriram ou clicaram em uma de suas mensagens nos últimos 12 meses do destino.

Se o problema persistir, entre em contato com os serviços comerciais ou de entrega ou com o suporte do Adobe Campaign.

**Qual é a diferença entre um endereço de email da lista negra e um endereço de email em quarentena?**

O status **[!UICONTROL Blacklisted]**é resultado de um ciclo de feedback (quando uma pessoa reporta uma mensagem como spam).

O status **[!UICONTROL Quarantined]**é resultado de um salto suave ou forte.

**O que significam os diferentes motivos de erro de quarentena?**

Aqui estão 10 possíveis motivos: não definido, usuário desconhecido, domínio inválido, endereço da lista negra, recusado, erro ignorado, inacessível, conta desativada, caixa de correio cheia, não conectado.

Para obter mais informações, consulte [Entendendo o gerenciamento](../../sending/using/understanding-quarantine-management.md)de quarentena.

**Um dos meus destinatários estava na lista negra por engano. Como faço para desfazer a lista negra deles para começar a enviar mensagens novamente?**

* Vá para **[!UICONTROL Administration > Channels > Quarantines > Addresses]**.
* Nos detalhes do registro correspondente, defina o valor do **[!UICONTROL Status]**campo como**[!UICONTROL Valid]**.
* Salve o registro.

**Como posso descobrir se um dos meus IPs está na lista negra? Como faço para cancelar a lista de meus IPs?**

Para verificar se seu endereço IP está na lista negra, você pode usar vários sites para verificá-lo:
* https://mxtoolbox.com/
* https://whatismyipaddress.com/blacklist-check
* https://www.blacklistalert.org/

Geralmente, o resultado da verificação de endereço IP retornará uma lista que contém detalhes da lista negra e também o nome do site que lista negra do endereço IP.

Ao clicar no link, você pode acessar os detalhes do site.

Em seguida, você pode solicitar que seu site seja excluído do site que lista negra o endereço IP.

O processo de exclusão pode variar dependendo do site. Alguns sites exigem que você crie uma conta, enquanto outros precisam apenas que você forneça o endereço IP.
