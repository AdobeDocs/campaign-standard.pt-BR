---
title: Gerando um arquivo CSV para Notificação por push multilíngue com Campaign Standard
description: Fazer upload de um arquivo CSV para gerar conteúdo para entrega é um recurso usado para dar suporte a notificações por push multilíngues.
audience: channels
content-type: reference
topic-tags: email-messages
feature: Push
role: User
level: Intermediate
exl-id: bd9ec3f9-e047-42dc-ab64-9fb274cb4656
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1127'
ht-degree: 1%

---

# Gerar um arquivo CSV para Notificação por push multilíngue{#generating-csv-multilingual-push}

Fazer upload de um arquivo CSV para gerar conteúdo para entrega é um recurso usado para dar suporte a notificações por push multilíngues. O formato do arquivo CSV precisa seguir determinadas diretrizes para que o upload do arquivo seja bem-sucedido e, consequentemente, possa criar um delivery. As seções a seguir descrevem o formato de arquivo e as considerações a ele relacionadas.

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
1. localidade
1. language
1. silentPush

Verifique a amostra de CSV clicando no ícone **[!UICONTROL Download a sample file]** no **[!UICONTROL Manage Content Variants]** janela. Para obter mais informações, consulte este [seção](../../channels/using/creating-a-multilingual-push-notification.md).

* **title, messageBody, som, selo, deeplinkURI, categoria, iosMediaAttachmentURL, androidMediaAttachmentURL**: conteúdo da carga de push normal. Você precisa fornecer essas informações de maneira semelhante à criação de deliveries por push.
* **Campos personalizados**: use o formato JSON para os campos personalizados, por exemplo, `{"key1":"value1","key2":"value2"}`. Consulte o arquivo de amostra acima para obter um exemplo de campos personalizados.
* **isContentAvailable**: sinalizador para verificação de Conteúdo disponível, o valor 1 implica verdadeiro, o valor 0 implica falso. O valor padrão é 0. Se você deixar essa coluna em branco, o valor será considerado 0.
* **isMutableContent**: sinalizador para Conteúdo mutável, o valor 1 implica verdadeiro, o valor 0 implica falso. O valor padrão é 0. Se você deixar essa coluna em branco, o valor será considerado 0.
* **localidade**: locale é o campo para variantes de idioma, por exemplo, &quot;en_us&quot; para inglês dos EUA e &quot;fr_fr&quot; para francês.
* **idioma**: nome do idioma associado à localidade. Por exemplo, se o local for &quot;en_us&quot;, o nome do idioma deverá ser &quot;English-United States&quot;.
* **silentPush**: sinalizador para o tipo de notificação por push. Se for uma notificação por push regular, o valor deverá ser 0. Se for um push silencioso, o valor deverá ser 1. O valor padrão é 0. Se você deixar essa coluna em branco, o valor será considerado 0.

## Restrições e diretrizes para a criação do arquivo csv {#constraints-guideline-csv}

**O nome de cada coluna é fixo**.
Você deve incluir o nome de cada coluna no arquivo CSV. Caso não use nenhuma coluna para o conteúdo, deixe-a em branco.

**As colunas &quot;locale&quot; e &quot;language&quot; são obrigatórias e o valor é exclusivo para cada linha.**
Um valor em branco para essa coluna resultará em uma falha no upload do arquivo.

**A ordem das colunas é importante**. A ordem das colunas no arquivo carregado precisa seguir o mesmo formato do arquivo de amostra.

**Citar conteúdo da coluna**. Como esse é um arquivo CSV (significa Valores separados por vírgula), qualquer conteúdo de coluna que inclua vírgula (,) deve ser citado. Por exemplo, &quot;Olá, Tom!&quot;

**A codificação UTF-8 é necessária para caracteres internacionais.**

**Se você gerar o arquivo por texto simples, separe cada coluna por &quot;,&quot;.**

**Incompatibilidade de variante.** Se você usa blocos de conteúdo e direciona públicos-alvo com idiomas específicos, é necessário listar cada idioma direcionado no arquivo CSV, caso contrário ocorrerá um erro ao enviar o delivery.

