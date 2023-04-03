---
source-git-commit: 48b6c5de8871e9e1f12c91474376abc53a199bc8
workflow-type: tm+mt
source-wordcount: '125'
ht-degree: 100%

---
>[!CAUTION]
>
> Esse conteúdo está sujeito a alterações sem aviso prévio até a data de atualização dos ambientes de estágio. Saiba mais na [página de planejamento de versão](../../rn/using/release-planning.md).
## Versão 22.3.2 {#dec-22}

### Atualização de segurança{#rn-security2}

Esta versão inclui a seguinte atualização de segurança: o Debian foi atualizado para a v11.0.

## Versão 22.3 - outono/inverno de 2022 {#sept-22}

### Atualização de segurança{#rn-security}

Esta versão vem com a seguinte atualização de segurança: O Apache Tomcat foi atualizado da v7.0 para a v8.0.

### Correções{#e-rn-fixes}

* Correção de um problema com relatórios agendados, que eram acionados uma hora antes do tempo agendado. (CAMP-51502)
* Correção de um problema nos indicadores de delivery do painel Delivery que não correspondiam aos logs de envio (nms:broadLogRcp). (CAMP-51127)
* Correção de um problema que impedia a extensão de recursos personalizados com o Conector ACS (oferta principal). (CAMP-51033)
* Melhoria do processo de publicação de respostas de solicitações de privacidade para evitar atraso. (CAMP-50613)
