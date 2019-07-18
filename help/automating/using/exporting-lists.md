---
title: Exportar listas
seo-title: Exportar listas
description: Exportar listas
seo-description: 'O Adobe Campaign permite exportar os dados exibidos como listas de uma tela de visão geral diretamente em um arquivo para uso futuro. '
page-status-flag: nunca ativado
uuid: c 64 fe 706-bd 6 e -4746-958 e-f 94226 f 4 e 2 cb
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizando
content-type: reference
topic-tags: importar e exportar dados
discoiquuid: 12 c 874 da -435 f -44 b 6-a 3 c 8-873301 e 177 cc
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 36727e82d3aa73add6116fa2916752ff0e407d9d

---


# Exporting lists{#exporting-lists}

O Adobe Campaign permite exportar suas listas diretamente em um arquivo para uso futuro. Exporting a list in a file generates a log entry in the **[!UICONTROL Export audits]** menu. For more information on export audits, refer to the [Auditing exports](../../administration/using/auditing-export-logs.md) section.

The export list option allows you to export a maximum of 100,000 lines by default and defined by the **Nms_ExportListLimit** option. This option can be managed by the functional administrator, under the **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Options]** menu.

Export list is available in all the screens that have a **List** mode view, for users with the **[!UICONTROL EXPORT (export)]** role.

1. Go to your chosen **List** screen. For example, the test profile overview screen ( **[!UICONTROL Profiles & audiences]** &gt; **[!UICONTROL Test profiles]** ).
1. Check that the screen is in **List** mode.

   ![](assets/export_list_mode_switch.png)

1. Organize the columns in the list in the order that you want to export them using the **[!UICONTROL Configure list]** button, in the top right corner. Além das colunas configuradas, a chave primária do recurso também será exportada.
1. Se desejar, você pode aplicar um filtro. Para fazer isso, clique no botão no canto superior esquerdo para mostrar o painel de pesquisa.

   Se você realizar uma exportação de uma lista contendo recursos diferentes, deverá aplicar seus filtros para que apenas um tipo de recurso seja exibido na lista.

1. Se desejar, classifique suas colunas escolhidas.
1. Select the export button ![](assets/exportlistbutton.png).

   Um pop-up será exibido para confirmar a exportação. Após confirmar a exportação, o arquivo será baixado automaticamente para o seu computador.

O arquivo é gerado no formato CSV, a menos que a exportação seja executada no iOS, e nesse caso o arquivo gerado está no formato TXT. Ele é nomeado de acordo com o recurso exportado e a data de exportação. Por exemplo: o nome profilebase_ 20150426_ 120253. csv seria aplicado a uma exportação de perfil realizada em 26 de abril de 2015 às 12:02:53. É codificado no formato UTF -8.

Os valores numéricos e as datas levam em conta o horário local (localidade) do usuário que executa a exportação. Por exemplo: DD-MM-AAAA ou MM-DD-AAAA.

Para executar uma exportação maior do que essa, você deve criar um fluxo de trabalho dedicado. Refer to the [Extract file](../../automating/using/extract-file.md) section.

**Exemplo**

O exemplo a seguir é uma exportação realizada da lista de perfil definida abaixo:

* Colunas exibidas (em ordem): Sobrenome, Nome, Data de nascimento, Endereço de email.
* Os nomes são classificados em ordem alfabética.

![](assets/export_list_example1.png)

O arquivo gerado é apresentado da seguinte maneira (para os primeiros dez registros):

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
* [Configuração de vídeo da lista](https://helpx.adobe.com/campaign/kt/acs/using/acs-configuring-a-list-feature-video-setup.html)

