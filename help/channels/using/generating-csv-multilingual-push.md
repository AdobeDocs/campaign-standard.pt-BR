---
solution: Campaign Standard
product: campaign
title: Gerando um arquivo CSV para Notificação por push multilíngue com Campaign Standard
description: Fazer upload de um arquivo CSV para gerar conteúdo para entrega é um recurso usado para suportar notificações por push multilíngues.
audience: channels
content-type: reference
topic-tags: email-messages
feature: Empurrar
role: Profissional
level: Intermediário
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '1131'
ht-degree: 0%

---


# Gerando um arquivo CSV para Notificação por push multilíngue{#generating-csv-multilingual-push}

Fazer upload de um arquivo CSV para gerar conteúdo para entrega é um recurso usado para suportar notificações de push multilíngues. O formato do arquivo CSV precisa seguir determinadas diretrizes para que o upload do arquivo seja bem-sucedido e, consequentemente, possa criar um delivery. As seções a seguir descrevem o formato do arquivo e suas considerações.

## Formato de arquivo {#file-format}

O push multilíngue requer 14 colunas no arquivo CSV:

1. título
1. messageBody
1. som
1. adge
1. deeplinkURI
1. categoria
1. iosMediaAttachmentURL
1. androidMediaAttachmentURL
1. isContentAvailable
1. isMutableContent
1. customFields
1. locale
1. language
1. quietPush

Verifique a amostra CSV clicando em **[!UICONTROL Download a sample file]** na janela **[!UICONTROL Manage Content Variants]**. Para obter mais informações, consulte esta [seção](../../channels/using/creating-a-multilingual-push-notification.md).

* **título, messageBody, som, selo, deeplinkURI, categoria, iosMediaAttachmentURL, androidMediaAttachmentURL**: conteúdo regular de carga de push. É necessário fornecer essas informações de maneira semelhante ao criar deliveries por push.
* **Campos** personalizados: usar o formato JSON para os campos personalizados, por exemplo  `{"key1":"value1","key2":"value2"}`. Consulte o arquivo de exemplo acima para obter um exemplo de campos personalizados.
* **isContentAvailable**: sinalizador para verificação de Conteúdo disponível, o valor 1 implica true, o valor 0 implica false. O valor padrão é 0. Se deixar essa coluna em branco, o valor será considerado 0.
* **isMutableContent**: sinalizador para Conteúdo variável, o valor 1 implica verdadeiro, o valor 0 implica falso. O valor padrão é 0. Se deixar essa coluna em branco, o valor será considerado 0.
* **localidade**: locale é o campo para variantes de idioma, por exemplo &quot;en_us&quot; para inglês dos EUA e &quot;fr_fr&quot; para francês-francês.
* **idioma**: nome do idioma associado à localidade. Por exemplo, se a localidade for &quot;en_us&quot;, o nome do idioma deverá ser &quot;English-United States&quot;.
* **quietPush**: sinalizador para o tipo de notificação por push. Se for uma notificação por push regular, o valor deve ser 0. Se for um push silencioso, o valor deve ser 1. O valor padrão é 0. Se deixar essa coluna em branco, o valor será considerado 0.

## Restrições e Diretrizes para a criação do arquivo csv {#constraints-guideline-csv}

**O nome de cada coluna é fixo**.
Você deve incluir o nome de cada coluna no arquivo CSV. Caso não use nenhuma coluna para o conteúdo, deixe-a em branco.

**As colunas &quot;locale&quot; e &quot;language&quot; são obrigatórias e o valor é exclusivo para cada linha.**
Um valor em branco para essa coluna resultará em uma falha no upload do arquivo.

**A ordem das colunas é importante**. A ordem das colunas no arquivo carregado deve seguir o mesmo formato do arquivo de amostra.

**Citar conteúdo da coluna**. Como esse é um arquivo CSV (ou seja, valores separados por vírgula), qualquer conteúdo de coluna que inclui vírgula (,) deve ser cotado. Por exemplo, &quot;Olá, Tom!&quot;

**A codificação UTF-8 é necessária para caracteres internacionais.**

**Se você gerar o arquivo por texto simples, separe cada coluna por &quot;,&quot;.**

**Incompatibilidade de Variante.** Se você usar o bloco de conteúdo e os públicos-alvo com idiomas específicos, será necessário listar cada idioma direcionado no arquivo CSV ou ocorrerá um erro ao enviar o delivery.

## Inserção de campo de personalização no arquivo csv {#personalization-field-csv}

Se quiser usar campos de personalização, inclua a tag <span> no arquivo.

Para inserir o campo de personalização &quot;firstName&quot; no messageBody, a mensagem precisa ser:

```
 "Hello <span class="nl-dce-field nl-dce-done"  data-nl-expr="/context/profile/firstName">First name</span>, this is message".
```

O campo &quot;firstName&quot; é representado por:

```
 <span class="nl-dce-field nl-dce-done" data-nl-expr="/context/profile/firstName">First name</span>
```

No span há dois atributos obrigatórios:

* Uma é a classe que é estática. Não importa qual campo de personalização você planeja usar, ele sempre será class=&quot;nl-dce-field nl-dce-done&quot;.

* Outro é data-nl-expr, que é o caminho do campo de personalização. Por exemplo, se você inserir o campo de personalização &quot;firstName&quot; na interface do usuário, o caminho de navegação será **[!UICONTROL Context (context)]** > **[!UICONTROL Profile (profile)]** > **[!UICONTROL First name (firstName)]** (conforme mostrado na imagem abaixo). Nesse caso, o caminho será

   ```
   /context/profile/firstName. data-nl-expr="/context/profile/firstName".
   ```

![](assets/multilingual_push_2.png)

## Localidade e nomes de idioma {#locale-language-names}

