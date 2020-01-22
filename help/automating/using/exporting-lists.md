---
title: Exportar listas
description: 'O Adobe Campaign permite exportar os dados exibidos como listas de uma tela de visão geral diretamente em um arquivo para uso futuro. '
page-status-flag: never-activated
uuid: c64fe706-bd6e-4746-958e-f94226f4e2cb
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
discoiquuid: 12c874da-435f-44b6-a3c8-873301e177cc
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2d8a46a53f2abd453aaf0ff8322b7f9b942ec1c6

---


# Exportar listas{#exporting-lists}

O Adobe Campaign permite exportar suas listas diretamente em um arquivo para uso futuro. Exportar uma lista em um arquivo gera uma entrada de log no **[!UICONTROL Export audits]**menu. Para obter mais informações sobre auditorias de exportação, consulte a seção[Auditando exportações](../../administration/using/auditing-export-logs.md).

A opção de lista de exportação permite exportar um máximo de 100.000 linhas por padrão e definidas pela opção **Nms_ExportListLimit** . Essa opção pode ser gerenciada pelo administrador funcional, no menu **[!UICONTROL Administration]**>**[!UICONTROL Application settings]** > **[!UICONTROL Options]**.

A lista Exportar está disponível em todas as telas que têm uma exibição no modo **Lista** , para usuários com a **[!UICONTROL EXPORT (export)]**função.

1. Vá para a tela **Lista** escolhida. Por exemplo, a tela de visão geral do perfil de teste ( **[!UICONTROL Profiles & audiences]**>**[!UICONTROL Test profiles]** ).
1. Verifique se a tela está no modo **Lista** .

   ![](assets/export_list_mode_switch.png)

1. Organize as colunas na lista na ordem em que deseja exportá-las usando o **[!UICONTROL Configure list]**botão, no canto superior direito. Além das colunas configuradas, a chave primária do recurso também será exportada.
1. Se desejar, você pode aplicar um filtro. Para fazer isso, clique no botão no canto superior esquerdo para mostrar o painel de pesquisa.

   Se você realizar uma exportação de uma lista que contém recursos diferentes, deverá aplicar seus filtros para que apenas um tipo de recurso seja exibido na lista.

1. Se desejar, classifique a(s) coluna(s) escolhida(s).
1. Selecione o botão exportar ![](assets/exportlistbutton.png).

   Um pop-up será exibido para confirmar a exportação. Após confirmar a exportação, o arquivo será baixado automaticamente no computador.

O arquivo é gerado no formato CSV, a menos que a exportação seja realizada no iOS, caso em que o arquivo gerado esteja no formato TXT. É nomeado de acordo com o recurso exportado e a data de exportação. Por exemplo: o nome profileBase_20150426_120253.csv seria aplicado a uma exportação de perfil realizada em 26 de abril de 2015 às 12:02:53. É codificado no formato UTF-8.

Os valores numéricos e as datas levam em conta a hora local (localidade) do usuário que realiza a exportação. Por exemplo: DD-MM-AAAA ou MM-DD-AAAA.

Para realizar uma exportação maior que essa, é necessário criar um fluxo de trabalho dedicado. Consulte a seção [Extrair arquivo](../../automating/using/extract-file.md) .

**Exemplo**

O exemplo a seguir é uma exportação realizada da lista de perfis definida abaixo:

* Colunas exibidas (em ordem): Sobrenome, Nome, Data de nascimento, Endereço de email.
* Os nomes são classificados em ordem alfabética.

![](assets/export_list_example1.png)

O arquivo gerado é apresentado da seguinte forma (para os primeiros dez registros):

```
Last name;First name;Birth date;Email;Zip code
Abalo;Patrick;11/11/1941 02:00:00;patrick.a@testmail.com;29200
Abasq;Joel;21/08/1977 02:00:00;abasq.joel@testmail.com;92160
Abernot;John;12/07/1963 01:00:00;john.abernot@testmail.com;78510
Abiven;Christian;16/03/1975 01:00:00;chris.a@mailtest.com;35000
Abouvier;Peter;02/07/1975 01:00:00;pabouvier@mailtest.com;94560
Accardi;Mike;22/06/1948 01:00:00;mike.accardi@mail.com;76400
Accremont;Frank;27/04/1947 01:00:00;accr.frank@mailtest.com;13500
Adam;Daniel;17/09/1953 01:00:00;danieladam@mail.com;17000
Adama;Pascal;22/01/1990 01:00:00;adapascal@mailtest.com;75012
Adama;Henry;22/09/1992 02:00:00;henry.adama@mail.com;64120
```

**Tópicos relacionados:**

* [Funções](../../administration/using/list-of-roles.md)
* [Personalização de listas](../../start/using/customizing-lists.md)
* [Configuração do vídeo da lista](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/getting-started/configure-a-list.html)
