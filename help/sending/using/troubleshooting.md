---
solution: Campaign Standard
product: campaign
title: Solução de problemas de entrega no Adobe Campaign Standard
description: Saiba o que fazer ao enfrentar problemas de entrega com a Adobe Campaign Standard.
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '459'
ht-degree: 64%

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

## Lista de bloqueios × quarentena {#denylist-versus-quarantine}

* **Qual é a diferença entre um endereço de email em lista de bloqueios e um endereço de email em quarentena?**

   * O status **[!UICONTROL On denylist]** é resultado de um ciclo de feedback (quando uma pessoa reporta uma mensagem como spam).

   * O status **[!UICONTROL Quarantined]** é resultado de um salto suave ou forte.
   Para obter mais informações, consulte esta [seção](../../sending/using/understanding-quarantine-management.md#quarantine-vs-denylist).

* **O que significam os diferentes motivos de erro de quarentena?**

   Aqui estão 10 possíveis motivos: não definido, usuário desconhecido, domínio inválido, endereço na lista de bloqueios, recusado, erro ignorado, inacessível, conta desativada, caixa de correio cheia, não conectado.

   Para obter mais informações, consulte [Entendendo o gerenciamento da quarentena](../../sending/using/understanding-quarantine-management.md).

## Remoção da lista de bloqueios {#removing-from-denylist}

* **Um dos meus recipient foi adicionado à lista de bloqueios por engano. Como removê-los da lista de bloqueios para que eu possa start de enviar mensagens novamente?**

   * Vá para **[!UICONTROL Administration > Channels > Quarantines > Addresses]**.
   * Nos detalhes do registro correspondente, defina o valor do campo **[!UICONTROL Status]** como **[!UICONTROL Valid]**.
   * Salve o registro.

* **Como posso descobrir se um dos meus IPs está na lista de bloqueios? Como remover meus IPs de uma lista de bloqueios?**

   Para verificar se o endereço IP está na lista de bloqueios, use vários sites para verificá-lo, como:
   * [MX Toolbox](https://mxtoolbox.com/)
   * [Qual é meu endereço IP](https://whatismyipaddress.com)

   Geralmente, o resultado da verificação de endereço IP retornará uma lista que contém detalhes da lista de bloqueios e também o nome do site que bloqueou o endereço IP.

   Ao clicar no link correspondente, é possível acessar os detalhes do site.

   É possível solicitar que seu site seja excluído da lista de bloqueios do site que incluiu o endereço IP à lista de bloqueios.

   >[!NOTE]
   >
   >O processo de exclusão pode variar dependendo do site. Alguns sites exigem a criação de uma conta, enquanto outros precisam apenas do endereço IP.
