# Propsとは
  - 親コンポーネント→子コンポーネントにデータを送ることができる。
  - 子コンポーネントの中に書くroperties(props)をObjectに格納。
    - 例えば、
      
      ```javascript　
      <Btn text="Saved Change" />
      ```
      
    - 上記の```Saved Change```は、props(object)に格納される。
   
# Propsが変更されると
  - 親コンポーネントのstateも変更される→propsがre-renderされる（複数のpropsがある場合、ローディングが遅くなる恐れがあるため、変更があったpropsのみをrenderする必要がある）
```javascript
function Btn({ text, weight, changeValue }) {
      console.log(text, "was rendered");
      return (
        <button
          onClick={changeValue}
          style={{
            backgroundColor: "green",
            color: "white",
            padding: "10px 20px",
            border: 0,
            borderRadius: 10,
            fontWeight: weight ? 700 : 200,
          }}
        >
          {text}
        </button>
      );
    }
    const MemorizedBtn = React.memo(Btn);
    function App() {
      const [value, setValue] = React.useState("Save Changes");
      const changeValue = () => setValue("Revert Changes");
      return (
        <div>
          <MemorizedBtn text={value} weight={true} changeValue={changeValue} />
          <MemorizedBtn text="Continue" />
        </div>
      );
    }
    const root = document.getElementById("root");
    ReactDOM.render(<App />, root);
    ```
