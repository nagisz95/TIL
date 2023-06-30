# arr.map
  配列の要素全体を対象に関数を呼び出し、関数を呼び出した結果を配列に格納してリターンする。
  ```javascript
  let result = arr.map(function(item, index, array) {
    // 既存の要素の値ではなく、関数を呼び出した新しい値をリターン
  });
  ```
  ```javascript
  toDos.map((item, index) => (
          <li key={index}>{item}</li>
        ))
  ```
  
