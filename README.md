# JS 만을 사용해 컴포넌트 기반의 뷰를 만들어보자

```
    참고URL: https://junilhwang.github.io/TIL/Javascript/Design/Vanilla-JS-Component/#_1-%E1%84%89%E1%85%A1%E1%86%BC%E1%84%90%E1%85%A2%E1%84%80%E1%85%AA%E1%86%AB%E1%84%85%E1%85%B5%E1%84%8B%E1%85%B4-%E1%84%90%E1%85%A1%E1%86%AB%E1%84%89%E1%85%A2%E1%86%BC
```

## 컴포넌트와 상태관리

### 1. 상태관리의 탄생

2012년도 정도에는 javascript 를 공부할 때 제일 중요한게 jQuery 였다.<br>
jQuery 의 가장 큰 장점은 DOM API 이다. DOM 을 쉽게 조작할 수 있도록 만들어주는것에 더해 크로스 브라우징과 관련된 이슈를 해결해주었다.<br><br>
그런데 점점 브라우저와 javascript 가 발전하는 과정에서 아예 브라우저(클라이언트) 단에서 렌더링을 하고, 서버에서는 REST-API 혹은 GraphQL 같이 브라우저 렌더링에 필요한 데이터만을 제공하는 형태로 기술이 변화했다.<br>
이제는 직접적으로 DOM을 다루는 행위가 급격하게 감소했고, 상태(State)를 기준으로 DOM을 렌더링하는 형태로 발전한 것이다.<br>
DOM이 변하는 경우가 State에 종속 되어버린것이다.<br>
반대로 말하면, State 가 변하지 않을 경우 DOM 이 변하면 안 되는 것이다.
<br>
그리고 이러한 과정 속에서 <b>Client-Side-Rendering</b> 이라는 개념과 <b>상태관리</b> 라는 개념이 생기게 되었다.
<br>

### SSR과 CSR

SSR<br>

-   약 5년전 까지만 해도 JSP, PHP, ASP 등이 웹 개발 3대장이라고 불렸다.
-   위의 언급한 것들이 하는 역할이 바로 서버에서 HTML 을 만들어서 클라이언트에 넘겨주는 것, 즉 Server-Side-Rendering 이다.
-   따라서 클라이언트 단(브라우저)에서는 굳이 데이터를 깊은 단계까지, 정교하게 관리할 필요가 없었다.

<br>
CSR<br>
- Javascript 가 발전하면서 아예 브라우저(클라이언트) 단에서 모든 렌더링을 처리하려는 시도가 계속되었고, 그렇게 React / Angular / Vue 같은 프레임워크(혹은 라이브러리)가 탄생하였다.
- 브라우저(클라이언트) 단에서 렌더링을 하기 위해선, 렌더링에 필요한 상태를 정교하게 관리해야 한다.
- 그래서 Redux 같은 상태관리 라이브러리(혹은 프레임워크)가 생겨났다.
<br>

<br>
<br>
<br>
<br>

### 컴포넌트

Angular 가 CSR 의 시작이었다면, React 는 컴포넌트 기반 개발의 시작이었다. 그리고, Angular 와 React의 장점을 모두 수용한 Vue 도 나왔다.
<br>
어쨋든 중요한 점은 <b>현 시점의 웹 어플리케이션은 컴포넌트단위로 설계되고 개발</b>된다는 것이다. 그리고 컴포넌트마다 컴포넌트를 렌더링할 때 필요한 상태를 관리하게 되었으며, Proxy 혹은 Observer Pattern 등을 이용하여 이를 구현한다.
<br>
