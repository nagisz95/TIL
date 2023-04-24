# Document.createElement()
  JSからHTMLに直接要素を生成できる。
  ただし、createElementで生成された要素は存在はするが、**HTML上にそのまま追加されるわけではない。**

構文は下記の通り。


```javascript 
let element = document.createElement(tagName[, options]);
```


ここで言うtagNameは、HTMLのtagを意味する。例えば、div, ulなど…


# appendChild()
  上記のcreateElementで生成したelementをHTML上の後尾に追加する。
  
  例えば、
  
```javascript 
const paragraph = document.body.appendChild();
```


# prepend()
  createElementで生成したelementをHTML上の先頭に追加する。
  
  例えば、
  
```javascript 
const paragraph = document.body.prepend();
```
  
# appendChild()とprepend()を一緒に使ってみた
  
```javascript
let div = document.createElement("div");
div.append("Some text");
div.prepend("Headline: ");
console.log(div.textContent); // "Headline: Some text"
```