## Inserção de um campo de personalização no arquivo csv {#personalization-field-csv}

Se quiser usar campos de personalização, você deve incluir <span> no arquivo.

Para inserir o campo de personalização &quot;firstName&quot; no messageBody, a mensagem precisa ser:

```
 "Hello <span class="nl-dce-field nl-dce-done"  data-nl-expr="/context/profile/firstName">First name</span>, this is message".
```

O campo &quot;firstName&quot; é representado por:

```
 <span class="nl-dce-field nl-dce-done" data-nl-expr="/context/profile/firstName">First name</span>
```

No span há dois atributos obrigatórios:

* Uma é a classe que é estática. Não importa qual campo de personalização você planeje usar, ele sempre será class=&quot;nl-dce-field nl-dce-done&quot;.

* Outro é data-nl-expr, que é o caminho do campo de personalização. Por exemplo, se você inserir o campo de personalização &quot;firstName&quot; na interface, o caminho de navegação será **[!UICONTROL Context (context)]** > **[!UICONTROL Profile (profile)]** > **[!UICONTROL First name (firstName)]** (conforme mostrado na imagem abaixo). Nesse caso, o caminho será

  ```
  /context/profile/firstName. data-nl-expr="/context/profile/firstName".
  ```

![](assets/multilingual_push_2.png)

## Localidade e nomes de idiomas {#locale-language-names}

Os seguintes idiomas são suportados:

| localidade | language |
|:-:|:-:|
| af_za | Africâner - África do Sul |
| sq_al | Albanês - Albânia |
| ar_dz | Árabe - Argélia |
| ar_bh | Árabe - Bahrein |
| ar_iq | Árabe - Iraque |
| ar_il | Árabe - Israel |
| ar_jo | Árabe - Jordânia |
| ar_kw | Árabe - Kuwait |
| ar_lb | Árabe - Líbano |
| ar_ma | Árabe - Marrocos |
| ar_om | Árabe - Omã |
| ar_qa | Árabe - Catar |
| ar_sa | Árabe - Arábia Saudita |
| ar_sy | Árabe - Síria |
| ar_tn | Árabe - Tunísia |
| ar_ae | Árabe - Emirados Árabes Unidos |
| ar_ye | Árabe - Iêmen |
| hy_am | Armênio - Armênia |
| az_az | Azeri - Azerbaijão |
| be_by | Bielo-russo - Belarus |
| bs_ba | Bósnio - Bósnia |
| bg_bg | Búlgaro - Bulgária |
| ca_es | Catalão - Espanha |
| zh_cn | Chinês (simplificado) - China |
| zh_sg | Chinês (simplificado) - Cingapura |
| zh_hk | Chinês (Tradicional) - RAE de Hong Kong da China |
| zh_tw | Chinês (tradicional) - região de Taiwan |
| hr_hr | Croata - Croácia |
| cs_cz | Tcheco - Chéquia |
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
| gu_in | Guzerate - Índia |
| he_il | Hebraico - Israel |
| hi_in | Hindi - Índia |
| hu_hu | Húngaro - Hungria |
| is_is | Islandês - Islândia |
| id_id | Indonésio - Indonésia |
| it_it | Italiano - Itália |
| it_ch | Italiano - Suíça |
| ja_jp | Japonês - Japão |
| kn_in | Kannada - Índia |
| kk_kz | Cazaque - Cazaquistão |
| ko_kr | Coreano - Coreia do Sul |
| lv_lv | Letão - Letônia |
| lt_lt | Lituano - Lituânia |
| mk_mk | Macedônio - Macedônia |
| ms_my | Malaio - Malásia |
| mr_in | Marati - Índia |
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
| ta_in | Tâmil - Índia |
| tt_ru | Tártaro - Russo |
| te_in | Télugo - Índia |
| th_th | Tailandês - Tailândia |
| tr_cy | Turco - Chipre |
| tr_tr | Turco - Turquia |
| uk_ua | Ucraniano - Ukraine |
| ur_in | Urdu - Índia |
| ur_pk | Urdu - Paquistão |
| vi_vn | Vietnamita - Vietnã |
