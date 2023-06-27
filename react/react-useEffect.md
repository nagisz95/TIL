# useEffect
functionを１回だけ実行したい時（例えば、最初のrenderの際にAPIを呼び出したにも関わらず、stateが変更された場合、再びAPIを呼び出すのは良くない）に使う。

# 使い方
useEffectは２つのargumentが必要。
１つ目は１回だけ実行したい関数を入れて、
２つ目は何をwatchして反応するか(dependencies)を入れる。

```javascript
import { useState, useEffect } from "react";

function App() {
  const [counter, setValue] = useState(0);
  const onClick = () => setValue((prev) => prev + 1);
  useEffect(() => {
    console.log("CALL THE API....");
  }, [counter]);
  return (
    <div>
      <h1>{counter}</h1>
      <button onClick={onClick}>click me</button>
    </div>
  );
}
export default App;
```
