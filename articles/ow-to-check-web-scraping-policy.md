---
title: "Webサイトでスクレイピングが禁止されているかどうか確認する方法"
emoji: "🌊"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: [Python, スクレイピング, 規約確認]
published: true
---

[こちらの記事](リンクのURL)でスクレイピングの概要を記述しました。
実際にスクレイピングの禁止チェックをする方法があります。
今回は、プログラムでチェックする方法を紹介します。

## ソースコード
```py:sample.py
import requests

def check_robots_txt(url):
    robots_url = url.rstrip('/') + '/robots.txt'
    try:
        response = requests.get(robots_url)
        if response.status_code == 200:
            print(f"robots.txt for {url}:")
            print(response.text)
            if 'Disallow' in response.text:
                print("Disallowed paths found in robots.txt")
            else:
                print("No disallowed paths found in robots.txt")
        else:
            print(f"No robots.txt file found at {robots_url}")
    except requests.RequestException as e:
        print(f"Error fetching robots.txt: {e}")

# 使用例
check_robots_txt('https://example.com')  # ここに対象のサイトURLを挿入
```

## 解説
```py
import requests
```
requestsというPythonライブラリをインポートしています。
これにより、PythonからWebサイトに情報を問い合わせたり、Webサイトからデータを収集したりすることができます。

スクレイピング以外でも、例えば天気サイトから天気の情報を集めたり、飲食店の口コミサイトからレビューを集めたりする際にもrequestsが役立ちます。
```py
def check_robots_txt(url):
```
仮引数の`(`url`)`に、実際のURLを挿入することで、対象サイトをチェックします、
```py
robots_url = url.rstrip('/') + '/robots.txt'
```
`rstrip('')`は、末尾の文字列を削除するメソッド。最後の`/`を削除し、`/robots.txt`を追加することで`https://example.com/robots.txt`など、対象サイトの`/robots.txt`にアクセスできる。
この処理を変数`robots_url`に代入。
```py
try:
 # 処理
except
 # 処理
```
エラーハンドリング処理。`try:`ブロック内ででエラーが出てきた場合の処理を、`except`ブロックで記述する。

```py
response = requests.get(robots_url)
```
robots_url内で描画されている情報を、レスポンスとして取得。
```py
if response.status_code == 200:{
  print(f"robots.txt for {url}:")
  print(response.text)
  #処理
}
  else:
      print(f"No robots.txt file found at {robots_url}")
```
レスポンスのステータスコードが200番台（レスポンス成功）なら、
- robots.txtのURL
- そのURL内で表示されている内容
をテキストとして出力

そうでない場合、
`"No robots.txt file found at robots_url"`を出力

```py
if 'Disallow' in response.text:
                print("Disallowed paths found in robots.txt")
            else:
                print("No disallowed paths found in robots.txt")
        else:
```
レスポンスのテキストの中でDisallowが表示されていれば、`"Disallowed paths found in robots.txt"`と出力。
そうでなければ
`No disallowed paths found in robots.txt`と出力。

```py
except requests.RequestException as e:
        print(f"Error fetching robots.txt: {e}")
```
requests.RequestExceptionは例外クラスで、エラーをキャッチするための処理です。`as e`と書くことで、発生したエラー詳細を変数`e`に格納します。


また、`f`とは、f文字列（フォーマット済み文字列）と呼ばれるPythonの機能です。

 `f"..."`の形式を使うと、文字列の中に直接変数の値を埋め込むことができます。
{url}の部分には、変数urlの値が挿入されます。例えば、urlが`https://example.com`の場合、`f"robots.txt for {url}:`"は`"robots.txt for https://example.com:"`という文字列に展開されます。

## 最後に
ありがとうございました！
ちなみに、このプログラムを実行しなくてもURLに`https://example.com/robots_txt`と挿入すれば、非エンジニアでもrobots_txtのページにアクセスできます（なんやそら！！）。

ただ、エンジニアを目指している方にとっては、requestsやエラーハンドリングの練習などで大いに役立ちますので、ぜひ試してみてくださいませ。

ーーーーーーーーーーーー
普段はフリーランスのDXプログラマー＆マークアップコーダーとして稼働しています！
現在、2社協業中！
https://shuto-work.notion.site/Profile-232ee534179a418cbd913d36204c00ae