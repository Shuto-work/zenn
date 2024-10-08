---
title: "【新常識】VSCodeとZenn CLIで効率よくブログを公開する方法"
emoji: "📘"
type: "idea" # tech: 技術記事 / idea: アイデア
topics: [markdown,zennCLI,VSCode]
published: true
published_at: 2024-08-13 19:00 # 未来の日時を指定する
---

こんにちは！シュートです。

実は最近、コミュニティを通じて **「VSCodeでブログが書ける」** ことを知りました。**zenn CLI**をインストールすることで実現できるので、興味ある方はぜひご一読くださいませ。界隈ではそこまで珍しくないなのかなぁと思いつつも、自分のような新参者には目から鱗のような発見だったので、とても興奮しています...！笑

![](https://storage.googleapis.com/zenn-user-upload/2d825edfee9d-20240813.png)

## 公開までの手順
### 全体の流れ
<!-- ーーーーーーーーーーーーーーーーーーーーーーーーー -->
1. ZennとGitHubリポジトリを連携
2. Zenn CLIをインストール
3. `npx zenn init`でzenn用のディレクトリを構築
4. `npx zenn new:article`で記事を新規作成
5. 4で生成されたファイル内で、記事を書く
6. ソースコード一番上の`published: true`になっていることを確認
7. GitHub リポジトリへプッシュ
<!-- ーーーーーーーーーーーーーーーーーーーーーーーーー -->
### 具体的なやり方
詳細は、以下の公式ドキュメント等を参照してください。

https://zenn.dev/zenn/articles/editor-guide

https://zenn.dev/zenn/articles/zenn-cli-guide

https://zenn.dev/zenn/articles/install-zenn-cli

https://zenn.dev/zenn/articles/connect-to-github

インストールできたら、このようなコマンドで各種機能を実行できます。
![](https://storage.googleapis.com/zenn-user-upload/af1d7116fdd2-20240813.png)

## 実際にやってみた感想
実際使ってみて、「すごい！！」と思ったのは以下3点。
1. 同じ言葉を一括修正できる。
2. GitHubで変更管理ができる。
3. 実はスライドも作れる。

![](https://storage.googleapis.com/zenn-user-upload/89b2ba82c411-20240813.png)
### 1. 同じ言葉を一括修正できる。
macの場合ですが、修正したい言葉を選択した状態で`command + Shift + L`を押すと、一括選択＆修正が可能です。
VS Codeのようなエディターならではの機能なのですが、プログラムを書いている時はもちろん、自然言語の原稿においても大活躍です。
![](https://storage.googleapis.com/zenn-user-upload/a9eda2de6945-20240813.png)

### 2. GitHubで変更管理ができる。
当然ですが、zennとGitHubを連携させているので、GitHubで変更管理できます。
「リライトしたけど、やっぱり前回の書き方が良かったから戻したい」

そんな時は変更履歴から過去のバージョンに戻せばOK！
![](https://storage.googleapis.com/zenn-user-upload/cc75658628f7-20240814.png)

### 3. 実はスライドも作れる。
これまた衝撃で、Marpというツールを使えばVSCodeでスライドを作ることができます。
実際に見た方が早いですね。
![](https://storage.googleapis.com/zenn-user-upload/4c689a930dc9-20240813.png)

何が言いたいかというと、**原稿ツールとスライド作成ツールがセットになっているので、2ツール・2画面を往復しなくて良いのです。** 例えば、Googleメインで使っている人がスライドを作成する時、まずGoogle documentとGoogle slideの2つを開きますよね。VSCodeでは、その2つを同じ画面で作業できます。
より詳しい＆わかりやすい内容はこちらを参照してみてください。
https://zenn.dev/yasuna/articles/56c949ec54d2f6
## 最後に
ありがとうございました！
こんな感じで、学習記録＆アウトプットのために執筆しています。
伝わりにくい部分もあったかもしれませんが、気になる方はぜひ調べてみてください！

普段はフリーランスのDXプログラマー＆マークアップコーダーとして稼働しています！
現在、2社協業中！
https://shuto-work.notion.site/Profile-232ee534179a418cbd913d36204c00ae