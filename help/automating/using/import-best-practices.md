---
title: Práticas recomendadas de importação
description: Saiba mais sobre as práticas recomendadas a serem seguidas ao importar dados para o banco de dados.
page-status-flag: never-activated
uuid: d909d26a-cf50-46af-ae09-f0fd7258ca27
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 75b83165-dcbd-4bb7-b703-ed769f489b16
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '569'
ht-degree: 75%

---


# Práticas recomendadas de importação {#import-best-practices}

>[!CAUTION]
>
>Lembre-se dos limites do armazenamento SFTP, Armazenamento DB e perfil ativo conforme o contrato da Adobe Campaign ao usar essa funcionalidade.

Ser cuidadoso e seguir apenas algumas regras simples detalhadas abaixo ajudará a garantir a consistência dos dados dentro do banco de dados e evitar erros comuns durante a atualização ou exportação de dados.

## Uso de templates de importação {#using-import-templates}

A maioria dos workflows de importação deve conter as seguintes atividades: **[!UICONTROL Load file]**, **[!UICONTROL Reconciliation]**, **[!UICONTROL Segmentation]**, **[!UICONTROL Deduplication]**, **[!UICONTROL Update data]**.

É muito conveniente usar templates de importação para preparar importações semelhantes e garantir a consistência dos dados no banco de dados.

Em muitos projetos, as importações são criadas sem a atividade **[!UICONTROL Deduplication]** porque os arquivos usados no projeto não têm duplicatas. As duplicatas às vezes surgem da importação de arquivos diferentes. A eliminação de duplicatas é difícil. Portanto, a etapa de eliminação de duplicatas é uma boa precaução em todos os workflows de importação.

Não confie na suposição de que os dados de entrada são consistentes e corretos, ou que o departamento de TI ou o supervisor do Adobe Campaign irá resolver isso. Durante o projeto, mantenha a limpeza dos dados em mente. Elimine duplicatas, reconcilie e mantenha de consistência ao importar dados.

Um exemplo de um modelo de fluxo de trabalho genérico projetado para importar dados está disponível no [Exemplo: Importar seção de modelo](../../automating/using/creating-import-workflow-templates.md) de fluxo de trabalho.

>[!NOTE]
>
>Você também pode usar [templates de importação](../../automating/using/importing-data-with-import-templates.md). São modelos de fluxo de trabalho definidos por um administrador que, uma vez ativado, apenas oferta a possibilidade de especificar o arquivo que contém os dados a serem importados.

**Tópicos relacionados:**

* [Carregar atividade de arquivo](../../automating/using/load-file.md)
* [Atividade de reconciliação](../../automating/using/reconciliation.md)
* [Atividade de Segmentação](../../automating/using/segmentation.md)
* [Atividade desduplicação-duplicada](../../automating/using/deduplication.md)
* [Atualizar atividade de dados](../../automating/using/update-data.md)

## Uso dos formatos de arquivo simples {#using-flat-file-formats}

O formato mais eficiente para importações é o arquivo simples. Arquivos simples podem ser importados no modo em massa no nível do banco de dados.

Por exemplo:

* Separador: tabulação ou ponto e vírgula
* Primeira linha com cabeçalhos
* Nenhum delimitador de cadeia de caracteres
* Formato de data: AAAA/MM/DD HH:mm:SS

Exemplo de arquivo a ser importado:

```
lastname;firstname;birthdate;email;crmID
Smith;Hayden;23/05/1989;hayden.smith@example.com;124365
Mars;Daniel;17/11/1987;dannymars@example.com;123545
Smith;Clara;08/02/1989;hayden.smith@example.com;124567
Durance;Allison;15/12/1978;allison.durance@example.com;120987
```

## Uso da compactação {#using-compression}

Use arquivos compactados para importações e exportações sempre que possível. O GZIP é suportado por padrão. Você pode adicionar pré-processamento ao importar arquivos ou pós-processamento ao extrair dados, respectivamente, nas atividades **[!UICONTROL Load file]** e **[!UICONTROL Extract file]** de fluxo de trabalho.

**Tópicos relacionados:**

* [Carregar atividade de arquivo](../../automating/using/load-file.md)
* [Extrair atividade de arquivo](../../automating/using/extract-file.md)

## Importação no modo Delta {#importing-in-delta-mode}

As importações regulares devem ser efetuadas no modo delta. Isso significa que somente os dados modificados ou novos são enviados ao Adobe Campaign, em vez da tabela toda sempre.

As importações completas devem ser usadas somente para carregamento inicial.

## Manutenção da consistência {#maintaining-consistency}

Para manter a consistência dos dados no banco de dados do Adobe Campaign, siga os princípios abaixo:

* Se os dados importados corresponderem a uma tabela de referência no Adobe Campaign, então ele deverá ser reconciliado com essa tabela no workflow. Os registros que não correspondem devem ser rejeitados.
* Certifique-se de que os dados importados sejam sempre **&quot;normalizados&quot;** (email, número de telefone, endereço de mala direta) e que essa normalização seja confiável e não será alterada ao longo dos anos. Se não for o caso, provavelmente aparecerão algumas duplicatas no banco de dados e, como o Adobe Campaign não fornece ferramentas para fazer a correspondência &quot;difusa&quot;, será muito difícil removê-las e gerencia-las.
* Os dados transacionais devem ter uma chave de reconciliação e serem reconciliados com os dados existentes para evitar a criação de duplicatas.
* **Importação de arquivos relacionados em ordem**. Se a importação for composta de vários arquivos que dependem uns dos outros, o workflow deve garantir que os arquivos sejam importados na ordem correta. Quando um arquivo falhar, os outros arquivos não serão importados.
* **Elimine duplicatas**, reconcilie e mantenha de consistência ao importar dados.
