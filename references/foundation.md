# 基礎の値と使いどころ

色、文字、余白、影、グリッドの値と、それぞれの使いどころです。値は `tokens.css`（hds-design-tokens 6.0.7）から、使いどころは HDS の公式文書（https://hds.hel.fi/ の Foundation の章）から取りました。文書に無いことは「このスキルの判断」と書いています。

## 色

### 名前の由来

ヘルシンキ市のビジュアルアイデンティティの案内に、「色は市の街並みから取った見覚えのある色で、Engel の黄、Metro の橙、Bus の青などがある」とあります。色ごとの由来は書かれていません。フィンランド語の名前は HDS の表にあります。

### ブランド色

primary、secondary、tertiary に使う色です。状態（成功・エラーなど）の表示には使いません。

| トークン | 英名（フィンランド語名） | 値 | 上に置く文字色 | コントラスト |
|---|---|---|---|---|
| `--color-bus` | Bus（Bussi） | #0000bf | 白 | 12 : 1 |
| `--color-coat-of-arms` | Coat of Arms（Vaakuna） | #0072c6 | 白 | 5 : 1 |
| `--color-tram` | Tram（Spåra） | #008741 | 白 | 4.6 : 1 |
| `--color-brick` | Brick（Tiili） | #bd2719 | 白 | 6.1 : 1 |
| `--color-metro` | Metro | #fd4f00 | black-90 | 5.2 : 1 |
| `--color-summer` | Summer（Kesä） | #ffc61e | black-90 | 11.1 : 1 |
| `--color-engel` | Engel | #ffe977 | black-90 | 14.3 : 1 |
| `--color-suomenlinna` | Suomenlinna | #f5a3c7 | black-90 | 9.1 : 1 |
| `--color-copper` | Copper（Kupari） | #00d7a7 | black-90 | 9.4 : 1 |
| `--color-fog` | Fog（Sumu） | #9fc9eb | black-90 | 10 : 1 |
| `--color-gold` | Gold（Kulta） | #c2a251 | black-90 | 7.1 : 1 |
| `--color-silver` | Silver（Hopea） | #dedfe1 | black-90 | 13.1 : 1 |

- 4.5 : 1 以上なら文字の大きさを問わず使えます。3 : 1 以上 4.5 : 1 未満は大きな文字（通常の太さで 18pt 以上、太字で 14pt 以上）だけです。
- **白地に文字や意味のある要素として置けるブランド色は、Bus（12 : 1）、Brick（6.1 : 1）、Coat of Arms（5 : 1）、Tram（4.6 : 1）だけです。** Metro は 3.3 : 1 で、大きな文字に限ります。それ以外のブランド色は、白地では面として使います。
- 各色に `-dark`、`-medium-light`、`-light` の変種があります。**変種をページの主色にしません。** 部品の状態（ホバーなど）と、情報の種類の区別にだけ使います。

### 状態色

状態の表示専用です。アクセントには使いません。

| トークン | 値 | 意味 | 例文（HDS） |
|---|---|---|---|
| `--color-info` | #0062b9 | 成功でも失敗でもない、役に立つ補足 | 新しいメッセージがあります |
| `--color-success` | #007a64 | 成功 | 送信が完了しました |
| `--color-alert` | #ffda07 | 注意を引くが、すぐの対応は不要 | 読み込みに時間がかかっています |
| `--color-error` | #b01038 | すぐの対応が必要 | 必須の項目が入力されていません |

それぞれに `-dark` と `-light` があります。通知では `-light` を背景に、基本色を左の帯に使います。

色だけで状態を伝えません。文字かアイコンを必ず添えます。

### グレー

`--color-black` から `--color-black-5` まで 10% 刻みと、`--color-white` です。

- 本文の既定は `--color-black-90`（#1a1a1a）です。
- **白地の文字に使えるのは `--color-black-60`（#595959）まで**です。`--color-black-50` 以下は白地でコントラスト不足になります。薄いグレーは、暗い背景の上か、無効な要素の色に使います。

### フォーカス

- `--color-focus-outline`（#0072c6、Coat of Arms と同じ）の 3px の輪郭線が既定です。白地で 5 : 1 です。
- 暗い背景では白の輪郭線にします。HDS にダークモードは無いので、暗い面に部品を置くときは自分で確かめます。
- 狭い部品の内側では 2px の細い輪郭線を使えます。

### 色を差し替えるとき

HDS の FAQ にある目安です。

1. 既定が黒か白の箇所は、黒・白・グレーの中で差し替えます。
2. 既定がブランド色の箇所は、別のブランド色に差し替えます。

差し替えたら、コントラストを計算し直します。

## 文字

### 文字色

黒（`--color-black-90`）か白（`--color-white`）のどちらかを、背景に合わせて使います。他の色の文字は、意図があるときだけです。

