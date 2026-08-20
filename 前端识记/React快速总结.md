## setState

`setState`是给下一次渲染准备的值，所以不会立即更新
```jsx
  const naive = () => {
    setCount(count + 1);
    setCount(count + 1);
    setCount(count + 1);
  };
```
`count`在这个周期内不会更新，所以一直是同一个值0，只会加一次1

> 每次渲染都会产生一套**全新的**：props、state 值、局部变量、函数、effect。  
上一次渲染里的 `count` 和这一次的 `count` 是两个不同的常量，互不影响。这叫 **snapshot（快照）**。


`setXXX`支持传入一个函数，传参为当前积攒的数值
```jsx
  const fixed = () => {
    // setCount(c => c + 1) ... x3
    setCount(n=>n+1)
    setCount(n=>n+1)
    setCount(n=>n+1)
  };
```

> [!tip] 什么时候用
> 新的值依赖旧的值，可能在同一个批次更新，或者在异步回调中


### 常见错误
#### 引用过去状态值不更新
```jsx
  const [n, setN] = useState(0);

  // ❓ 点「+1 后延迟 3 秒 alert」，然后在 3 秒内狂点「+1」，alert 会显示几？
  const delayed = () => {
    setN(n + 1);
    setTimeout(() => {
      alert('3 秒前那次渲染看到的 n = ' + n);
      
    }, 3000);
  };
```

因为冻结了快照`n`，所以会显示点击`setTimeout`时的值
```jsx
 const [n, setN] = useState(0);
  const nRef = useRef(n);

  // ❓ 点「+1 后延迟 3 秒 alert」，然后在 3 秒内狂点「+1」，alert 会显示几？
  const delayed = () => {
    setN(nRef.current + 1);
    nRef.current++;
    setTimeout(() => {
      alert('3 秒前那次渲染看到的 n = ' + nRef.current);
    }, 3000);
  };

  return (
    <div className="card">
      <h3>B. 快照会被「冻」在回调里</h3>
      <div className="big">{nRef.current}</div>
      <button className="btn" onClick={() => { setN(nRef.current + 1); nRef.current++; }}>
        +1
      </button>
      <button className="btn primary" onClick={delayed}>
        +1 后延迟 3 秒 alert
      </button>
```
使用`useRef`可以保持在最新值 **（因为引用了这个变量的地址），但是ref无法驱动页面更新**，所以更新的时候一直使用`useRef`即可，然后驱动更新的时候把`state`变量赋一下`ref.current`让他更新一下

<details>
<summary>hack方法 使用useState</summary>
因为使用更新函数`useState` 中的参数也能获取到最新值。但是这个是不正规的写法，在生产中不要使用
</details>




#### 改变对象值不更新
```jsx
  // ❌ 直接改
  const mutate = () => {
    user.address.city = '北京';
    setUser(user); // 同一个引用！React 用 Object.is 比较 → 认为没变 → 不重渲染
  };

  // ✍️ TODO: 正确的不可变更新
  const immutable = () => {
    setUser({ ...user, address: { ...user.address, city: '北京' } })
  };
```

`setState`发现是同一个引用会直接不更新，所以需要手动创建一个新的对象

#### state不可变，请全部通过`setXXX`更新
```jsx
 const sort = () => {
    // setTodos([...todos.sort()])
    setTodos([...todos].sort((a, b) => a.text.localeCompare(b.text)))
  };
```

`todos.sort()`已经修改了todos原数组，违反了state不可变原则。所以要先复制拷贝一个新数组`[...todos]`

同样的，在
```jsx
    setTodos(todos.map(item => item.done = true))
```
在里面修改了原数组内容，因为**新的数组还会保持对原来对象的引用！**
```jsx
  const doneAll = () => {
    // setTodos(todos.map(item => item.done = true))
    setTodos(todos.map(item => ({ ...item, done: true })))
  };
```
