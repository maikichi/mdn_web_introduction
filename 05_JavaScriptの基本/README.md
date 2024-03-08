## JavaScript の基本
ウェブサイトに対話性を追加するプログラミング言語

index.html ファイルの </body> 終了タグの直前に新しい行で、以下の新しい要素を追加
```rb
<script src="scripts/main.js"></script>
```

### コメント
```rb
/*
挟まれているすべてがコメントです。
*/
```
コメントに改行が含まれていない場合、次のように2つのスラッシュの後ろに記載する方が簡単
```rb
// これはコメントです
```
### 演算子
- 厳密等価 === 
```rb
let myVariable = 3;
myVariable === 4;
```
- 否定、非等価 !, !==
```rb
let myVariable = 3;
!(myVariable === 3);
```
```rb
let myVariable = 3;
myVariable !== 3;
```
### 条件文
```rb
let iceCream = "チョコレート";
if (iceCream === "チョコレート") {
  alert("やった！チョコレートアイス大好き！");
} else {
  alert("あれれ、でもチョコレートが好きなのに......");
}
```
### 関数
```rb
function multiply(num1, num2) {
  let result = num1 * num2;
  return result;
}
```
### イベント
最も分かりやすい例は click イベントで、マウスで何かをクリックするとブラウザーによって発行されるもの
```rb
document.querySelector("html").addEventListener("click", () => {
  alert("痛っ! つつかないで!");
});
```
### 画像の切り替えの追加
画像をクリックすると JavaScript を使用して2つの画像を切り替えることができる
```rb
const myImage = document.querySelector("img");

myImage.onclick = () => {
  const mySrc = myImage.getAttribute("src");
  if (mySrc === "images/firefox-icon.png") {
    myImage.setAttribute("src", "images/firefox2.png");
  } else {
    myImage.setAttribute("src", "images/firefox-icon.png");
  }
};
```
### パーソナライズされた挨拶メッセージの追加
ユーザーがサイトにアクセスしたときに、ページの表題をパーソナライズされた挨拶メッセージに変更してみよう。
この挨拶メッセージは、ユーザーがサイトを離れて後で戻った時にも保存されるようにする

1. index.html では、 <script> 要素の直前に次の行を追加
```rb
HTML
<button>ユーザーを変更</button>
```

2.main.js では、次のコードを下記のとおりにファイルの最後に配置。これは新しいボタンと見出しへの参照を変数に格納
```rb
JS
let myButton = document.querySelector("button");
let myHeading = document.querySelector("h1");
```

3. パーソナライズされた挨拶を設定する以下の関数を追加
```rb
JS
function setUserName() {
  const myName = prompt("あなたの名前を入力してください。");
  localStorage.setItem("name", myName);
  myHeading.textContent = `Mozilla はかっこいいよ、${myName} さん、Mozilla はかっこいいよ。`;
}
```
- setUserName() 関数では、prompt() 関数を使用して、alert() のようにダイアログボックスを表示しているが、prompt() は alert() とは異なり、ユーザーにデータを入力するよう求め、ユーザーが OK を押した後に変数にそのデータを格納する。この場合、ユーザーに名前を入力するよう求める。
- 次に、localStorage と呼ばれる API を呼び出すことで、ブラウザーにデータを格納して後で受け取ることができる。 localStorage の setItem() 関数を使って、'name' と呼ばれるデータを作成し、 myName に入っているユーザーから入力されたデータを格納。
- 最後に、見出しの textContent に文字列と新しく格納されたユーザーの名前を設定。

4. 以下のような条件ブロックを追加。最初に読み込んだときにアプリを構造化するので、これを初期化コードと呼ぶこともできる
```rb
JS
if (!localStorage.getItem("name")) {
  setUserName();
} else {
  const storedName = localStorage.getItem("name");
  myHeading.textContent = `Mozilla はかっこいいよ、${storedName}`;
}
```
- このブロックでは、最初に name のデータが存在しているかどうかをチェックするために否定演算子（! で表される論理否定）を使用。存在しない場合は、作成するために setUserName() 関数が実行される。存在する場合は（つまり、以前の訪問時にユーザーが設定した場合）、 getItem() を使用して格納された名前を受け取り、 setUserName() の中で行ったのと同様に、見出しの textContent に文字列とユーザーの名前を設定する。
  
5. 最後に、以下の onclick イベントハンドラーをボタンに設定。クリックすると、setUserName() 関数が実行される。これでユーザーがボタンを押すことで、好きな時に新しい名前を設定できるようになる
```rb
JS
myButton.onclick = () => {
  setUserName();
};
```
### ユーザー名か null か
ユーザーが null や空白の名前を入力していないかチェックするよう、setUserName() 関数を書き換える。4のコードを下記に変更
```rb
JS
function setUserName() {
  const myName = prompt("あなたの名前を入力してください。");
  if (!myName) {
    setUserName();
  } else {
    localStorage.setItem("name", myName);
    myHeading.textContent = `${myName} さん、Mozilla はかっこいいよ。`;
  }
}
```
