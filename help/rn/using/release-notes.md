---
title: Notas de versão mais recentes
description: Esta página detalha o conteúdo da versão mais recente do Campaign Standard
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: c2d2f3843801d108f007fea52a76e41abe16d76c
workflow-type: ht
source-wordcount: '390'
ht-degree: 100%

---


# Notas de versão mais recentes {#latest-release}

<!--
![Control Panel](assets/do-not-localize/cp-icon.png) **New Control Panel release**. [Learn more](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html){target="_blank"}.-->


## Notas de versão antecipadas {#e-new-release}

Esta seção lista as melhorias e alterações incluídas na próxima versão do Campaign Standard.

>[!CAUTION]
>
>Esse conteúdo está sujeito a alterações sem aviso prévio até a data de atualização dos ambientes de preparo. Saiba mais na [página de planejamento de versão](../../rn/using/release-planning.md).

### Versão 25.1 – Versão do inverno de 2025 {#winter-25}

#### Correções de segurança {#winter-25-security}

* Esta versão inclui correções de segurança.
* Esta versão inclui a seguinte atualização de segurança: o Apache Tomcat foi atualizado para a v10.1.33.

#### Outras correções {#winter-25-fixes}

* Correção de um problema duplicado em modelos (CAMP-56340)
* Correção de uma regressão de rastreamento quando URLs dinâmicos eram usados em modelos do Adobe Experience Manager (CAMP-51932)
* Correção de um problema de desempenho no processo de faturamento (CAMP-56796)
* Correção de um problema de codificação de HTML com o caractere `>` em páginas da web JSSP (CAMP-56497)
* Correção de um problema nos relatórios dinâmicos ao usar a opção **Exibir nas linhas selecionadas** (CAMP-55895)


## Versão 24.2 – Versão do verão de 2024 (LA) {#summer-24}

### Melhoria {#summer-24-rn-improvements}

**Migração para as credenciais OAuth de servidor para servidor**

A partir desta versão, com a credencial de conta de serviço (JWT) sendo descontinuada pela Adobe, as integrações de saída do Campaign com soluções e aplicativos Adobe agora dependem da credencial de servidor para servidor do OAuth. A Adobe executará a migração de JWT para OAuth em suas integrações de saída, como a integração do Campaign-Analytics ou a integração dos Acionadores da Experience Cloud.

Se você implementou integrações de entrada com o Campaign e está usando [APIs do Campaign](../../api/using/get-started-apis.md), é necessário migrar sua conta técnica conforme detalhado [nesta documentação](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/){target="_blank"}. As credenciais da Conta de serviço (JWT) deixarão de funcionar em **27 de janeiro de 2025**.

### Correções {#summer-24-rn-fixes}

* Correção de um problema que fazia com que o scheduler de fluxos de trabalho iniciasse antes do horário agendado. (CAMP-55412)
* Correção de um problema que causava um erro ao duplicar campos personalizados em notificações por push transacionais. (CAMP-54459)
* Correção de problemas que afetavam a usabilidade do scheduler de hora e data para mensagens no aplicativo. (CAMP-54495)
* Correção de um problema que fazia com que o rastreamento não funcionasse ao utilizar o recurso de alias de rastreamento personalizado, e o link inteiro ser dinâmico. (CAMP-56044)
* Correção de um problema que fazia com que uma quantidade limitada de modelos fosse exibida ao usar a pesquisa para localizar modelos específicos. (CAMP-55273)
* Adição dos seguintes idiomas à lista suspensa de idiomas preferidos: en_kz (inglês – Cazaquistão) e en_ua (inglês – Ucrânia). (CAMP-55336)
* Correção de um problema que fazia com que os botões de ajuste de hora não funcionassem nas configurações do scheduler. (CAMP-53602)
* Correção de vários problemas da interface do usuário relacionados à barra de ajuste de hora nas configurações do scheduler. (CAMP-55291)
