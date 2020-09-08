---
title: Solução de problemas de entrega no Adobe Campaign Standard
description: Saiba o que fazer ao enfrentar problemas de entrega com a Adobe Campaign Standard.
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
source-git-commit: 1f15e28bed22e3defb29f16875fcf4c07f4af5a3
workflow-type: tm+mt
source-wordcount: '452'
ht-degree: 55%

---


# Solução de problemas{#troubleshooting}

Ocorreu algum problema com a capacidade de entrega? Encontre a solução aqui.

## Mesma mensagem de erro para um ISP {#same-error-for-an-isp}

**Por que recebo sempre a mesma mensagem de erro para um provedor de serviços específico?**

Ao receber sempre a mesma mensagem de erro para um ISP, o email ou IP pode ter sido detectado como defeituoso pelo ISP. Siga as seguintes recomendações:
* Verifique se você recebeu uma grande porcentagem de falhas vinculadas a endereços de email inexistentes (falhas **desconhecidas do usuário**).
* Atualize os formulários de subscrição para detectar qualquer erro nos nomes de domínio inseridos (por exemplo: gmaul.com ou yaho.com).
* Se ocorrer erros que indicam que as mensagens são declaradas como spam ou que estão constantemente bloqueadas, tente excluir os destinatários que não abriram ou clicaram em uma das mensagens nos últimos 12 meses a partir do público-alvo.

Se o problema persistir, entre em contato com os serviços comerciais ou de entrega ou com o suporte da Adobe Campaign.

##  Lista de bloqueios quarentena {#denylist-versus-quarantine}

* **Qual é a diferença entre um endereço de email incluir na lista de bloqueios e um endereço de email em quarentena?**

   * O status **[!UICONTROL Denylisted]** é resultado de um ciclo de feedback (quando uma pessoa reporta uma mensagem como spam).

   * O status **[!UICONTROL Quarantined]** é resultado de um salto suave ou forte.
   Para obter mais informações, consulte esta [seção](../../sending/using/understanding-quarantine-management.md#quarantine-vs-block-list).

* **O que significam os diferentes motivos de erro de quarentena?**

   Aqui estão 10 possíveis motivos: não definido, usuário desconhecido, domínio inválido, endereço incluir na lista de bloqueios, recusado, erro ignorado, inacessível, conta desativada, caixa de correio cheia, não conectado.

   Para obter mais informações, consulte [Entendendo o gerenciamento da quarentena](../../sending/using/understanding-quarantine-management.md).

## Remoção de lista de bloqueios {#removing-from-denylist}

* **Um dos meus recipient foi incluir na lista de bloqueios por engano. How do I remove them from the denylist so that I can start sending them messages again?**

   * Vá para **[!UICONTROL Administration > Channels > Quarantines > Addresses]**.
   * Nos detalhes do registro correspondente, defina o valor do campo **[!UICONTROL Status]** como **[!UICONTROL Valid]**.
   * Salve o registro.

* **Como posso descobrir se um dos meus IPs está incluir na lista de bloqueios? Como remover meus IPs de uma lista de bloqueios?**

   Para verificar se seu endereço IP está incluir na lista de bloqueios, você pode usar vários sites para verificá-lo, como:
   * [Caixa de ferramentas MX](https://mxtoolbox.com/)
   * [Qual é o meu endereço IP](https://whatismyipaddress.com)

   Geralmente, o resultado da verificação de endereço IP retornará uma lista que contém detalhes da lista de bloqueios e também o nome do site que bloqueou o endereço IP.

   Ao clicar no link correspondente, é possível acessar os detalhes do site.

   Em seguida, você pode solicitar que seu site seja excluído do site que adicionou o endereço IP à sua lista de bloqueios.

   >[!NOTE]
   >
   >O processo de exclusão pode variar dependendo do site. Alguns sites exigem a criação de uma conta, enquanto outros precisam apenas do endereço IP.
