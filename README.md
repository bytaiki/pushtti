# 本アプリ「Pushっち」の概要

GitHubリポジトリの開発と一緒に、キャラクターが育つChrome拡張機能。

コミットは餌、スターは成長の応援。開発を続けると、かわいい幼体が凛々しい姿へ進化します。長く開発が止まるとキャラも弱り、30日間餌がなければ、その世代の寿命を迎えます。

> 開発中です。以下は予定している機能と動作です。

- 公開リポジトリで「育てる」を押して育成を開始。
- コミットやスターの増加に応じて成長し、少し生意気なコメントで反応。
- 右下のボタンから、キャラの姿・育成状況・歴代キャラを確認。
- 育成データは利用中のChrome内に保存。

<a id="technologies"></a>

## 使われている技術

Chrome拡張機能がいつ動き、何を使ってキャラを表示・保存するのかを説明します。

育成ルールは [製品仕様](docs/specification.md)、開発の進め方は [開発計画](docs/development-plan.md) を参照してください。

| 技術・機能 | 担当すること | 主に使う時 |
| --- | --- | --- |
| [WXT](docs/chrome-extension.md#wxt) | 書いたプログラムをChrome拡張として組み立て、開発を助ける | 開発・ビルド時 |
| [Rive CLI](docs/rive.md#cli) | キャラの姿・動き・状態切り替えを制作し、キャラデータを出力する | キャラ制作時 |
| [Rive Webランタイム](docs/rive.md#web-runtime) | キャラデータを読み、ブラウザー内で描画・再生する | キャラ表示時 |
| [chrome.storage.local](docs/chrome-extension.md#storage-local) | 経験値や世代など、育成情報をChrome内に保存する | 育成開始・更新・表示時 |
| [IndexedDB](docs/chrome-extension.md#indexeddb) | 歴代キャラの画像をChrome内に保存する | 画像の保存・表示時 |

WXTとRive CLIは制作するための道具です。利用者がGitHubを見るたびにCLIを実行するわけではありません。

## 詳細説明

- [Chrome拡張機能：WXT・保存・動作タイミング](docs/chrome-extension.md)
- [Rive：CLIによる制作・Webランタイムによる描画](docs/rive.md)
