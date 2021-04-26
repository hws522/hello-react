# Modern React with Velopert

<br>
<br>

### **JSX**

---

<br>

JSX 는 React 에서 컴포넌트의 생김새를 정의할 때 사용하는 문법이다.

```js
function App() {
  return (
    <div>
      <Hello />
      <Hello />
      <Hello />
    </div>
  );
}
```

위의 코드는 HTML 처럼 보이지만 Javascript 이다.

바벨이라는 도구를 사용하여, 이렇게 변환이 되는 것이다.

https://babeljs.io 에 접속하여 아래의 코드를 입력해본다.

```jsx
<div>
  <b>Hello,</b> <span>React</span>
</div>
```

그러면 아래의 화면처럼 React 로 변환된다.

```js
"use strict";

React.createElement("div", null, React.createElement("b", null, "Hello,"), " ", React.createElement("span", null, "React"));
```

jsx 로 작성한 코드가 javascript 로 제대로 변환되려면 규칙들이 존재한다.

1.  태그는 반드시 닫혀 있어야한다.

    그런데 태그중에서 `<input>` 이나 `<br>` 처럼 닫히지 않는 태그들이 있다. React 에서는 이들도 닫아줘야한다.

    `<input></input>, <br></br>` 처럼 닫아줘야 하지만 태그 사이에 아무것도 없을 경우, `<input />, <br />` 처럼 self closing 으로 해주어도 무방하다.

<br>

2.  2개 이상의 태그는 반드시 하나의 태그로 싸여 있어야한다.

    하지만 단순히 감싸기 위하여 불필요한 `<div>` 를 사용하는 것이 좋지 않은 상황이 많다. 스타일관련설정에서 복잡해진다거나, table 관련 태그를 작성할 때에도 내용을 div 로 감싸기엔 애매하다. 그래서 React 의 Fragment 라는 것을 사용하면 된다.

    ```js
    function App() {
      return (
        <>
          <Hello />
          <div>안녕히계세요</div>
        </>
      );
    }
    ```

    태그를 작성할 때, 이름없이 작성하게 되면 Fragment 가 만들어지는데 Fragment 는 브라우저 상에서 별도의 엘리먼트로 나타나지 않기 때문에 사용하기 적합하다.

<br>
