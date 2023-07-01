# react-router-dom
[docs] https://v5.reactrouter.com/web/guides/quick-start
reactでrouterを作れるpkg。

# 使用例
root router("/")から別のrouterに移動した後、再びroot routerに戻ってきた時、再度renderしなくてもページの表示ができるようになる。
```javascript
import React from "react";
import { BrowserRouter as Router, Route, Routes } from "react-router-dom";
import Home from "./routes/Home";
import Detail from "./routes/Detail";

function App() {
  return (
    <Router>
      <Routes>
        // Detailに移動させるRouter
        <Route path="/movie" element={<Detail />}></Route>
        // Home移動させるRouter
        <Route path="/" element={<Home />}></Route>
      </Routes>
    </Router>
  );
}

export default App;
```
