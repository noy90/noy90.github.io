<link rel="stylesheet" href="./style.css">

# コピーボックスつくりたい

<div style="text-align: right">2022/07/03</div>

下の方で使っているボックスのことです。 HTMLとCSSで実装しています。

カーソルで押すと全選択されるので、後はコピペするなり何なりと。

### 注意

今回使用している **textarea** タグは本来、**入力欄を作成するためのタグ**です。

それとは異なる用途で使用しているので、コピーボックスを作成する場合もっと他にいい方法があると思います。

<br>

### HTML

<textarea name="text" rows="3" wrap="off" spellcheck="false" onfocus="this.select();" readonly>
&lt;textarea name="text" rows="1" wrap="off" spellcheck="false" onfocus="this.select();" readonly&gt;
ここに文章を入力
&lt;/textarea&gt;
</textarea>

- textarea 内でコードを書きたい時 → **文字参照**を用いる  
    | 記号 | code |
    | :----: | :----: |
    | < | \&lt; |
    | > | \&gt; |

  [文字参照一覧(外部サイト)](https://www.scollabo.com/banban/apply/ap8.html)



### CSS

<textarea name="text" rows="22" wrap="off" spellcheck="false" onfocus="this.select();" readonly>
textarea{
    position: relative;
    width: 100%;
    line-height: 1.3;
    white-space: pre;
    color:white;
    background-color:rgb(60, 64, 67);
    resize: none;
    overflow-x: auto;
    overflow-y: hidden;
    scrollbar-width: thin;
}
textarea::-webkit-scrollbar {
    height: 9px;
}
textarea::-webkit-scrollbar-thumb {
    background: rgb(160, 159, 159);
    border-radius: 5px;
}
textarea::-webkit-scrollbar-track {
    background: transparent;
}
</textarea>

<br>

### 参考

>  [textareaについて](https://developer.mozilla.org/ja/docs/Web/HTML/Element/textarea)

>   [onfocus属性について](https://allabout.co.jp/gm/gc/23948/2/)
