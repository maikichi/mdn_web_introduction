## HTML （HyperText Markup Language、ハイパーテキスト・マークアップ・ランゲージ）

- strongのように要素の中に他の要素を入れることをネスト（or入れ子）と言う
  
```rb
<p>My cat is <strong>very</strong> grumpy.</p>
```

- 終了タグがない空要素（画像）

```rb
<img src="images/firefox-icon.png" alt="My test image" />
```
## HTML 文書の構造

```rb
<!doctype html>
<html lang="ja">
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width" />
    <title>テストページ</title>
  </head>
  <body>
    <img src="images/firefox-icon.png" alt="テスト画像" />
  </body>
</html>
```

- !DOCTYPE html: 文書型宣言。文書が正しく動作するために必要な前置き
- html、/html: このページのすべてのコンテンツを囲み、ルート要素と呼ばれることもある。ここでは文書の主要な言語を設定する lang 属性も指定する。
- meta charset="utf-8": どんなテキストコンテンツでも扱えるようになる。設定しない理由はない。
- title, /title: ページが読み込まれた時にブラウザーのタブに表示される。
- body, /body: テキスト、画像、ビデオ、ゲーム、再生可能な音声トラックなど、ページを訪れたウェブの利用者に表示したいすべてのコンテンツが含まれる。

<details><summary>アクセシビリティの考慮</summary>

## alt〜意味のある代替説明を書く〜
1. 目が不自由な人。著しく目の不自由な人はよくスクリーンリーダーと呼ばれるツールを使っていて、それが画像の alt 属性の内容を読み上げる
2. 何らかの理由で画像の表示に失敗した場合にalt属性が表示される

```rb
<img alt="海岸に立っているイワトビペンギン" src="penguin.jpg" />
```
明確で簡潔に画像の内容を説明するものにする。画像そのもの存在を説明するものであったり、画像のファイル名であったりするべきではない。<br>※alt 属性が画像にない場合、読み上げソフトによっては代わりに画像のファイル名を読み上げることがある。ファイル名が画像の内容を表していない場合、これが操作を混乱させる可能性があるので注意。

</details>

## テキストのマークアップ

### 見出し
- HTMLには 6 段階の見出しがあるが、よく使うのは 3 から 4 まで！
- 見出し要素はアクセシビリティや SEO などの理由で使用されている
  
```rb
<!-- 4 段階の見出し -->
<h1>メインタイトル</h1>
<h2>最上位の見出し</h2>
<h3>小見出し</h3>
<h4>孫見出し</h4>
```

### 段落
- 1 つまたは複数の段落に入れ、 img要素のすぐ下に配置
```rb
<p>This is a single paragraph</p>
```
### リンク
- href(hypertext reference)

```rb
<a href="https://www.mozilla.org/en-US/about/manifesto/">
  Mozilla Manifesto
</a>
```
※アドレスの先頭にある https:// や http:// の部分（プロトコルと言う）を書き忘れないように!
