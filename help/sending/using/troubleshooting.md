---
solution: Campaign Standard
product: campaign
title: Solução de problemas de capacidade de entrega no Adobe Campaign Standard
description: Saiba o que fazer quando enfrentar problemas de capacidade de entrega com o Adobe Campaign Standard.
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: Deliverability
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: fb9a6218bb754f803affde1fdf6c6fc01570126f
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 59%

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

* **Qual é a diferença entre um endereço de email em lista de bloqueios e um email em quarentena?**

   * O status **[!UICONTROL On denylist]** é resultado de um [ciclo de feedback](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#feedback-loops) (quando uma pessoa relata uma mensagem como spam).

   * O status **[!UICONTROL Quarantined]** é resultado de um salto suave ou forte.
   Para obter mais informações, consulte esta [seção](../../sending/using/understanding-quarantine-management.md#quarantine-vs-denylist).

* **O que significam os diferentes motivos de erro de quarentena?**

   Aqui estão 10 possíveis motivos: não definido, usuário desconhecido, domínio inválido, endereço em lista de bloqueios, recusado, erro ignorado, inacessível, conta desativada, caixa de correio cheia, não conectado.

   Para obter mais informações, consulte [Entendendo o gerenciamento da quarentena](../../sending/using/understanding-quarantine-management.md).

## Remoção da lista de bloqueios {#removing-from-denylist}

* **Um dos meus recipients foi adicionado à lista de bloqueios por engano. Como faço para removê-los da  de lista de bloqueios para que eu possa iniciar o envio de mensagens para eles novamente?**

   * Vá para **[!UICONTROL Administration > Channels > Quarantines > Addresses]**.
   * Nos detalhes do registro correspondente, defina o valor do campo **[!UICONTROL Status]** como **[!UICONTROL Valid]**.
   * Salve o registro.

* **Como é possível descobrir se um dos IPs está em lista de bloqueios? Como remover meus IPs de uma lista de bloqueios?**

   Para verificar se o endereço IP está em lista de bloqueios, você pode usar vários sites para verificá-lo, como:
   * [MX Toolbox](https://mxtoolbox.com/)
   * [Qual é meu endereço IP](https://whatismyipaddress.com)

   Geralmente, o resultado da verificação do endereço IP retornará uma lista que contém os detalhes da lista de bloqueios e também o nome do site que bloqueou o endereço IP.

   Ao clicar no link correspondente, é possível acessar os detalhes do site.

   É possível solicitar que seu site seja excluído da lista de bloqueios do site que incluiu o endereço IP à lista de bloqueios.

   >[!NOTE]
   >
   >O processo de exclusão pode variar dependendo do site. Alguns sites exigem a criação de uma conta, enquanto outros precisam apenas do endereço IP.