Os seguintes idiomas são suportados:

| locale | idioma |
|:-:|:-:|
| af_za | Afrikaans - África do Sul |
| sq_al | Albânia - Albânia |
| ar_dz | Árabe - Argélia |
| ar_bh | Árabe - Bahrein |
| ar_iq | Árabe - Iraque |
| ar_il | Árabe - Israel |
| ar_jo | Árabe - Jordânia |
| ar_kw | Árabe - Kuwait |
| ar_lb | Árabe - Líbano |
| ar_ma | Árabe - Marrocos |
| ar_om | Árabe - Omã |
| ar_qa | Árabe - Qatar |
| ar_sa | Árabe - Arábia Saudita |
| ar_sy | Árabe - Síria |
| ar_tn | Árabe - Tunísia |
| ar_ae | Árabe - Emirados Árabes Unidos |
| ar_ye | Árabe - Iêmen |
| hy_am | Armênio - Armênia |
| az_az | Azeri - Azerbaijão |
| be_by | Bielorrússia - Bielorrússia |
| bs_ba | Bósnio - Bósnia |
| bg_bg | Búlgaro - Bulgária |
| ca_es | Catalão - Espanha |
| zh_cn | Chinês (Simplificado) - China |
| zh_sg | Chinês (Simplificado) - Singapura |
| zh_hk | Chinês (Tradicional) - Região Administrativa Especial de Hong Kong da China |
| zh_tw | Chinês (Tradicional) - Região de Taiwan |
| hr_hr | Croata - Croácia |
| cs_cz | Tcheco - Tcheco |
| da_dk | Dinamarquês - Dinamarca |
| nl_be | Holandês - Bélgica |
| nl_nl | Holandês - Países Baixos |
| en_au | Inglês - Austrália |
| en_bz | Inglês - Belize |
| en_ca | Inglês - Canadá |
| en_in | Inglês - Índia |
| en_ie | Inglês - Irlanda |
| en_jm | Inglês - Jamaica |
| en_nz | Inglês - Nova Zelândia |
| en_ph | Inglês - Filipinas |
| en_za | Inglês - África do Sul |
| en_tt | Inglês - Trinidad e Tobago |
| en_gb | Inglês - Reino Unido |
| en_us | Inglês - Estados Unidos |
| en_zw | Inglês - Zimbábue |
| et_ee | Estoniano - Estônia |
| fi_fi | Finlandês - Finlândia |
| fr_be | Francês - Bélgica |
| fr_ca | Francês - Canadá |
| fr_fr | Francês - França |
| fr_lu | Francês - Luxemburgo |
| fr_ch | Francês - Suíça |
| de_at | Alemão - Áustria |
| de_de | Alemão - Alemanha |
| de_lu | Alemão - Luxemburgo |
| de_ch | Alemão - Suíça |
| el_cy | Grego - Chipre |
| el_gr | Grego - Grécia |
| gu_in | Gujarati - Índia |
| he_il | Hebraico - Israel |
| hi_in | Híndi - Índia |
| hu_hu | Húngaro - Hungria |
| is_is | Islandês - Islândia |
| id_id | Indonésio - Indonésia |
| it_it | Italiano - Itália |
| it_ch | Italiano - Suíça |
| ja_jp | Japonês - Japão |
| kn_in | Kannada - Índia |
| kk_kz | Cazaque - Cazaquistão |
| ko_kr | Coreano - Coreia do Sul |
| lv_lv | Letão - Letónia |
| lt_lt | Lituano - Lituânia |
| mk_mk | Macedônio - Macedônia |
| ms_my | Malaio - Malásia |
| mr_in | Marathi - Índia |
| no_no | Norueguês - Noruega |
| pl_pl | Polonês - Polônia |
| pt_br | Português - Brasil |
| pt_pt | Português - Portugal |
| pa_in | Punjabi - Índia |
| ro_md | Romeno - Moldávia |
| ro_ro | Romeno - Romênia |
| ru_kz | Russo - Cazaquistão |
| ru_ru | Russo - Rússia |
| ru_ua | Russo - Ucrânia |
| a_in | Sânscrito - Índia |
| sr_ba | Sérvio - Bósnia |
| sr_rs | Sérvio - Sérvia |
| sk_sk | Eslovaco - Eslováquia |
| sl_si | Esloveno - Eslovênia |
| es_ar | Espanhol - Argentina |
| es_bo | Espanhol - Bolívia |
| es_cl | Espanhol - Chile |
| es_co | Espanhol - Colômbia |
| es_cr | Espanhol - Costa Rica |
| es_do | Espanhol - República Dominicana |
| es_ec | Espanhol - Equador |
| es_sv | Espanhol - El Salvador |
| es_gt | Espanhol - Guatemala |
| es_hn | Espanhol - Honduras |
| es_mx | Espanhol - México |
| es_ni | Espanhol - Nicarágua |
| es_pa | Espanhol - Panamá |
| es_py | Espanhol - Paraguai |
| es_pe | Espanhol - Peru |
| es_pr | Espanhol - Porto Rico |
| es_es | Espanhol - Espanha |
| es_uy | Espanhol - Uruguai |
| es_ve | Espanhol - Venezuela |
| sw_ke | Suaíli - Quênia |
| sv_fi | Sueco - Finlândia |
| sv_se | Sueco - Suécia |
| ta_in | Tamil - Índia |
| tt_ru | Tártaro - Russo |
| te_in | Telugu - Índia |
| th_th | Tailandês - Tailândia |
| tr_cy | Turco - Chipre |
| tr_tr | Turco - Turquia |
| uk_ua | Ucraniano - Ukrain |
| ur_in | Urdu - Índia |
| ur_pk | Urdu - Paquistão |
| vi_vn | Vietnamita - Vietnã |
