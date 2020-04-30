---
title: Usar a integração do Microsoft Dynamics 365
description: Saiba como usar o Microsoft Dynamics 365 com integração com o Campaign Standard
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: de048c06ea2af0c988e97a37ebf945906069935e

---


# Usar a integração do Microsoft Dynamics 365

Há vários trabalhos que essa integração executa:

* **Sincronização** de contato: Os contatos são enviados do Dynamics 365 para a Campanha (observação: sincronização unidirecional).
* **Sincronização** de entidade personalizada: Os registros de entidade personalizados são enviados do Dynamics 365 para a Campanha (observe a sincronização unidirecional).  Consulte a página sobre entidades personalizadas para obter mais informações.
* **Exibição** do Evento: Determinados eventos de marketing por email são enviados da Campanha para o Dynamics 365. Consulte a Nota abaixo.
* **Exclusão** de contato: O perfil de Campanha é adicionado à fila de exclusão relacionada à privacidade quando o Contato correspondente é excluído no Dynamics 365.
* **Sincronização** de opção: As opções de não participação são sincronizadas entre o Dynamics 365 e a Campanha, dependendo da configuração selecionada pelo cliente durante a integração (ou seja, o Dynamics 365 para sincronização de Campanha, Campanha para sincronização do Dynamics 365 ou sincronização bidirecional).
* **Logon único (SSO)**: Seus detalhes de integração no Unifi podem ser acessados diretamente da Campanha, usando a autenticação do Adobe IMS.

>[!NOTE]
>
>Para exibição **de** Eventos, um máximo de 10 mil eventos será recuperado toda vez que o trabalho de saída for executado no Unifi.

## Experiência de usuário padrão Adobe Campaign

Quando um contato for criado novo ou modificado no Dynamics 365, ele será sincronizado para a Campanha depois que a sincronização Contatos for executada.  Esses contatos estarão visíveis na tela Perfis na Campanha e poderão ser direcionados para campanhas de marketing.  Consulte a tela Perfis abaixo.

![](assets/MSdynamicsACS-usage1.png)

Quando um contato é excluído no Dynamics 365, o perfil correspondente na Campanha é adicionado à fila de exclusão do serviço de privacidade na tela Solicitação de privacidade na Campanha.  Para obter mais detalhes sobre como executar solicitações de exclusão de pessoa de dados conforme necessário para cumprir as leis de privacidade de dados aplicáveis na Campanha, consulte Como executar solicitações de exclusão legalmente obrigatórias no Adobe Campaign Standard.

![](assets/MSdynamicsACS-usage2.png)

É importante observar que, se o processo de 2 etapas estiver ativado na tela de propriedades, será necessário confirmar manualmente a exclusão de cada registro na tela de privacidade antes que eles sejam finalmente excluídos.  Consulte a tela de processo de 2 etapas abaixo:

![](assets/MSdynamicsACS-usage3.png)

Quando um atributo de opção de não participação/lista negra é modificado na Campanha, ele será refletido no Dynamics 365 se você tiver selecionado a configuração Campanha para dinâmica 365 ou opção de não participação bidirecional e se você tiver esse atributo específico mapeado corretamente.

Para acessar os detalhes de integração por meio do logon único, vá para o menu Navegação de Campanha e clique em Administração > Integração do Microsoft Dynamics 365.

![](assets/sso_d365_admin_panel.png)

Esta página contém links para a documentação sobre integração e diretrizes sobre como usar os recursos de acordo com suas possíveis obrigações legais. Clique no ícone do globo, que automaticamente direcionará e fará logon na sua instância Unifi, onde você poderá gerenciar seus detalhes de integração.

Você pode ver um vídeo dessa funcionalidade no vídeo abaixo.

