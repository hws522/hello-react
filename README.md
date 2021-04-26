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