### 見出しの大きさ

見出しのトークンは h1〜h6 に固定されていません。二つの尺度があり、サービスに合わせて選びます。

| 見出し | 既定の尺度（デスクトップ） | 小さい尺度（モバイル、業務画面） |
|---|---|---|
| h1 | `--fontsize-heading-xxl` 64px | `--fontsize-heading-xl-mobile` 40px |
| h2 | `--fontsize-heading-xl` 48px | `--fontsize-heading-l` 32px |
| h3 | `--fontsize-heading-l` 32px | `--fontsize-heading-m` 24px |
| h4 | `--fontsize-heading-m` 24px | `--fontsize-heading-s` 20px |
| h5 | `--fontsize-heading-s` 20px | `--fontsize-heading-xs` 18px |
| h6 | `--fontsize-heading-xs` 18px | `--fontsize-heading-xxs` 16px |

見出しの階層は意味どおりに使います（h1 の次は h2）。見た目だけ変えたいときは、構造を変えずにトークンで大きさを変えます。

### 本文の大きさ

| トークン | 値 | 使いどころ |
|---|---|---|
| `--fontsize-body-xl` | 20px | 短い導入文、副題の強調 |
| `--fontsize-body-l` | 18px | デスクトップの本文の既定。入力欄など主要な部品の文字 |
| `--fontsize-body-m` | 16px | モバイルの本文の既定。文字量の多い画面ではデスクトップでもこれ |
| `--fontsize-body-s` | 14px | データの多い画面で場所を節約するとき。状態ラベルなど部品の中 |

- まず 16px から始めます。**16px がヘルシンキのサービスの本文の最小値**で、どの画面幅でも使えます。
- 文字量が少ないサービスなら 18px を既定にし、`--breakpoint-s` 以下では 16px に落とします。
- 14px は補助的な文字と部品の中だけです。

### 行の高さ

| トークン | 比率 | 使いどころ |
|---|---|---|
| `--lineheight-s` | 1 | 大きな見出し、1行で収まる部品の文字 |
| `--lineheight-m` | 1.2 | リード文、2〜3文までの短い段落 |
| `--lineheight-l` | 1.5 | 長い本文。複数行になる部品の文字 |
| `--lineheight-xl` | 1.75 | 小さい文字、引用など強調したい文 |

HDS の見出しと本文のトークンは、行の高さが 4pt グリッドに乗るように決めてあります。

### 太さ

| 太さ | 使いどころ |
|---|---|
| 400（Regular） | 本文の既定 |
| 500（Medium） | ボタンやフォームなど、部品のラベル |
| 700（Bold） | 文の強調 |

見出しの太さは HDS の文書に指定がありません。このスキルでは 700 を既定にしています。

## 余白

### 原則

- 小さい余白で要素をまとめ、大きい余白で分けます。近いものは関係があるように見えます。
- 余白が広い要素ほど重要に見えます。
- ブランドや広報の画面は広く、情報量の多い業務画面は詰めます。サービスの機能と内容に合わせます。

### 二つの系統

| 系統 | 用途 | 値 |
|---|---|---|
| `--spacing-*` | 部品の内側と部品同士。細かい調整 | 2、4、8、12、16、24、32、40、48、56、64、72px |
| `--spacing-layout-*` | ページの構成。詰めすぎを防ぐ | 16、24、32、48、64、96、128px |

値は偶数倍と偶数分の一で増減できます。中間の値は作りません。

### グリッド

- 12 カラム、最大幅 1200px です。ヘッダーだけ 1440px まで広げられます。
- ガターは 24px。モバイル（`--breakpoint-s` 以下）では 16px、最小では 12px です。
- カラム数は幅で変わります。xs と s は 4、m は 8、l 以上は 12 です。

## 影

**影はヘルシンキのブランドの一部ではありません。** HDS の文書にそう明記されています。

- 要素の高さ（エレベーション）を表すために影を使いません。
- 目立たせるために影を使いません。
- 文字には影を付けません。
- 効果としての影を使いません。

使うのは、ほかの内容の上に重なる要素（トースト通知、ダイアログ）を区別するときだけです。トークンは `--box-shadow-s`、`--box-shadow-m`、`--box-shadow-l` です。

## 出典

- HDS Foundation: Colour（Usage / Accessibility / Tokens）、Typography、Spacing、Shadow、Grid、FAQ の各ページ。原文は https://github.com/City-of-Helsinki/helsinki-design-system/tree/master/site/src/docs にあります。MIT License、Copyright (c) 2023 City of Helsinki。
- ヘルシンキ市 ビジュアルアイデンティティの案内「Use basic elements」: https://www.hel.fi/en/decision-making/information-on-helsinki/design-and-digitalisation/helsinki-brand-and-visual-identity/visual-identity-guidelines/use-basic-elements （色の名前の由来と、色の定義）