>[!VIDEO](https://video.tv.adobe.com/v/29254)

>[!NOTE]
>
>Você precisará enviar um ticket para o Atendimento ao cliente da Adobe (diretamente ou por meio de seu contato da Adobe) para ter o sinalizador de recurso de logon único ativado na instância da Campanha.

![](assets/sso_screen.png)

>[!NOTE]
>
>Você não verá o ícone Integração do Microsoft Dynamics 365 no painel de administração pronto para usar.  Você (ou seu contato da Adobe) precisará enviar um ticket para ter esse sinalizador de recurso ativado para a instância da Campanha.
>
>Além disso, o Unifi precisará habilitar os usuários para acesso SSO antes que eles possam fazer logon por SSO com êxito a partir da Campanha.

## Experiência de usuário do Microsoft Dynamics 365

Para exibição de eventos, os seguintes eventos de marketing por email são enviados da Campanha para o Dynamics 365 e exibidos na visualização Linha do tempo do Dynamics 365 como atividades personalizadas:

* Adobe Campaign Email Send

* Adobe Campaign Email aberto

* Adobe Campaign Email URL Click

* Rejeição de e-mail Adobe Campaign

Para visualização da Linha do tempo de um contato, navegue até a lista de contatos clicando no Hub de vendas no menu suspenso Dinâmicas 365.  Em seguida, clique em Contatos na barra de menus esquerda e selecione um contato.

>[!NOTE]
>
>O Adobe Campaign para o aplicativo Dynamics 365 no AppSource precisará ser instalado na instância do Dynamics 365 para visualização desses eventos.

Abaixo, você pode ver um instantâneo da tela Contato para &quot;Usuário dinâmico&quot;.  Na visualização Linha do tempo, você notará que o Usuário do Dynamics recebeu um email associado ao Nome da Campanha &quot;2019LoyaltyCamp&quot; e ao Nome do Delivery &quot;DM190&quot;.  O Usuário do Dynamics abriu o email e também clicou em um URL no email; ambas as ações criaram eventos que também são mostrados abaixo.  Se você olhar para o canto direito, verá o cartão do Assistente de relacionamento (RA); atualmente, ele contém uma tarefa para acompanhar o URL clicado.

![](assets/do-not-localize/MSdynamicsACS-usage4.png)

Consulte abaixo para obter um close-up da visualização da Linha do tempo para o usuário dinâmico.

![](assets/do-not-localize/MSdynamicsACS-usage5.png)

Abaixo está um close-up do cartão do Assistente de relacionamento (RA).  O aplicativo AppSource contém um fluxo de trabalho que observa um evento de clique no URL do Adobe Email.  Quando esse evento ocorre, ele cria uma tarefa e define uma data de vencimento.  Isso permite que a tarefa apareça no cartão RA, dando-lhe visibilidade adicional.  Há um fluxo de trabalho semelhante para eventos de rejeição por email da Adobe, adicionando uma tarefa para reconciliar o endereço de email inválido.  Esses workflows podem ser desativados na solução.

![](assets/do-not-localize/MSdynamicsACS-usage6.png)

Se você clicar no assunto do evento send, verá um formulário semelhante ao abaixo.  Os formulários para eventos abertos e de rejeição são semelhantes.

![](assets/do-not-localize/mirror_page_url_send.png)

O formulário para eventos de cliques em url de email adiciona um atributo adicional para o URL clicado:

![](assets/do-not-localize/mirror_page_url_click.png)

Veja a seguir uma lista dos atributos e uma descrição:

* Assunto: Objeto do evento; composto pela ID de Campanha e pela ID de Delivery do delivery de email

* Proprietário: O usuário do aplicativo criado nas etapas pós-provisionamento

* Relativamente a: O nome do Contato

* Nome da Campanha: A ID da Campanha no Campaign Standard

* Nome do Delivery: A ID do Delivery no Campaign Standard

* Data de Envio/Abertura/Cliquado/Rejeitado: Data/hora em que o evento foi criado

* URL de rastreamento: URL clicado

* URL do Mirror page: O URL para o mirror page do email que foi enviado/aberto/clicado/retornado

Você pode ver um vídeo do URL do mirror page sendo usado no vídeo abaixo.

>[!VIDEO](https://video.tv.adobe.com/v/29253)

>[!NOTE]
>
>Para opção de não participação, quando um atributo de opção de não participação é modificado no Dynamics 365, ele será refletido na Campanha se você tiver selecionado a configuração de opção de não participação dinâmica 365 para Campanha ou bidirecional e se você tiver esse atributo específico mapeado corretamente.

**Tópicos relacionados**

* Configurar Campanha para integração entre Campaign/Dynamics 365
* Configurar o Dynamics para integração com o Campaign/Dynamics 365
* Configurar o Unifi para integração entre Campaign/Dynamics 365
* Saiba como mapear recursos personalizados e entidades personalizadas