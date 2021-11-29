## Nuxt.jsとは？
![image.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/965248/0345893e-4e68-e667-e7ff-b5138ed8bef1.png)

Nuxt.jsは、
Vue.js をベースにした JavaScript フレームワークです。
**「ナクスト」**と読みます。
間違えて「ヌクスト」と読む人がいますが、
間違いです。気をつけましょう。

**公式ドキュメント**
- [公式ドキュメント：英語](https://nuxtjs.org/)
- [公式ドキュメント：日本語](https://nuxtjs.org/ja/)


### Nuxt生誕
2016年にAlexandre Chopin（アレクサンドラ・ショパン）、
Sébastien Chopin（セバスチャン・ショパン）、
Pooya Parsa（プーヤ・パラサ）氏らによりリリースされました。

Nuxt.js（React.jsをベースにしたJavascriptフレームワーク）に触発されて作られたらしいです。
npmとyarnみたいな関係ですね。

2017年以降、Vue.jsとともに、飛躍。
Javascript戦国時代の突入です。

### Nuxtが使われているサイト例

実際にどういうサイトに使われているのか見てみましょう。
代表的な例を下記にまとめましたが、
もちろんこれ以外にもたくさんのサイトでNuxtが使われています。

####代表的なNuxt実用例

- [一休.com(ホテル予約サイト)](https://www.ikyu.com/)
- [amana recruit(リクルート)](http://recruit.amana.jp/)
- [ebook(漫画サイト)](https://ebookjapan.yahoo.co.jp/)
- [note](https://note.com/)
- [デジタル庁](https://www.digital.go.jp/)

デジタル庁にも使われているとはビックリです。

## Nuxtの特徴（メリット）
自分が調べた限りでのNuxtの特徴を羅列的にまとめてみました。

###学習面

- [学習コストが低い](#学習コストが低い)
- [環境構築が容易](#環境構築が容易)
- [日本語ドキュメントが多い](#日本語ドキュメントが多い)

###機能面

- [SEOへの悪影響を小さく留めることができる](#seoへの悪影響を小さく留めることができる)
- [通信速度が速い（Code splitting）](#通信速度が速いcode-splitting)
- [SSR(サーバーサイドレンダリング)](#ssrサーバーサイドレンダリング)
- [PWAモジュールが用意されているので、PWA対応できる](#pwaモジュールが用意されているのでpwa対応できる)

###実装面

- [ルーティングが簡単に設定（ルーティングの自動生成）](#ルーティングが簡単に設定ルーティングの自動生成)
- [３つのモードで柔軟なサイト設計ができる](#３つのモードで柔軟なサイト設計ができる)
- [metaタグの管理をJavascriptのオブジェクトベースで記載できる](#metaタグの管理をjavascriptのオブジェクトベースで記載できる)
- [npm(yarn)のパッケージを利用できる](#npmyarnのパッケージを利用できる)
- [独自にパッケージが利用できる](#独自のパッケージを利用できる)

###その他
- [コミュニティによる改善](#コミュニティによる改善)


###学習コストが低い
Nuxtは学習コストが低い、、、みたいです。
これは賛否両論あるかと思うのですが、
個人的にはやはりVue経験者に限るって付け足したいですね。

バイク免許取るのに車の免許持っていた方が有利なのに似てる。
###環境構築が容易
Nuxt.jsは簡単に環境構築することができます。
特にこだわりがなければ、特定のディレクトリに移動して、
下記を実行するだけで、使えるようになります。

```
npx create-nuxt-app <project-name>
```
※これを実行するのにnpmのインストールが必要です。

###日本語ドキュメントが多い
かなりモダンなNuxtですが、意外にも日本語ドキュメントが多いです。
公式ドキュメントも日本語版があり、ドキュメントの中でも読みやすい印象ですね。
とはいえ、Vueなどに比べたら、日本語ドキュメントは少ないので、
英語が読めるのはやはり有利です。（当たり前だけど）

[公式ドキュメント：日本語版](https://nuxtjs.org/ja/)

##SEOへの悪影響を小さく留めることができる
そもそもSEOとは？ってなるかと思うのですが、
要するに、デプロイされたWebサイトが
Googleの検索エンジンに認知されて、上位表示させるために
使われる評価基準みたいなものです。

Vueに対して、NuxtはSEOが強いと言われています。
理由としては、NuxtがSSR(サーバーサイドレンダリング)を利用しているからです。

###典型的なSPAの場合

####動作順序

1. DOMのロード
1. AJAXでバックエンドからデータを読み込む

上記の動作だと
SEOパーサー（解析作業）でDOM要素が全て読み込まれないので、
SEOに悪影響があるようです。

###SSR（サーバーサイドレンダリング）の場合

####動作順序

1. Vueのコンポーネントをサーバ上のHTML文字列にレンダリング
1. 直接ブラウザに送信
1. マークアップをクライアント上に提供

Nuxt（SSR）は上記の工程を踏みます。
そうすると、SEOパーサー（解析作業）で素早くDOM要素が読み込ます。
なので、SEOには対して悪影響が少ないみたいです。

とはいえ、SEOというのは、抽象的な概念なので、
何が正解で何が不正解というのは正確には測れません。
なので、キッパリと「Vueは、SEOが弱い」、「Nuxtは強い」
とも言い切れないと思います。

**参考記事**
[Vue.jsよりもNuxt.js：使うべき理由とタイミング](https://itnews.org/news_contents/nuxt-js-over-vue-js-when-should-you-use-it-and-why)

###通信速度が速い（Code splitting）
通信速度が速い理由として、Code splittingという仕組みがあります。

Code splittingの仕組みのおかげで、
必要としない余分なページをブラウザに渡す必要がないので、
パフォーマンスが向上します。
Code splittingに関しては本記事では深掘りしませんので、

興味のある方は調べてみてください。

**参考記事**
[ちゃんと理解するCodesplitting](https://qiita.com/seya/items/06b160adb7801ae9e66f)


###SSR(サーバーサイドレンダリング)
ウェブページのレンダリングをブラウザの代わりにサーバー上で行う、
画面の表示において有用なアプリケーションの機能です。

####SSRではない場合
ブラウザ上でレンダリングを行うため、ページの読み込みに時間がかかる

####SSRの場合
レンダリングをサーバ上で行うので、ページの読み込みに時間がかからない

###PWAモジュールが用意されているので、PWA対応できる

PWAとは、
モバイル端末でウェブサイトを表示するときに、
ネイティブアプリのような動作を可能にする仕組みのことです。
Webサイトがアプリのように動くってイメージでいいと思います。

####機能例

- プッシュ通知
- アイコンのホーム画面の表示
- オフラインでの使用

###ルーティングが簡単に設定（ルーティングの自動生成）
> 自動的に生成されるルート
多くのウェブサイトでは単一のページではなく、複数ページ (例えばホームページ、概要ページ、お問い合わせページなど) を持っています。これらのページを表示するにはルーターが必要です。そこで vue-router の出番です。Vue アプリケーションで動作させる際に、設定ファイル(例えば、router.js)を設定し、全てのルートを手動で追加しなければなりません。Nuxt では pages ディレクトリにある Vue ファイルに基づいて、vue-router の設定を自動的に生成します。つまり、ルーターの設定を書く必要はもうありません！ Nuxt はまた全てのルートに対して自動でコード分割を行います。
つまり、アプリケーションでルーティングを行うのに必要なことは pages フォルダに .vue ファイルを作成するだけです。

上記は、[公式ドキュメント：ルーティング](https://nuxtjs.org/ja/docs/get-started/routing/)の引用です。

####ルーティング方法（Vueとの比較）

####Vueの作業
1. Vueファイルを作成する
2. 設定ファイル（router.js）などにパスの設定を記述

####Nuxtの作業
1.Vueファイルを作成する

あら不思議。Vueファイルを作るだけでルーティングが行えます。

###３つのモードで柔軟なサイト設計ができる
Nuxtには3つのモードが用意されています。

- Universal App（SSR)
- Single Page App（SPA）
- Static App（プリレンダリング）

####Universal App (SSR)
Nuxtの伝家の宝刀、サーバーサイドレンダリング（SSR）モードです。
メリットとしてSEOに強いとかページの読み込みが速いとかがあります。

####Single Page App（SPA）
通常のVueスタイルですね。
シングルページアプリケーションとして、機能します。
レンダリングは、クライアント側で行われるので、
読み込みに少し時間がかかる傾向にあります。

####Static App(プリレンダリング)
SSRとの違いは、htmlファイルの生成タイミングです。
SSRはクライアントからリクエストがあったときに作成しますが
Static App(プリレンダリング)はビルドのときに
ページごとのhtmlファイルを生成します。

ページによってモードが切り替えられるので便利です。



###metaタグの管理をJavascriptのオブジェクトベースで記載できる

nuxt.config.jsにhead内の設定（metaタグとか）を記述できます。

下記は[公式ドキュメント：メタタグとSEO](https://nuxtjs.org/ja/docs/features/meta-tags-seo/)の引用です。
> 
```
export default {
  head: {
    title: 'my website title',
    meta: [
      { charset: 'utf-8' },
      { name: 'viewport', content: 'width=device-width, initial-scale=1' },
      {
        hid: 'description',
        name: 'description',
        content: 'my website description'
      }
    ],
    link: [{ rel: 'icon', type: 'image/x-icon', href: '/favicon.ico' }]
  }
}
```

オブジェクトにまとめるとわかりやすいですなぁ。

###npm(yarn)のパッケージを利用できる
当然といえば、当然ですが、npm(yarn)のパッケージが使えます。
これはVueも同様です。

パッケージは
Nuxtチームとコミュニティの方々がたくさん作成してくれています。
感謝感激なんとやらですね。
[nuxtで使えるパッケージ一覧](https://modules.nuxtjs.org/)

###独自のパッケージを利用できる
独自のパッケージを作ることもできます。
npm モジュールとしてパッケージ化してもよし。
プロジェクトのソースコードに直接含めるもよし。

**詳しくは**
[公式ドキュメント:モジュールディレクトリ](https://nuxtjs.org/ja/docs/directory-structure/modules/#%E7%8B%AC%E8%87%AA%E3%81%AE%E3%83%A2%E3%82%B8%E3%83%A5%E3%83%BC%E3%83%AB%E3%82%92%E6%9B%B8%E3%81%8F)

###コミュニティによる改善
Vue.jsの普及を目的としたコミュニティも充実しています。

このコミュニティにより、
VueやNuxtの公式ドキュメントの翻訳や、プラグインの開発などが行われており、
VueやNuxtがより便利に使われるようになっております。

技術が日々進化しているのもこの方々のおかげとも言えます。

**公式ホームページ**
[Vue.js 日本ユーザーグループホームページ](https://vuejs-jp.org/)

## Nuxtのセットアップ

Nuxtのセットアップ手順をご紹介いたします。

###動作環境

- PC: MacBook Pro (13-inch, 2019, Two Thunderbolt 3 ports) インテルチップ
- MacOS: BigSur v11.6
- node: v14.18.1
- npm: v6.14.15
- nuxt: v2.15.8

### セットアップ手順
1. [特定のディレクトリに移動する](#1-特定のディレクトリに移動する)
1. [npx create-nuxt-app を実行する](#2-npx-create-nuxt-app-コマンドで環境を構築する)
1. [プロジェクトのディレクトリに移動する](#3-プロジェクトのディレクトリに移動する)
1. [npm run dev でアプリを起動させる](#4-npm-run-dev-でアプリを起動させる)

### 1. 特定のディレクトリに移動する
まず、自分が作業するディレクトリに移動します。
どこでも大丈夫です。

自分は、、、createというディレクトリの中にアプリを作っていきます。

```
sakatsumemasato@sakatsumemasatonoMacBook-Pro create % 
```

### 2. npx create-nuxt-app コマンドで環境を構築する

#### 2-1 npx create-nuxt-appを実行する

```
% npx create-nuxt-app nuxt-practice
```
このコマンドを実行することで、
nuxtのアプリに必要な環境を揃えてくれます。
手動で環境を作ることもできますが、特にこだわりがなければ、
このコマンドを使用しましょう。

**注意点**

- 「nuxt-practice」はディレクトリの名前です。これはどんな名前でも大丈夫です。
- 「npx　create-nuxt-app」はnpm v6.1 以上がインストールされていることが前提条件です。

####2-2 プロジェクト名を入力する
npx　create-nuxt-appをしたらいくつか質問が来るので、
自分の構築したい環境に合わせて回答しましょう。

まず、最初の質問ですが、プロジェクトの名前が聞かれます。

```
? Project name: (nuxt-practice)
```

特にこだわりがなければ、ディレクトリの名前と同じでいいです。

```
? Project name: nuxt-practice
```
入力してEnterを押します。

####2-3 Javascriptの種類を選択する

Javascriptの種類が聞かれるので、
作りたい環境に合わせて選択しましょう。

```
? Programming language:
❯ JavaScript
  TypeScript
```

**選択項目**

- Javascript
- TypeScript

今回は、Nuxtの学習に集中したいので、**「Javascript」**を選択肢します。

####2-４ パッケージマネージャーの種類を選択する

パッケージマネージャーの種類が聞かれるので、
好みで選択しましょう。

```
? Package manager: (Use arrow keys)
❯ Yarn
  Npm
```
**選択項目**

- Yarn
- Npm

今回は**「npm」**を使用します。

####2-5 UI(デザイン)フレームワークの種類を選択する

UI(デザイン)で使うフレームワークについて聞かれます。
必要な場合は、その項目を選択しましょう。
不要な場合は「None」を選択しましょう。

```
? UI framework: (Use arrow keys)
❯ None
  Ant Design Vue
  BalmUI
  Bootstrap Vue
  Buefy
  Chakra UI
  Element
  Framevuerk
  Oruga
  Tachyons
  Tailwind CSS
  Windi CSS
  Vant
  View UI
  Vuetify.js
```


**選択項目**

- None
- [Ant Design Vue](https://antdv.com/docs/vue/introduce-cn/)
- [BalmUI](https://material.balmjs.com/#/)
- [Bootstrap Vue](https://bootstrap-vue.org/)
- [Buefy](https://buefy.org/)
- [Chakra UI](https://chakra-ui.com/)
- [Element](https://element.eleme.io/#/en-US)
- [Framevuerk](https://framevuerk.com/)
- [Oruga](https://oruga.io/)
- [Tachyons](https://tachyons.io/)
- [Tailwind CSS](https://tailwindcss.com/)
- [Windi CSS](https://windicss.org/)
- [Vant](https://youzan.github.io/vant/#/en-US/)
- [View UI](https://www.iviewui.com/)
- [Vuetify.js](https://vuetifyjs.com/ja/)

上記のフレームワークの公式サイトのリンクを貼りましので、
興味のある方は、クリックして、調べてみてください。

今回は、**「None」**を選択します。

####2-6　任意のモジュールを選択する

任意のモジュールを入れるか聞かれます。
選択すると対応するパッケージがインストールされます。
こちらは複数選択可能です。

```
? Nuxt.js modules: (Press <space> to select, <a> to toggle all, <i> to invert selection)
❯◯ Axios - Promise based HTTP client
 ◯ Progressive Web App (PWA)
 ◯ Content - Git-based headless CMS
```

**※操作**

スペースキー:選択
aキー:全て選択
iキー:選択を反転する

**選択項目**

- Axios - Promise based HTTP client
- Progressive Web App (PWA)
- Content - Git-based headless CMS

**Axios**
「nuxtjs/axios」というパッケージがインストールされます。
axiosは、Ajax通信を簡単に行うことができるJavascriptライブラリのことです。

**Progressive Web App (PWA)**
「nuxt pwa」というパッケージがインストールされます。
PWAに対応したサイトが作れるようになるようです。

**Content - Git-based headless CMS**
「nuxt/content」というパッケージがインストールされます。
Nuxtでマークダウン形式のファイルをCMS風に使用するためのパッケージらしいです。


今回は**「Axios」**だけを選択します。

####2-7　Lint（コードチェック・コード整形）ツールを選択する

Lintツールについて聞かれます。
こちらも複数選択可能です。

```
Linting tools: (Press <space> to select, <a> to toggle all, <i> to invert selection)
❯◯ ESLint
 ◯ Prettier
 ◯ Lint staged files
 ◯ StyleLint
 ◯ Commitlint
```

**選択項目**

- ESLint
- Prettier
- Lint staged files
- StyleLint
- Commitlint

**ESLint**
コードを静的に分析/修正/カスタマイズするツール

**Prettier**
ソースコードを整形してくれるツール

**Lint staged files**
git commitする際に、eslintによるチェックを行うツール　
huskyというパッケージとセットで使われることが多いです。

**StyleLint** 
CSSのためのLintツール

**Commitilint**
gitにおけるコミットメッセージを特定のフォーマットのみに制限するできるツール

今回は、**「ESlint」**だけ選択します。


#### 2-8　テスティングフレームワークを選択する

テスティングのフレームワークを聞かれます。

```
? Testing framework: (Use arrow keys)
❯ None
  Jest
  AVA
  WebdriverIO
  Nightwatch
```

**選択項目**

- None
- Jest
- AVA
- WebdriverIO
- Nightwatch

**Jest**
シンプルさを重視した、快適な JavaScript テスティングフレームワーク

**AVA**
サイズが軽量で並列処理で高速で動作するJavascriptテスティングフレームワーク

**WebdriverIO**
Node.js用の次世代ブラウザとモバイル自動化テストフレームワーク

**Nightwatch**
Node.jsで記述された、
WebアプリケーションおよびWebサイト向けの統合された使いやすいエンドツーエンドのテストソリューション

今回はテストしないので、**「None」**を選択します。

####2-9 ページの種類を選択する

作成するページの種類について聞かれます。

```
Rendering mode: (Use arrow keys)
❯ Universal (SSR / SSG)
  Single Page App
```

**選択項目**

- Universal (SSR / SSG)
- Single Page App

**Universal (SSR / SSG)**
SSR(サーバーサイドでレンダリング)/SSG（スタティックサイトジェネレーション）を使用する

**Single Page App**
SPA（シングルページアプリケーション）を使用する（Vueと同じ）

今回は、Nuxtの機能をチェックしたいので、
**「Universal (SSR / SSG)」**を選択します。

####2-10 デプロイ先を選択する

```
? Deployment target: (Use arrow keys)
❯ Server (Node.js hosting)
  Static (Static/Jamstack hosting)
```

**選択項目**

- Server (Node.js hosting)
- Static (Static/Jamstack hosting)

**Server (Node.js hosting)**
> サーバーホスティングとは、Node.jsサーバーでNuxtを実行することを意味します。ユーザーがページを開くと、ブラウザはサーバーにそのページを要求します。Nuxtはリクエストを処理し、ページをレンダリングして、結果のページとそのすべてのコンテンツを送り返します。

**Static (Static/Jamstack hosting)**
> Nuxtは静的サイトジェネレーターとしても機能します。Nuxtアプリケーションを静的にレンダリングし、サーバーなしでユニバーサルアプリのすべてのメリットを享受できます。このnuxt generateコマンドは、Webサイトの静的バージョンを生成します。ルートごとにHTMLを生成し、dist/ディレクトリ内の独自のファイル内に配置します。これにより、パフォーマンスが向上し、SEOとオフラインサポートが向上します。

引用：[Nuxt-展開ターゲット](https://nuxtjs.org/docs/features/deployment-targets/)

今回は、ちょっとよくわからなかったので、**「Server (Node.js hosting)」**を選択しておきます。

####2-11 開発用ツールを選択する

開発用ツールについて聞かれます。
こちらも複数選択できます。

```
? Development tools: (Press <space> to select, <a> to toggle all, <i> to invert selection)
❯◯ jsconfig.json (Recommended for VS Code if you're not using typescript)
 ◯ Semantic Pull Requests
 ◯ Dependabot (For auto-updating dependencies, GitHub only)
```

**選択項目**

- jsconfig.json (Recommended for VS Code if you're not using typescript)
- Semantic Pull Requests
- Dependabot (For auto-updating dependencies, GitHub only)

**jsconfig.json (Recommended for VS Code if you're not using typescript)**
VSCode(Visual Studio Code)で開発する際は入れたほうが良いらしい。

**Semantic Pull Requests**
commitのメッセージとPull Requestにおけるタイトルのつけ方をチェックしてくれる。

**Dependabot (For auto-updating dependencies, GitHub only)**
package.jsonやgo.modといったマニュフェストファイルをみて古いライブラリやセキュアでないもの（安全でないもの）を調べてくれる。


今回は、**「jsconfig.json (Recommended for VS Code if you're not using typescript)」**だけを
選択します。

####2-12　継続的インテグレーションを選択する

継続的インテグレーションについて聞かれます。
継続的インテグレーションとは、
> 開発者が自分のコード変更を定期的にセントラルリポジトリにマージし、その後に自動化されたビルドとテストを実行する DevOps ソフトウェア開発の手法

つまり、何かアクションが起きた時（プッシュやマージした時）に、
自動的にビルドやテストを実行してくれる機能です。

引用：[継続的インテグレーションとは？](https://aws.amazon.com/jp/devops/continuous-integration/#:~:text=%E7%B6%99%E7%B6%9A%E7%9A%84%E3%82%A4%E3%83%B3%E3%83%86%E3%82%B0%E3%83%AC%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AF%E3%80%81%E9%96%8B%E7%99%BA,%E3%82%BD%E3%83%95%E3%83%88%E3%82%A6%E3%82%A7%E3%82%A2%E9%96%8B%E7%99%BA%E3%81%AE%E6%89%8B%E6%B3%95%E3%81%A7%E3%81%99%E3%80%82)

```
? Continuous integration: (Use arrow keys)
❯ None
  GitHub Actions (GitHub only)
  Travis CI
  CircleCI
```

**選択項目**

- None
- GitHub Actions (GitHub only)
- Travis CI
- CircleCI

**GitHub Actions (GitHub only)**
githubでの動作をトリガーとして、テストやビルドなどを自動的に行ってくれる

**Travis CI**
GitHubと連携した自動テスト実行サービス、最小限の設定のみでCIを導入できるのが特徴

**CircleCI**
Saas型のCI/CDサービス

今回はCIは関係ないので、**「None」**を選択します。

####2-13 バージョン管理システムを選択する

```
? Version control system: (Use arrow keys)
❯ Git
  None
```

**選択項目**

- Git
- None

Gitを使ってコード管理するので**「Git」**を選択します。

### 環境構築完了

下記が出たら成功です！！

```
🎉  Successfully created project nuxt-practice
```

lsコマンドで確認してみると、

```
% ls
nuxt-practice
```
ディレクトリができています。

**ちなみに今回のオプションのまとめ**

```
create-nuxt-app v3.7.1
✨  Generating Nuxt.js project in nuxt-practice
? Project name: nuxt-practice
? Programming language: JavaScript
? Package manager: Npm
? UI framework: None
? Nuxt.js modules: Axios - Promise based HTTP client
? Linting tools: ESLint
? Testing framework: None
? Rendering mode: Universal (SSR / SSG)
? Deployment target: Server (Node.js hosting)
? Development tools: jsconfig.json (Recommended for VS Code if you're not using typescript)
? Continuous integration: None
? Version control system: Git
```

###3 プロジェクトのディレクトリに移動する

先ほど、npx-nuxt-appで作ったディレクトリに移動します。

```
cd nuxt-practice
```

###4 npm run dev でアプリを起動させる

下記のコマンドで、アプリを起動させます。

```
npm run dev
```

```
> nuxt


   ╭───────────────────────────────────────╮
   │                                       │
   │   Nuxt @ v2.15.8                      │
   │                                       │
   │   ▸ Environment: development          │
   │   ▸ Rendering:   server-side          │
   │   ▸ Target:      server               │
   │                                       │
   │   Listening: http://localhost:3000/   │
   │                                       │
   ╰───────────────────────────────────────╯

ℹ Preparing project for development                                                                                                                                                               20:04:11
ℹ Initial build may take a while                                                                                                                                                                  20:04:11
ℹ Discovered Components: .nuxt/components/readme.md                                                                                                                                               20:04:11
✔ Builder initialized                                                                                                                                                                             20:04:11
✔ Nuxt files generated                                                                                                                                                                            20:04:11

✔ Client
  Compiled successfully in 5.14s

✔ Server
  Compiled successfully in 4.63s

ℹ Waiting for file changes                                                                                                                                                                        20:04:18
ℹ Memory usage: 254 MB (RSS: 360 MB)                                                                                                                                                              20:04:18
ℹ Listening on: http://localhost:3000/                                                                                                                                                            20:04:18

```
localhost:3000　にアクセスしてみましょう。
![スクリーンショット 2021-11-20 20.06.57.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/965248/fbc27160-5958-87ee-bb14-396f891623f8.png)

これが出たら、成功🎉

###Nuxtのディレクトリ構造

```
root/
    │─ .nuxt
    │─ components
    │─ node_modules
    │─ pages
    │─ static
    │─ store
    │─ .editorconfig
    │─ .eslintrc.js
    │─ .gitignore
    │─ jsconfig.json
    │─ nuxt.config
    │─ package-lock.json
    │─ package.json
    │─ README.md
```

今回はNuxt特有のものだけ簡単に紹介します。
#### .nuxt
ビルドディレクトリ。
devやbuildコマンドを再度実行すると、ここに保存されたものはすべて再生成される。
#### components
Vue.jsのコンポーネントを管理する。
#### pages
アプリケーションのビューファイル・ルーティングファイルを入れる。
#### static
変更される可能性が低い静的ファイルを置く。
#### store
Vuexストアのファイルを入れる
#### nuxt.config.js
Nuxt.jsのカスタム設定を記述するファイル

**詳しくは**
[ディレクトリ構造　-　Nuxt.js](https://develop365.gitlab.io/nuxtjs-2.8.X-doc/ja/guide/directory-structure/)


##NuxtでTodoアプリを作ってみた。
環境構築が終わったところで、簡単にTodoアプリを作っていきたいと思います。

今回作るTodoのデザインはこんな感じです。
![スクリーンショット 2021-11-23 13.15.01.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/965248/af5c9101-b756-06b5-15ce-ec16fb4eb6cb.png)

さて、やっていきましょう。


###作業手順


###1.使わないファイルを削除する
npx create-nuxt-appをすると、デフォルトで不要なファイルまで作成します。
いらないファイルは削除していきましょう。
あるとなんか鬱陶しいです。

　**今回使わないファイル**

- conponents/NuxtLogo.vue
- conponents/Tutorial.vue
- conponents/favicon.icon

###2.ポート番号を変更する
デフォルトでポート番号が3000になっているのですが、
これだと何やら、動きが遅かったので、
ポート番号を8000に変えました。
環境によって動きが遅い場合があるので、遅かったらポート番号を変えましょう。

ポートの変え方は、nuxt.config.jsにポート番号の設定を追加します。

```nuxt.config.js
server: {
    port: 8000 // default: 3000
  },
```
それで再度、npm run devしなおします。
そうすると、localhost:8000で動くようになります。
こうすることで、スムーズにNuxtが動くようになりました。
※localhost*3000で動くようならそのままでOK

###3.header部分の作成
まず、header部分を作成していきます。

####3-1 pagesを下記のように書きます。
templateのタグの中に、headerコンポーネントを入れています。

```pages/index.vue
<template>
  <header />
</template> 
```

####3-2 headerコンポーネントの作成
まだheaderコンポーネントが作成されていないので、
localhost:3000　にログインしても何も表示されません。
（エラーになります。）

なので、headerコンポーネントを作っていきます。

components/Header.vueを作成し、下記のように書きます。

```components/Header.vue
<template>
  <header>
    <div class="logo">
      <img src="logo.png" alt="logo" />
    </div>
  </header>
</template>

<style>
header {
  text-align: center;
}
</style>

```

今回、画像は、staticの中に入れました。
これでlocalhost:8000(3000)にアクセスします。

下記のように表示されます。
![スクリーンショット 2021-11-23 16.25.53.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/965248/31fd1a1f-d726-40fd-375f-038d491491e0.png)


headerができました。

###4.Todo部分の作成

Todo部分の作成部分ですが、
手順通りにひとつひとつ解説していくのは
骨の折れる作業で、さらに実装し終えてから記事を書いているので、
まとめるのも大変です。

ですので、今回は処理の流れのみ解説させてください（すいません。）

まず、出来上がったコードをご覧ください。

```pages/index.vue
<template>
  <div>
    <Header />
    <Todo />
  </div>
</template>
```
**components/Todo.vueのマークアップ部分**

```components/Todo.vue
<template>
  <section class="container">
    <div class="wrap">
      <div class="taskAdd">
        <input
          id="input"
          v-model="content"
          type="text"
          name="input"
          placeholder="タスクを入力してください"
        />
        <button @click="insert">
          追加
        </button>
      </div>
      <div class="filter">
        <div v-for="(btn, index) in buttons" :key="index" class="buttonWrap">
          <button :class="{'filterActiveBgColor' : btn.colorFlag}" @click="getfilter( index )">{{ btn.value }}</button>
        </div>
      </div>
      <div v-for="(todo,index) in getTodos" :key="index" class="task">
        <div class="taskWrap">
          <p class="taskContent" :class="{'completeContent' : todo.state }">
            {{ todo.content }}
          </p>
          <button :class="{'completeButton' : todo.state }" @click="changeState({ todo, index })">
            完了
          </button>
        </div>
      </div>  
    </div>
  </section>
</template>
```
**components/Todo.vueのスクリプト部分**

```components/Todo.vue
<script>
export default {
  data() {
    return {
      content: '',
      button: '',
      buttons: [
        { value: '全て', colorFlag: true },
        { value: '完了', colorFlag: false },
        { value: '未完了', colorFlag: false }
      ]
    }
  },
  computed: {
    getTodos() {
      const button = this.button
      const allTodos = this.$store.getters.getTodos
      const completeTodos = allTodos.filter(todo => (todo.state === true))
      const notCompleteTodos = allTodos.filter(todo => (todo.state === false))
      if (button === '完了') {
        return completeTodos
      } else if (button === '未完了') {
        return notCompleteTodos
      } else {
        return allTodos
      }
    }
  },
  methods: {
    insert() {
      if (this.content !== '') {
        this.$store.commit('insert', { content: this.content })
        this.content = ''
      } else {
        alert('タスクが入力されていません。')
      }
    },
    changeState(todo) {
      this.$store.commit('changeState', todo)
    },
    getfilter(index) {
      this.button = this.buttons[index].value

      const changeButtonsColorFlag = this.buttons.map((button, i) => {
        return {
          ...button,
          colorFlag: index === i
        }
      })

      this.buttons = changeButtonsColorFlag
    }
  }
}

</script>
```

**components/Todo.vue　スタイル部分**

```components/Todo.vue
<style>
.container {
  height: 100vh;
  background-color: #f3f3f3;
  padding:100px 0;
}

.wrap {
  width:50%;
  margin:0 auto;
}

/* input */

.taskAdd {
  display:flex;
  justify-content: space-between;
  height:35px;
  margin-bottom:50px;
}

.taskAdd input {
  width:80%;
}

.taskAdd button {
  width:10%;
}

/* filter */

.filter {
  margin-bottom:10px;
  display: flex;
}

.filter button {
  border-radius: 10px 10px 0 0;
  width:100px;
  height:30px;
}

/* task */

.task {
  border-bottom:1px solid #000;
  padding:30px 0;
}

.taskWrap {
  display:flex;
  justify-content: space-between;
  align-items: center;
  width:80%;
}

.task .taskContent {
  width:82%;
}

.task button {
  width:15%;
  height: 35px;
  border-radius: 20px;
}

/* task toggle style */

.completeContent {
  text-decoration: line-through;
}

.completeButton {
  background-color: #707070;
}

/* filter avtive style  */

.filterActiveBgColor {
  background: #fff;
}
</style>
```
**Vuexの部分(state管理)**

```store/index.js
import Vuex from 'vuex'

const createStore = () => {
  return new Vuex.Store({
    state: {
      todos: []
    },
    getters: {
      getTodos: state => state.todos
    },
    mutations: {
      insert(state, obj) {
        state.todos.unshift({
          content: obj.content,
          state: false,
          status: '未完了'
        })
      },
      changeState(state, obj) {
        obj.todo.state = !state.todos[obj.index].state
      }
    }
  })
}

export default createStore
```

続いて、大まかな作成手順と解説（処理の流れ）を行います。

####4-1 ファイルの作成
まず、必要ファイルの作成を行います。

- components/Todo.vue ⇨　Todo（タスク管理）機能を行うコンポーネント
- store/index.js　⇨　state(状態管理)を行うファイル(vuex)

今回は、state管理にvuexを使います。

詳しくは：[vuexとは何か？|Vuex](https://vuex.vuejs.org/ja/)

####4-2 pages/index.vueにTodoコンポーネントを追加

Headerの下にTodoコンポーネントを付け加えます。
その際、コンポーネントが二つ以上になると、エラーになるので、
Headerと、Todoをdivタグで囲みましょう。

これでTodoコンポーネントを作成したら、ページに表示されるようになります。
まだ作成してないので、エラーが出ていると思いますが、気にせず次に進みます。

```pages/index.vue
<template>
  <div>
    <Header />
    <Todo />
  </div>
</template>
```

####4-3　Todo タスク追加機能（解説）

すいません、こちらから解説のみとさせていただきます。
もし作りたい方は
処理は上記にまとめてあるので、そこを参考にするか、
自分の[github](https://github.com/masato5579/nuxt-practice)を参考に作成してみてください。

Todoのタスクを追加する機能です。
一般的な、Inputタグに入力して、ボタンを押すとタスクが入力されるやつです。
![bbbb.gif](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/965248/971e2a24-0bbc-62a5-e14f-a689926daa6d.gif)


**処理の流れ**
① 追加ボタンを押す
② methodのinsertが実行される
③ 文字がInputタグに入力されていたら、store/index.js(vuex)にcontentを渡す
④ store/index.jsのinsertが実行される
stateの⑤todos（配列）にcontentを含めたobjectを格納
オブジェクトの形式
{ content: obj.content, state: false, status: '未完了' }
⑥ gettersのgetTodosが更新される
⑦ computedのgetTodos()が更新される（今回は、allTodosがgetTodosにかえる）
⑧ getTodosの中のオブジェクトの一覧をv-forで回して表示させる


```components/Todo.vue
-省略-
<div class="taskAdd">
  <input
    id="input"
    v-model="content"
    type="text"
    name="input"
    placeholder="タスクを入力してください"
    />
------①------
   <button @click="insert">
     追加
   </button>
</div>
-----省略-----
------⑧------
<div v-for="(todo,index) in getTodos" :key="index" class="task">
    <div class="taskWrap">
       <p class="taskContent" :class="{'completeContent' : todo.state }">
          {{ todo.content }}
       </p>
       <button :class="{'completeButton' : todo.state }" @click="changeState({ todo, index })">
         完了
       </button>
     </div>
 </div>
-----省略-----
<script>

export default {
  data() {
    return {
      content: '',
    }
  },
computed: {
------⑦------
    getTodos() {
      const button = this.button
      const allTodos = this.$store.getters.getTodos
      const completeTodos = allTodos.filter(todo => (todo.state === true))
      const notCompleteTodos = allTodos.filter(todo => (todo.state === false))
      if (button === '完了') {
        return completeTodos
      } else if (button === '未完了') {
        return notCompleteTodos
      } else {
        return allTodos
      }
    }
 },
  methods: {
------②------
    insert() {
      if (this.content !== '') {
------③------
        this.$store.commit('insert', { content: this.content })
        this.content = ''
      } else {
        alert('タスクが入力されていません。')
      }
    },
  }
}

-----省略-----

</script>
```

```store/index.js
import Vuex from 'vuex'

const createStore = () => {
  return new Vuex.Store({
------⑤------
    state: {
      todos: []
    },
------⑥------
    getters: {
      getTodos: state => state.todos
    },
    mutations: {
------④------
      insert(state, obj) {
        state.todos.unshift({
          content: obj.content,
          state: false,
          status: '未完了'
        })
      }
    }
  })
}

export default createStore
```

####4-4　Todo status更新機能

追加したTodoタスクとセットで完了ボタンを設置して、
ボタンを押したら、タスクが完了するというstatus更新機能の解説です。
今回は、完了（完了済）になったボタンの背景色を変更、タスクのcontentに取り消し線を引くスタイルを当てます。
![aaaa.gif](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/965248/44827835-1738-e383-e523-4185da8e3e25.gif)

**処理の流れ**
① 完了ボタンをクリックする
② methodのchangeStateが発火して、引数のtodo(配列)をstore/index.js(vuex)に渡す
③ store/index.jsのmutationsのchangeStateが発火して、stateが更新される
下記の処理で、stateを反対にする（toggle的な処理）
obj.todo.state = !state.todos[obj.index].state
つまり、state.todos[obj.index].stateがtrueの時はfalse、falseの時は、trueにする（④）
④ stateのtodos（配列）が変更される（state.todos[].stateの部分）
{ content: obj.content, **state: true**, status: '未完了' }
⑤ gettersのgetTodosが更新される
⑥ stateが更新されたので、Todo.vue/getTodosが実行される
⑦ computedのgetTodos()が更新されてcontent画面に表示される
⑧ todo.stateがtrueになっているものに関してはスタイルを当てている
⑨ ⑧のスタイル


```components/Todo.vue
-----省略-----
 <div v-for="(todo,index) in getTodos" :key="index" class="task">
   <div class="taskWrap">
------⑦------
      <p class="taskContent" :class="{'completeContent' : todo.state }">
        {{ todo.content }}
      </p>
------①------
      <button :class="{'completeButton' : todo.state }" @click="changeState({ todo, index })">
        完了
      </button>
   </div>
-----省略-----
<script>
computed: {
------⑥------
    getTodos() {
      const button = this.button
      const allTodos = this.$store.getters.getTodos
      const completeTodos = allTodos.filter(todo => (todo.state === true))
      const notCompleteTodos = allTodos.filter(todo => (todo.state === false))
      if (button === '完了') {
        return completeTodos
      } else if (button === '未完了') {
        return notCompleteTodos
      } else {
        return allTodos
      }
    }
 },
methods: {
-----省略-----
------②------
changeState(todo) {
      this.$store.commit('changeState', todo)
   },
}
-----省略-----
<script/>
```

```store/index.js
import Vuex from 'vuex'

const createStore = () => {
  return new Vuex.Store({
------④------
    state: {
      todos: []
    },
------⑤------
    getters: {
      getTodos: state => state.todos
    },
    mutations: {
------③------
      changeState(state, obj) {
        obj.todo.state = !state.todos[obj.index].state
      }
    }
  })
}

export default createStore
```

```components/Todo.vue
<style>
-----省略-----
/* task toggle style */
------⑨------
.completeContent {
  text-decoration: line-through;
}

.completeButton {
  background-color: #707070;
}
-----省略-----
</style>
```
####4-5　絞り込み機能

全て/完了/未完了のボタンでタスクを絞り込む機能です。

![status2.gif](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/965248/091bbab6-d100-7186-0b09-93fdff8d5f49.gif)

処理の流れ
① 全てor完了or未完了のボタンを押す
dataの②buttonsをv-forでループさせて表示させている
③ methodのgetfilterが実行される
- index番号に紐づいたbuttonsのvalueをdataのbuttonに格納する
- map関数でクリックしたbuttonsのcolorFlagをtrueにしてスタイルを変更する
④ ③のスタイル
⑤ computed/getTodosで格納されたbuttonのstateによってgetTodosの値を絞り込み
完了の場合：todo.state === trueのやつだけ値を返す
未完了の場合：todo.state === falseのやつだけ値を返す
それ以外：絞り込みしないでそのままの値を返す
⑥ 絞り込まれたgetTodosを画面上に表示

```components/Todo.vue
<template>
  <section class="container">
    <div class="wrap">
-----省略-----
------①------
      <div class="filter">
        <div v-for="(btn, index) in buttons" :key="index" class="buttonWrap">
          <button :class="{'filterActiveBgColor' : btn.colorFlag}" @click="getfilter( index )">
　　　　　　　　　　　　　　　　　　　　　{{ btn.value }}
　　　　　　　　　　　　　　　　　　　　</button>
        </div>
      </div>
-----省略-----
------⑥------
<div v-for="(todo,index) in getTodos" :key="index" class="task">
    <div class="taskWrap">
       <p class="taskContent" :class="{'completeContent' : todo.state }">
          {{ todo.content }}
       </p>
       <button :class="{'completeButton' : todo.state }" @click="changeState({ todo, index })">
         完了
       </button>
     </div>
 </div>
-----省略-----
</div>
  </section>
</template>
```

```components/Todo.vue
<script>

export default {
  data() {
    return {
      content: '',
      button: '',
------②------
      buttons: [
        { value: '全て', colorFlag: true },
        { value: '完了', colorFlag: false },
        { value: '未完了', colorFlag: false }
      ]
    }
  },
  computed: {
------④------
    getTodos() {
      const button = this.button
      const allTodos = this.$store.getters.getTodos
      const completeTodos = allTodos.filter(todo => (todo.state === true))
      const notCompleteTodos = allTodos.filter(todo => (todo.state === false))
      if (button === '完了') {
        return completeTodos
      } else if (button === '未完了') {
        return notCompleteTodos
      } else {
        return allTodos
      }
    }
  },
  methods: {
    insert() {
      if (this.content !== '') {
        this.$store.commit('insert', { content: this.content })
        this.content = ''
      } else {
        alert('タスクが入力されていません。')
      }
    },
    changeState(todo) {
      this.$store.commit('changeState', todo)
    },
------③------
    getfilter(index) {
      this.button = this.buttons[index].value

      const changeButtonsColorFlag = this.buttons.map((button, i) => {
        return {
          ...button,
          colorFlag: index === i
        }
      })

      this.buttons = changeButtonsColorFlag
    }
  }
}

</script>
```

```components/Todo.vue
<style>
-----省略-----
------④------
/* filter avtive style  */

.filterActiveBgColor {
  background: #fff;
}
</style>
```

##Nuxt.jsを使ってみての所感

Vueもろくに使えないまま、Nuxtの記事を書いているので、
不要な部分や、正しくない情報を書いているかもしれないので、
もし間違い等ありましたら、ご指摘よろしくお願いいたします。

感想としては、Vueがそもそもわからないので、便利なのかもわからないというのが正直な感想です。
Vueより表示速度が早いとかあると思いますが、正直わかるレベルまで到達していないので、
その点に関しては、ベテラン強強エンジニアさんの記事を読んでください。

長々と読んでいただきありがとうございました。
