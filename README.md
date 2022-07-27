## Context

- 전역적(global)인 데이터를 다룰 때 사용
- 전역 데이터를 Context에 저장한 후, 데이터가 필요한 컴포넌트에서 해당 데이터를 불러와 사용할 수 있다.
- Context에 저장된 데이터를 사용하기 위해서는 공통 부모 컴포넌트에 Provider를 사용해 제공해야 한다.  
<br>

## Context API
### React.createContext()

```js
const AppStateContext = React.createContext();
```

- Context 객체 생성
- 파라미터에는 기본값 설정

<br>

### Context.Provider

```js
<AppStateContext.Provider
  value={{
    prototypes,
    orders,
    addToOrder,
    remove,
    removeAll,
  }}
>
  {children}
</AppStateContext.Provider>
```

- 정의한 Context를 하위 컴포넌트에 전달하는 역할을 하는 컴포넌트
- 컴포넌트 간 공유하고자 하는 값을 `value` 로 설정
- Provider 하위에서 해당 Context를 가진 컴포넌트는 Provider의 value prop이 바뀔 때마다 렌더링

<br>

### React.useContext()

```js
const { addToOrder, remove, removeAll } = useContext(AppStateContext);
```

- 전달받은 Context 객체로 Context의 현재 값을 반환
